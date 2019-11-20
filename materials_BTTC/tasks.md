# タスク集

>## `unable to convert unpermitted parameters to hash`
1. 子どもページから検索かけたときに出るエラー
2. ストロングパラメタ仕様なのに送信がpermitされていない状態で`.to_hash`を用いてハッシュ化しているために出るエラー
3. 案
   `lib/enju_ndl/query_params_builder.rb` L.145
   ```ruby
   params = params.permit!.to_hash
   ```

   ```ruby
   # ストロングパラメータの対応を行う必要あり
   params.permit!
   params = params.to_hash
   ```
   
4. 公式
   [StrongParameters](https://railsguides.jp/action_controller_overview.html#strong-parameters)

5. お残しリストに言及あるはずなので書いておく 

>## 修正
1. showやsearch viewで([""])が入る問題
- m.titleなどに.to_s.gsub!(/\[\"+|\"\]/, "")を付け加える
- app/view/children/show.heml.erbの３０行目

2. 図書情報(タイトルとか)の照会先
   一覧(search.html.erb): solr(検索用API)
   書誌詳細(show.html.erb): DB(posgre)

3. 注意
   `Resource`モデルというモデル名がある(showのDB)

>## aasmのサーバ立ち上がらない問題
`model/resource.rb`の`:pending`部と`:rejected`部コメントインするとエラー
ログ
```
The scope body needs to be callable.
・・・
```
- aasm gemのバージョン上げたら直った

>## テストの手法
1. ホワイトテスト　C0テスト：命令文が全部実行されているか(if文も含め)

>## NDL検索機能のテスト
1. テスト要綱
   - 「すべての連携先を検索する」は確認しないで良し(横断検索タスクのため)
   - タイトルorキーワード:「教育」,出版地：「北海道」検索で統一

>## 検索結果一覧において著者の<em>タグがエスケープされちゃう問題
1. `app\views\books\_list_group_item.erb`(一覧表示画面), L.61側のhighlightメソッドで適切にhtml_safeされていない
2. `app\helpers\ndl_application_helper.rb`, L.978のtr_double_slashメソッドが原因？
3. `app\helpers\ndl_application_helper.rb`, L. に`highlight`メソッドあり

>## 書誌詳細検索マッチキーワードがハイライトされない問題
1. `app\views\books\show.html.erb`(L.70)から呼び出されるパーシャルである`app\views\books\_detail_content.html.erb`に関する問題
2. `_detail_content.html.erb`のL.16以降がハイライトされて欲しい箇所(chromeの検証機能よりid名照会)
3. `app\helpers\ndl_application_helper.rb`のhighlightメソッドは`keywords`がnullの時ハイライトしない
   -  `_detail_content.html.erb`の`highlight_keywords`がnullだった。(`<%= highlight_keywords %>`挿れてチェック)これが原因か
   -  `books_query`の方も空だった
   -  さらに親の`cookies[:books_query]`がそもそも空(`<%= cookies[:books_query].inspect %>`挿入で調査)ー＞これが原因

[流れ]
- 検索する
- 検索クエリが`cookies[:books_query]`に保存される(はず、 code不明)
- その内容を基に書誌詳細画面でキーワードハイライトを行う

- 環境の違いに起因するものだった

>## 障害者検索＞検索フォームが機能しない問題
- 「原本出版社ほか」、「製作者、所蔵館」フォームから検索実行した際、`一時的に利用できません`ページ(500エラー)にリダイレクトされる

下記は該当ログ
  ```
    172.18.0.1 - - [18/Nov/2019:05:13:53 UTC] "POST /books/search HTTP/1.1" 302 219
http://localhost.ndl.go.jp:3000/books?any=%22%22 -> /books/search

RSolr::Error::Http (RSolr::Error::Http - 400 Bad Request
Error: 'org.apache.solr.search.SyntaxError: Cannot parse \' ui_media_type_sm:8 (((publisher_morph_text:北海道^400 OR publisher_cjk_norm_text:北海道^20 OR publisher_cjk_text
:北海道^20 OR publisher_sm:北海道^500) [:repository_no_sm]:R100000049) OR digitized_publisher_sm:*北海道* OR library_sm:*北海道*)(access_right_sm:S01P99U99)\': Encountered
" "]" "] "" at line 1, column 158.
  ```
  - ` 'org.apache.solr.search.SyntaxError: Cannot parse \'`の`\'`は`'`を表示するためのエスケープシーケンスと思われる(\'～\'間で成立)
    - やはり`"]" "] "`がエラー原因か

1. `app\views\layouts\_books_query_form.html.erb`が検索フォームのパス
   - L.465以降が障害者検索のフォームか
2. `config\locales\enju_ndl_ja.yml`に検索フォーム名の定義あり
   - original_publisher: 原本出版者ほか
   - producer: 製作者、所蔵館
3. RSolrの設定ファイル：`vendor\bundle\ruby\2.6.0\gems\rsolr-2.2.1\lib\rsolr.rb`
4. 不要文字列(`"]`)が含まれていることによるエラー？
   - でもタイトルとかは含まれていても対応される

5. params[:medyatypes] = ["8"]をparams[:medyatypes] = nilとしたところ
   Error: 'org.apache.solr.search.SyntaxError: Cannot parse \' (((publisher_morph_text:北海道^400 OR publisher_cjk_norm_text:北海道^20 OR publisher_cjk_text:北海道^20 OR publi
sher_sm:北海道^500) [:repository_no_sm]:R100000049) OR digitized_publisher_sm:*北海道* OR library_sm:*北海道*)(access_right_sm:S01P99U99)\': Encountered " "]" "] "" at line
 1, column 139.
 - errorログからmediatype_sm: 8が消えた

6. `lib\enju_ndl\solr_search.rb` L.503の`add_word`メソッド(`lib\enju_ndl\ndl_solr.rb` L.40)への変数の渡し方の問題だった
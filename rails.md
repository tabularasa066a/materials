# railsについて

>## MVCの各部分の役割
1. Controller:
- ブラウザからURLを通じてリクエストがあった際
  コントローラと同じ名前のビューフォルダから
  アクションと同じ名前のHTMLファイルを探してブラウザに返す
- `ルーティング（routers.rb）`：ブラウザとコントローラをつなぐ
  - routerの並びに注意！（undefined methodのエラーが出る）
- 処理の流れ：
`ブラウザ`->`ルータ`->`コントローラ`->`ビュー`  

![処理の流れ](images/progate_rails/about_routers.png)  
![変数の渡し方](images/progate_rails/handling_variables.png)  

> `rails g controller users index`にて生成

1. Model:  
- DBのテーブルを操作するための特殊なクラス（テーブルのイメージ）  
  - １インスタンスがレコードに相当 
  - `@変数名　= Model名.all`とすると、配列に各レコードが保存  
  
> 1. `rails g model Post content:text`にて生成
> 2. `rails db:migrate`にてマイグレーションファイルをdbに反映

![モデル名.all](images/progate_rails/model_all.png)

- バリデーションについて
  ![バリデーション](images/progate_rails/validates.png)  
  `validates :content, {presence: true, length: {maximum: 140}}`  
  - エラーメッセージの表示
  ![エラーメッセージ](images/progate_rails/error_message.png)  
- columnの追加
>`rails g migration add_collumn_to_users`
>`migrationファイル`にて`add_columnメソッド`

1. View
- `params[:取得したいパラメータ名]`で値を得られる
- `<textarea>初期値</textarea>`  
- yieldの取り扱い
![yield](images/progate_rails/yield.png)
- paramsの取り扱い
  ![paramsについて](images/progate_rails/params.png) 
  - 文字列で返ってくる点注意
- flashメッセージ  
  ![flashメッセージ](images/progate_rails/flash.png)

- フォームの初期値はvalue, 内容はnameタグにて取得

- `application.html.erb`について
  ![application.html.erb](images/progate_rails/about_application_html_erb.png)
  - アクションで渡す共通した変数は`application_controller`にまとめ
    `before_action :メソッド名`で最初に実行すると便利
    ![before_actionの構文](images/progate_rails/before_action.png)

- 画像の表示について
![画像の表示](images/progate_rails/displaying_image.png)
![画像アップロード](images/progate_rails/uploading_image_tag.png)
![form_tagによる画像送信](images/progate_rails/sending_image.png)
  - 画像アップの流れ
  - ![画像のアップ](images/progate_rails/image_uploading_process.png)
  - ![画像の保存](images/progate_rails/saving_image.png)
>## よく使うヘルパー
1. `form_tag("URL") do |f|`  
   `送るもの(textareaやsubmitボタンも)`  
   `end`  
   - URLを`routers.rb`に渡す->コントローラに渡す
   - `name=`タグで入力データを送信する->`params`で受け取れる
     `<textarea name="content">aaa</textarea>`  
     `params[:content]="aaa"`と出力  

2. `redirect_to("URL")`  
   - ページを強制的に遷移

3. `link_to("URL", method: "post")`
   - postのときはこれ

4. `session[:KEY]`
   - ログイン処理で`session[:user_id]=@user.id`とすればログイン状態を保持
   - `session[:user_id] = nil`でログアウト

5. `where`メソッド：ある条件に合致する複数のデータを取得（`find_by`は一対一）
  ![where](images/progate_rails/where.png)
6. `count`メソッド：データの個数を取得
   ![count](images/progate_rails/count_method.png)
7. `has_secure_password`
- `bcrypt`をインストールすることで使える
  ![bcrypt](images/progate_rails/handling_bcrypt.png)  
  ![bcrypt](images/progate_rails/handling_bcrypt2.png)
>## その他
1. getとpostの違い
- get: データベースを変更しない
- post: データベースを変更する  
  ![getとpost](images/progate_rails/get_post.png)
2. `render("フォルダ名/ファイル名")`
- 別のアクションを経由しないで直接ビューに行く
- 直前の入力内容が消されない
- モデル内にインスタンスメソッドを定義する
  ![メソッド定義１](images/progate_rails/defining_instance_method.png)
  ![メソッド定義２](images/progate_rails/defining_instance_method2.png)
- font-awesomeの画像にリンクを張る際の注意
  ![fontawesome](images/progate_rails/font_awesome.png)

>## データベース間の紐づけ
1. 例：いいね！機能の実装  
- likeテーブルを作る
  - このモデルにレコードが入る＝いいね！される
  ![likeテーブル](images/progate_rails/implementing_favorite.png)

>## 用語
gem: RubyやRailsでよく使う機能をパッケージ化したもの

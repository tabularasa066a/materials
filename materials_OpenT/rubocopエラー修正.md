> tbo-modelのrubocopエラー修正

- `tbo-model`のREADMEわかりやすいので参照

- rubocopコマンド：`rubocop`(dockerに入ってからやること)
  →rubocopの突っ込みを消すのがメインになる
- 便利なコマンド：`rubocop --auto-correct`
  ->自動で修正をかけてくれる！
- 警告基準は`tbo_model/.rubocop.yml`に存在

  (参考)[Qiita](https://qiita.com/t-vinn/items/fe57b5d6440712016742)

>## 修正計画
1. `Layout/SpaceBeforeBlockBraces: Space missing to the left of {.`
- expect{やchange{ のかっこに半角スペースを入れる

1. `Style/StringLiterals: Prefer double-quoted strings unless you need single quotes to avoid extra backslashes for escaping.`
- 文字列を囲むとき、`' '`よりも`" "`の方がよい(と`.rubocop.yml`にて規定)

3. `Metrics/BlockLength: Block has too many lines.`
- 一つのブロックに記述される行数が`26`行以上の場合、警告される。(`.rubocop.yml`)
- factorieディレクトリ以下のテストデータに関してはしょうがなくない？

- migrationファイルについてはしょうがなくない？
(参考)[Qiita記事](https://qiita.com/jkr_2255/items/b5de2a514ca8a96f788e)

4. `Metrics/AbcSize: Assignment Branch Condition size for change is too high.`
- Assignment(変数への代入)・Branch(メソッド呼び出し)・Condition(条件文)の合計ポイントを自動計算して、基準値を超えると警告を出す。

（参考）
- [はてブ記事](http://hikitest.hatenablog.com/entry/2015/01/14/034346)
- [AbcMetrix](http://wiki.c2.com/?AbcMetric)

5. `Lint/AmbiguousBlockAssociation: Parenthesize the param [インスタンス呼び出し句] to make sure that the block will be associated with the [メソッド名] method call.`
- spec文などにおいて、括弧の配置の仕方などに対する文句
(参考)[Qiita記事](https://qiita.com/dmiya/items/171fd059c337afdda7fa)
- change {}の形式をやめてchange()の形式にする
  ```ruby
    expect { instance.save! }.not_to change { instance.updated_by }
  ```
  を下記のように修正する(右端のメソッドをシンボル化))
  ```ruby
    expect { instance.save! }.not_to change(instance, :updated_by)
  ```

1. `Naming/HeredocDelimiterNaming: Use meaningful heredoc delimiters.`
- ヒアドキュメントのデリメタ(EOFとか)の名前もっとわかりやすくしろ
delimiter(≒separator): 区切り文字

7. `Style/GlobalVars: Do not introduce global variables.`
- グローバル変数を使うな

>### $ON_ETL_APIについて
- GlobalVars使うなと突っ込まれた箇所
- boolean型
- `etl_filter.rb`と`etl_filter_spec.rb`にて使用
- 情報連携中でもON_ETL_APIがtrueの場合DBの更新処理ができる

>## その他
1. factory bot
   - rspec用などのテストデータを作成するのに便利なgem

2. dockerコンテナ内でのrspecの実行
  `tbo-model` コンテナの中に以下のコマンドにて入る
  ```bash
  $ docker-compose run --rm tbo-model bash
  ```

  `tbo-model` コンテナ内にてテストを実施する
  ```bash
  $ bundle install --path vendor/bundle
  $ DB_HOST=db bundle exec rake   # これがrspecテストの実行コマンド
  ```

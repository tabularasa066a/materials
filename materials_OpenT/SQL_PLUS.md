# SQL*PLUSについて
1. SQL*PLUSとは
   OracleDBのコンソール

2. 接続方法
  `cd /home/instantclient_19_3/etl_tbo-payment_ruby`
  `docker-compose up`
  `sqlplus set_ttp_app/set_ttp_app@//127.0.0.1:1521/XE`
  or(後者のほうが良い)`
  `cd /home/instantclient_19_3/etl_tbo-payment_ruby`
  `docker-compose up`
  `docker exec -u 1000 -it oracle /bin/bash`
  `sqlplus`
  ユーザ名：system
  password：pLocal

3. 便利なコマンド
  - テーブル一覧取得：
    `select table_name from all_tables;`
  - スキーマ一覧取得：
    `select distinct owner from all_objects order by owner;`


4. 注意点
- SQL文を実行する際にスキーマの指定が必要
  `select * from set_ttp_app.etl_terminals;`

5. 用語集
- `スキーマ`と`テーブル`の違い：
  `ユーザは人、スキーマは鞄、テーブルはペン`
  `スキーマはテーブルなどのオブジェクトの集合体、スキーマの中にテーブルやビューが格納される`

- `テーブルを作成する`とは：
  あなた（ユーザー）がカバン（スキーマ）の中にペン（テーブル）を入れる


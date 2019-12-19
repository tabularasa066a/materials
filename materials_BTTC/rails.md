# railsについて

>## 用語と概念
1. [ストロングパラメータ](https://qiita.com/mochio/items/45b9172a50a6ebb0bee0)
   - DBに入れる値を制限することで、不正なパラメタの入力を防ぐ仕組みのこと
   - `.permit`で許可する値を決めれる

>## メソッド


>## 注意
1. ローカルサーバを再起動するとなくなるエラーもある
2. httpエラー(404など)表示用のviewは`public/`配下にあり

>## デバッグ
1. debugの便利メソッド(View用)
   `app/views/layouts/application.html.erb`
   ```ruby
    <!DOCTYPE html>
    <html>
    <body>
        <%= render 'layouts/header' %>
        <div class="container">
        <%= yield %>
        <%= render 'layouts/footer' %>
        <%= debug(params) if Rails.env.development? %>
        </div>
    </body>
    </html>
    ```

2. loggerを使う方法(controller用)
   ```ruby
   Rails.logger.error("[debug](show用)---#{resource.inspect}")
   ```

   - `vi log/development.rb`で見る

>## 諸概念について
1. lambda式
   - def 定義をワンライナーで書けるようになる(継承しないようなメソッドの場合)

2. DBコンソールへのアクセス(`config/database.yml`を基にアクセス)
   - `bunndle exec rails dbconsole`
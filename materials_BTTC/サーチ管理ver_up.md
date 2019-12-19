# サーチ管理のバージョンアップ
- ローカルサーバを立ち上げる

1. gem
- gem 'fastercsv', '1.5.5'へ
- gem 'RedCloth', '4.3.2'へ
- gem 'rails-geocoder'は'geocoder'に変わった
- gem cancanはcancancanへ？

2. ecrypt関連
   - config/initializers/devise.rbをすべてコメントアウト

3. devise関連
 undefined method `devise' for User (call 'User.connectio
n' to establish a connection):Class (NoMethodError)
   - `config/initializers/devise.rb`をすべてコメントアウト
   - routes.rbの該当箇所コメントアウト

4. 
 undefined method `debug_rjs=' for ActionView::Ba
se:Class (NoMethodError)
   - `config/environment/develop.rb`のdebug_rjs=箇所コメントアウト

5. `vendor/plugins/enju_iss_search`配下から足りないファイル移動させる



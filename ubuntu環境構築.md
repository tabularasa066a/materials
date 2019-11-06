# ubuntuの環境構築まとめ

>## ruby on rails
1. `rbenv`を用いる（プロジェクト毎に異なるバージョンのrailsやrubyを扱うため）
- 基本的にインストールはこれを通して行う
  
- rbenv install `インストールしたいrubyのバージョン数字`
- rbenv versions
- rbenv global `インストールしたrubyのバージョン数字`
- rbenv local `インストールしたrubyのバージョン数字`

- 複数のバージョンを取り扱う場合には`rbenv local`で！

- `gem install bundler`
- `rbenv rehash`

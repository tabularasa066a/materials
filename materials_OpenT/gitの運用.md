# gitの運用について

>## pull requestの出し方(dockerコンテナ内での操作)
1. developから`git clone`後、**直ちに**ブランチを切る：
   `git branch feature/{ブランチ名(任意)}`
2. ブランチを移動する：
   `git checkout feature/{ブランチ名(任意)}`
3. ファイルのコミットを行う：<br>
   `git add .`<br>
   `git commit -m "{コミット文}"`
   - この際認証を求められるので
     `git config --global user.email "tabularasa066@gmail.com"`を実行
4. `git push`
5. gitのwebページから`new pull request`

(参考)[Qiita記事](https://qiita.com/takamii228/items/80c0996a0b5fa39337bd)

>## git cloneしない場合のgit push手順
1. `git init`
   - `.git`という隠しディレクトリができる
2. ローカルリポジトリにいったん反映してステージングへ
   - `git add .`
   - `git commit -m "{コミット文}"`
   ->省略形の`git commit -am "{コミット文}"`としてもよい(ファイルを新規追加した際はこの省略形はダメ)
3. github上で作成リポジトリ(リモートリポジトリ)への反映
   `git remote add {github上で作成したリポジトリ名} {URL}`
   - 2回目以降はこの操作いらん
4. `git push origin master`

(参考)[Qiita記事](https://qiita.com/yukibe/items/9ef9d54f2e7d53cfb51c)

>## ファイルパーミッションの変更時(chmod)差分に表示されるのを無視
1. `git config core.filemode false`で差分に出さない設定
2. `git config -l | grep filemode`で`false`になってるか確認

>## git一般
1. アップしたくないファイルやディレクトリは`.gitignore`ファイルに記載
   - `.gitignore`ファイルがなかったら作る
   - `git rm --cached {ファイル名}`->`git commit/push`でアップ済みのファイルを削除できる
2. `git push origin feature/revises_DBvalidations`のように指定する必要がある。(`git branch -a`で確認のこと)
   - `git push {リモートレポジトリ(URLも可)} {ブランチ名}`
3. AuthorやCommiterの修正はやっておくこと
4. git pull時にコンフリクトがある場合
  - `git reset --hard [ブランチ名]`
  - `git pull`
5. 元々クローンしていたものを編集するときは最新版がリモートに反映されている可能性があるため`git pull`すること。
6. git add 時はファイルを絞る
7. ローカルでディレクトリ構造を変えたがgit hub上で認識されないとき
   - `git rm --cached [directory名]`で一旦そのディレクトリを削除
   - `git add [directory名]`で再度add
   - `git commit`, `git push`

(参考)
[Qiita記事](https://qiita.com/leon-joel/items/a1ebe76f21c76e862b9b)
- トラブったらこれ

>## 初期設定と意識すること
1. commiterとauthorの設定
   [Qiita記事](https://qiita.com/sea_mountain/items/d70216a5bc16a88ed932)
2. branchは必ず最初に切ること
3. [gitの初期設定](https://qiita.com/wnoguchi/items/f7358a227dfe2640cce3)
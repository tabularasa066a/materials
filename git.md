# gitについて

>## git用語
ローカルリポジトリ：自分の環境(PC)上にあるgitに送るファイル群のこと
リモートリポジトリ：GitHub上にあるリポジトリのこと

>## pushまでの流れ
1. `git init`  
- ローカルリポジトリの作成

1. `git add .`  
- 作業内容をインデックスに追加してコミットに備える  

1. `git remote add origin URL`

1. `git commit -m "'メッセージ'"`
- ローカルリポジトリに変更を反映させること

1. `git push origin master` 
- リモートリポジトリに変更を反映させること

>## 注意
1. https接続とSSH接続がある
- SSH接続する際は公開鍵と秘密鍵を作成し、githubの方に公開鍵を乗せる設定をする必要がある。
- `git remote -v`で接続方式を確認

1. > ! [rejected]        master -> master (non-fast-forward)
   > error: failed to push some refs to
   と出たとき
   `git push -f origin master`とすることで強制的にupできるが、他のコミットは全部消える

1. indexからローカルリポジトリにコミットを行う
   - indexに加えるからadd

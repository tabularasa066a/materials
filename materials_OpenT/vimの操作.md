# vimの操作

>## vimgrep
1. ファイル内やディレクトリ内から、特定の語句を縦横無尽に検索
2. `vim [ディレクトリ名]`でvim explorerに入る
3. `:vim 検索ワード 検索先`にて検索が行える
4. 複数候補がある場合
   ```bash
    # 次の結果を表示する
    :cn
    # 前の結果を表示する
    :cp
    # Quickfixを閉じる
    :ccl
    # もっと知るには
    :help quick-window
   ```
5. 便利な表現
   - ディレクトリ内のすべてのファイルを検索
    `:vim あ ot-backend/**`

>## PowerShelでvimを扱えるようにする(win)
[powershell+vim](https://qiita.com/shuhoyo/items/d9966e12976275f20c24)

>## 操作方法メモ
1. `gg`: 一番上へ ←→ `shift + g`
2. 全選択
   - vi {ファイル名}でファイルを開く
   - 「gg」でファイルの先頭にいく
   - vを押してvisualモードにする
   - 「shift」 +「g」 でファイルの最後尾にいく
   
>## 便利な拡張機能
1. easymotion
  - `space*2 + s` + `飛びたい文字`でその場所までカーソル移動
  - `space*2 + w`で飛ぶ候補をハイライト
  - space: `leader`(設定)

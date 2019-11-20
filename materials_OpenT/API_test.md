# API試験
1. `Postman`使う
2. `POST`メソッドでAPIにkey,value投げるとStepFunctionにより下記パラメタが発行される
`numberOfPackets`: 証明書の数, Step Functions発行のやつと数が一致しているか確認すること
`processingKey`: 処理識別ID
3. `端末情報(terminals)`のところだけでok

>## URLの送り方
1. クエリは`params`のところに記載(VALUEも入れる！)
2. 送信する中身は`body`に記載(JSON形式)
3. `processingKey`にS3のバケットから既知のものを選んで入れる
   - `numberOfPackets`はS3上そのディレクトリ内にあるファイルの個数

[流れ]
- ParamsにS3にある`processingKey`と`numberOfPackets`の値を入力する
- Bodyに端末情報を入力する
- 送信する
- URLのクエリに載った上記の値とS3のバケット内を照会し、`processingKey`が一致しているディレクトリ内の証明書をカウントし、その数と`numberOfPackets`の値を比較する
  - 数が一致していたら`200 OK`
  - 数が不一致だったらレスポンスエラー発生

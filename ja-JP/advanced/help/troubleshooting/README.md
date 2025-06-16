# エラーが出た時・困った時は

エラーが発生した場合、[フォーラム](https://community.anytype.io/)での質問や[サポート](mailto:support@anytype.io)への連絡の前に、まず以下の手順をお試しください。

1.  お使いのコンピューターの時刻が正確であることを確認する。（2時間以上のずれは接続エラーの原因となります）
2.  プロキシ、VPN、ファイアウォール、または社内ネットワークを利用している場合は、一時的に無効にして接続を試す。
3.  可能であれば、社内ネットワークなど以外から接続する。
4.  スマートフォンのテザリング機能を使って接続する。
5.  別のデバイスや、普段と違うネットワーク環境からログインを試す。
6.  **画面表示に関する問題の場合：** `~/.config/anytype` 内にある `GPUCache` フォルダーを削除すると改善されることがあります。

For more specific issues:

<details>

<summary>モバイル版のログイン画面で動作が停止した場合に、StackGoroutinesログの共有方法</summary>

1.  ログイン画面で動作が停止した場合、[「保管庫にログイン（Enter My Vault）」の文字部分を5回タップ](https://drive.google.com/file/d/1V4muGfFDNDb98ZVp213-YmbnVv3Vx_tX/view?usp=drive_link)してください。
2.  Rpc.Debug.StackGoroutinesコマンドが成功すると、デバッグ用のログファイルが生成されます。
3.  生成されたログファイルを、ご都合の良い方法でサポートチームに共有してください。

</details>

<details>

<summary>ストレージ使用量が正しく表示されない場合の対処法</summary>

デスクトップアプリ上部のメニューバーから`デバッグ > 競合データの解消（Debug > Reconcile）`の順に選択し、その後アプリを再起動してください。


</details>

<details>

<summary>メンバーシップ購入後にANY名の選択画面が表示されない場合</summary>

お使いのブラウザ、またはAnytypeアプリ内の検索画面に`anytype://main/membership`と入力して実行した後、アプリを再起動してください。

</details>

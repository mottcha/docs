# AnySync Netcheck（同期接続診断ツール）

Anytypeノードへ正しく接続できるかを確認するためのシンプルなツールです。
主に、ネットワーク接続や同期（TLS）に関する問題を診断するために使用します。

コーディネーターノードとの通信を試み、ネットワーク設定が正常に行えるか（libp2pプロトコルやAnysyncハンドシェイク）を確認します。

***

### ダウンロード <a href="#p-42130-download-2" id="p-42130-download-2"></a>

以下のリンクから、お使いのOSに対応したバージョンをダウンロードできます。

{% embed url="https://github.com/anyproto/any-sync-tools/releases" %}

ダウンロードした.zipファイルにはすべてのツールが含まれていますが、同期チェックの手順で必要なのは**“any-sync-netcheck”**のみです。
（もう一方のファイルは、[セルフホスト用のツール](https://github.com/anyproto/any-sync-tools/blob/main/any-sync-network/README.md)です。）

### インストール <a href="#p-42130-installation-3" id="p-42130-installation-3"></a>

**ソースからのビルド：**

`go install github.com/anyproto/any-sync-tools/any-sync-netcheck@latest`

***

#### ツールの実行 <a href="#p-42130-runing-the-tool-5" id="p-42130-runing-the-tool-5"></a>

以下のコマンドでツールを実行します。

* `any-sync-netcheck`
* または、詳細な情報を出力する場合は `any-sync-netcheck -v` を使用します。

***

#### 実行結果 <a href="#p-42130-result-6" id="p-42130-result-6"></a>

* **同期が正常な場合**、出力ログは以下のようになります。

    <figure><img src="../../../../.gitbook/assets/Screenshot 2023-08-02 at 16.40.02.png" alt="正常な場合のログ出力例"></figure>
* **エラーが検出された場合**は、お使いのネットワーク環境（VPN、プロキシ、ファイアウォール、アンチウイルスソフトの有無など）の詳細情報をご準備ください。後ほど、より詳細な調査のために、トレースルートなどの追加情報をお願いする場合があります。

***

#### Anyteamへの報告 <a href="#p-42130-send-to-anyteam-7" id="p-42130-send-to-anyteam-7"></a>

出力されたログとネットワーク環境の情報を[support@anytype.io](mailto:support@anytype.io)までお送りください。

***
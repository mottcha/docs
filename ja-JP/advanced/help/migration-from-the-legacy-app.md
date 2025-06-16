---
description: アルファ版テスター向けの移行手順
---

# ベータ版への移行

#### **移行方法**

旧バージョン（アルファ版/レガシー版、0.31.*以前）で作成したコンテンツを引き続き利用するには、以下の手順でデータを移行する必要があります。

1.  お使いの旧バージョンのアプリを、アプリ内（Anytype > Check for updates）または[こちらのリンク](https://download.anytype.io/?ref=migration\&platform=desktop)から最新版（0.31.9）にアップデートします。
    <div align="left"><figure><img src="../../../.gitbook/assets/Check updates.png" alt="アップデートを確認" width="331"><figcaption></figcaption></figure></div>
2.  アップデートした旧バージョンから、データをエクスポートします。（File > Export > Protobuf）
    <div align="left"><figure><img src="../../../.gitbook/assets/Anytype Export.gif" alt="データのエクスポート" width="336"><figcaption></figcaption></figure></div>
3.  新しいベータ版アプリを[ダウンロード](https://download.anytype.io/)し、インストールして開きます。
4.  ベータ版アプリに、先ほどエクスポートしたバックアップデータをインポートします。

より詳細な情報は、コミュニティの[移行ガイド](https://community.anytype.io/t/anytype-legacy-to-beta-migration-trail-guide/9274)もご確認ください。

#### **最新の旧バージョン（Alpha版）のダウンロード**

データをエクスポートする前に旧アプリを削除してしまった場合は、[こちらのリンク](https://download.anytype.io/?ref=migration\&platform=desktop)から、エクスポートに必要なバージョン（0.31.9）を再度ダウンロードできます（Mac, Windows, Linux対応）。


#### How can I skip the import backup step?

Instead of migrating, you’ll have the following alternatives:

*   Create a new vault. When the app is launched, pick up Join instead of Login.

    <div align="left"><figure><img src="../../../.gitbook/assets/Join Anytype.png" alt="" width="354"><figcaption></figcaption></figure></div>
* Manually import selected Objects one by one from Legacy to Beta. You may want to do this if your Legacy vault / account has become messy but you have a few projects you’d like to carry over to Beta.

For these options, you’ll need to create a new vault, which will generate a new Key.

#### Troubleshooting

* Error "open profile: file does not exist"
  * Reason: this happens with old Legacy versions (e.g. 0.31.0).
  * Solution: update the Legacy app via the instructions above.
* Error "can't run service 'client.clientspace': EOF" \*

#### バックアップのインポートをスキップする方法

データを一括で移行する代わりに、以下の選択肢もあります。

* **新しい保管庫で始める**：アプリの起動時に「すでに鍵を持っている」ではなく「初めて利用する」を選択します。これで、新しい保管庫と鍵が作成され、新しいユーザーとして始められます。
    <div align="left"><figure><img src="../../../.gitbook/assets/Join Anytype.png" alt="Join Anytype" width="354"><figcaption></figcaption></figure></div>
* **必要なオブジェクトだけを手動で移行する**：新しい保管庫と鍵が作成し、必要なオブジェクトだけ移行します。旧バージョンの保管庫が散らかっていて、一部だけ移行したい場合に有効です。

#### トラブルシューティング

* **エラー： "open profile: file does not exist"**
    * **原因：** 旧バージョン（Alpha版）のアプリが古いために発生します (例: 0.31.0)。
    * **解決策：** 前のセクションの指示に従い、旧アプリを最新版にアップデートしてください。
* **エラー： "can't run service 'client.clientspace': EOF"**
# よくある質問

## 全般

<details>

<summary>OSのキー管理機能から自分の「鍵」を復元するには？</summary>

#### Macの場合

Macをお使いの場合、Anytypeの鍵は、OS標準の「キーチェーンアクセス」アプリに自動で保存されます。他の場所に保存されることはありません。

お使いのMacの設定でiCloudキーチェーンを有効にしている場合は、iCloudにも鍵がバックアップされます。詳しくは[Appleのサポートページ](https://support.apple.com/ja-jp/109016)をご覧ください。

この仕組みは、万が一、鍵を紛失してしまった場合に備えた安全策です。将来的には他の選択肢も検討していますが、現時点ではこの方法で採用しています。

Macで鍵を使ってログインした場合、以下の手順で鍵を確認できます。

1.  DockからFinderを開きます。
2.  「アプリケーション」フォルダを開き、次に「ユーティリティ」フォルダを開きます。
3.  「キーチェーンアクセス」アプリを起動します。
4.  サイドバーの「デフォルトキーチェーン」から「ログイン」を選択します。
5.  Anytypeに関連する項目を探し、開きます。
6.  「パスワードを表示」のチェックを入れると、鍵が表示されます。

#### Windowsの場合

Windowsをご利用の場合、あなたの鍵はOS標準の「[資格情報マネージャー](https://support.microsoft.com/ja-jp/windows/windows-%E3%81%AE%E8%B3%87%E6%A0%BC%E6%83%85%E5%A0%B1%E3%83%9E%E3%83%8D%E3%83%BC%E3%82%B8%E3%83%A3%E3%83%BC-1b5c916a-6a16-889f-8581-fc16e8165ac0)」に保存されています。

ただし、システムの状況によっては資格情報マネージャーに鍵の「表示」ボタンがなく、直接確認できないことがあります。その場合は、[こちら](https://gist.github.com/requilence/de8da32adc44d4786559789debb3bf88)のPowerShellスクリプトを試してみてください。エクスプローラーで右クリックし、「PowerShellで実行」で実行できます。

#### Linuxの場合

お使いのLinux環境で[GNOMEキーリング](https://wiki.gnome.org/Projects/GnomeKeyring/)をご利用の場合、[Seahorse](https://wiki.gnome.org/Apps/Seahorse/)を使用して鍵を見つけることができます。

</details>

<details>

<summary>保管庫の鍵はどのような仕組みで生成されるのですか？</summary>

Anytypeでは、[**BIP39**](https://medium.com/coinmonks/mnemonic-generation-bip39-simply-explained-e9ac18db9477)という広く利用されている標準規格を採用しています。鍵からあなた専用の秘密鍵が作られます。

</details>

<details>

<summary>Anytypeを使う上での最小要件は？</summary>

* **デスクトップ版（Windows, macOS, Linux）**\
    Electronで開発されており、その動作環境は[Google Chrome](https://support.google.com/chrome/a/answer/7100626?hl=ja)に準じます。\
    現時点では以下の環境が必要です。
    * **Windows**：Windows 10 以降
    * **macOS**：macOS 10.15 (Catalina) 以降
    * **Linux**：64-bit版のUbuntu 18.04、Debian 10、openSUSE 15.5、Fedora 38、またはそれ以降のバージョン
* **Android版**\
    Google Playストアからインストールする場合、Android 8.0 以降を搭載し、RAMが4GB以上ある64-bit対応デバイスが必要です。
* **iOS版**\
    iOS 16 以降がインストールされたデバイスが必要です。

</details>

<details>

<summary>Anytypeはどこにインストールされますか？</summary>

* **Windows** (10以降) では、通常以下の場所にあります。\
    `C:\Users\<ユーザー名>\Appdata\Local\Programs\anytype`\
    `<ユーザー名>`の部分は、お使いのPCのユーザー名に置き換えてください。
* **macOS** の場合：\
    `HDD > Users > <ユーザー名> > Library > Application Support > anytype`
* **Linux** の場合、作業ディレクトリは以下の場所にあります。\
    `~/.config/anytype`
* **Android** の場合、デフォルトの場所にインストールされます。\
    キャッシュ用のフォルダ：`device/data/data/io.anytype.app`\
    Androidデバイスでは、Anytypeのディレクトリは保護された領域に保存されるため、ユーザーが直接アクセスすることはできません。
* **iOS** の場合、iOSの標準パスにインストールされます。

</details>

<details>

<summary>ローカルモードでも外部ネットワークに通信されるのですか？</summary>

Anytypeネットワークへの通信は一切行われないことを保証します。ただ、利用状況に関するデータは引き続き送信されます。将来的には、利用状況の収集をオフにできる機能の導入を予定しています。

ただし、一部外部サービスと連携する機能（埋め込みブロック、ブックマーク情報の取得など）を利用する際には、そのサービスへの通信が必要です。

</details>

<details>

<summary>Linux版で、起動のたびに鍵の入力を求められるのはどうにかならないの？</summary>

お使いのLinux環境によっては、Anytypeを起動するたびに鍵の入力を求められることがあります。これは、入力した鍵を安全に保存するための「キーチェーン」という仕組みがシステムにない場合に発生します。

この問題を解決するには、以下の2点をご確認ください。

1.  **キーチェーンをインストールする**
    [GNOMEキーリング](https://wiki.gnome.org/Projects/GnomeKeyring)などのキーチェーン用ソフトウェアをインストールしてください。これにより、一度入力した鍵が安全に保存され、次回の起動時から入力が不要になります。

2.  **必要なソフトウェアを確認する**
    Anytypeの動作に必要となる[依存関係（ライブラリ）](https://github.com/anyproto/anytype-ts#dependencies)が、お使いのシステムにすべてインストールされているか、あらかじめご確認ください。

</details>

<details>

<summary>Anytypeにブラウザ版はないんですか？</summary>

Anytypeはブラウザ版は提供しておりません。デスクトップ版およびモバイル版の専用アプリ（スタンドアロンソフトウェア）として提供しています。

ブラウザ版では、ブラウザ固有の脆弱性の影響を受けてしまうため、最も重要な徹底したデータの安全性と暗号化という理念を損なう可能性があるためです。

</details>

<details>

<summary>アルファ版にあったホームページ機能はもうないんですか？</summary>

<img src="../../../../.gitbook/assets/w=3840,quality=80 (1).webp" alt="" data-size="original">


アルファ版で提供されていたホームページ機能は、新しいサイドバーとウィジェット機能の導入に伴い、廃止されました。

以前のホームページ機能のようなレイアウトを再現したい場合、以下の2つの方法があります。

1.  クエリ機能とギャラリービュー表示を組み合わせる。
2.  [旧ホームページを再現したテンプレート](https://gallery.any.coop/Made%20by%20Any?experience=legacy_homepage)を試す。

</details>

<details>

<summary>保管庫を切り替えて使う方法はありますか？</summary>

デスクトップ版であれば、特殊な方法ですが可能です。

まず、別の保管庫用のショートカットを作成します。そして、そのショートカットの起動コマンドに`--user-data-dir="$path"`というフラグを追加してください。

（例：`--user-data-dir="D:\Anytype"`）

</details>

<details>

<summary>ChromebookにAnytypeをインストールできますか？</summary>

はい、可能です。ChromebookでAnytypeをインストールする方法はいくつかあります。

一番簡単な方法は、[AppImage版](https://download.anytype.io)をダウンロードして利用することです。より詳しい手順や、その他のインストール方法については、コミュニティの[こちらの投稿](https://community.anytype.io/t/guide-to-use-anytype-on-a-chromebook/12181)をご覧ください。

</details>

<details>

<summary>脆弱性報奨金制度（bug bounty program）はありますか？</summary>

Anytypeは非営利団体として運営されており、まだ財政的に安定していないため、常設の脆弱性報奨金制度はご用意できていないのが現状です。

その一方で、セキュリティは私たちにとって最重要事項です。もし私たちのアプリに重大な脆弱性を発見され、その詳細を非公開でご報告いただける場合は、謝礼についてぜひご相談させていただきたいと考えております。詳しい報告手順については、GitHubの[セキュリティポリシー](https://github.com/anyproto/.github/blob/main/docs/SECURITY.md)をご覧ください。

</details>

<details>

<summary>ブラウザからAnytypeのリンクが開けません</summary>

ブラウザからAnytypeリンクを開けない場合は、Anytypeアプリ内で直接リンクを開くことができます。

開きたいリンクをコピーし、アプリ内の検索ウィンドウにペーストして、Enterキーを押してください。これで、リンクされたページへ直接移動します。

</details>

<details>

<summary>GLIBCXXエラーが表示された</summary>

GLIBCXXに関するエラーが発生した場合は、以下のいずれかの方法をお試しください。

* Anytypeの[最新バージョン](https://download.anytype.io/)をインストールする
* [こちらのコミュニティスレッド](https://community.anytype.io/t/update-45-1-unable-to-launch/26723/4?u=filip)で解決策を確認する
* (非公式の)[Flatpak版](https://flathub.org/apps/io.anytype.anytype)を試す

</details>

<details>

<summary>どうやったら段組み（ブロックを横に並べることが）できますか？</summary>

各ブロックの左端にある縦長の「⋮」ボタンを掴んで、別のブロックの横まで持っていき、掴んだブロックをドロップしてみてください。これで段組みできるはずです。

また、同じようにブロックを入れ子にする（親子関係にする）こともできます。

<div><figure><img src="../../../../.gitbook/assets/image (70).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../../../.gitbook/assets/image (71).png" alt=""><figcaption></figcaption></figure></div>

</details>

<details>

<summary>iOSではオブジェクト内検索できないのでしょうか？</summary>

申し訳ありません。現在、iOS版Anytypeではオブジェクト内検索に対応しておりません。

</details>

<details>

<summary>モバイル版ではクエリ内の検索や一括選択はできないのでしょうか？</summary>

申し訳ありません。現在、iOS版およびAndroid版のAnytypeアプリでは、クエリ内での検索や、オブジェクトの一括選択に対応しておりません。

</details>

<details>

<summary>自分の保管庫にだけマイスペースがあるのはなぜですか？</summary>

マイスペースは、バージョン0.44.0より前に作られた保管庫に存在するスペースです。

このスペースが不要な場合は、自由に削除していただいて構いません。データを別のスペースに移行したい場合は、[インポート・エクスポート機能](../../data-and-security/import-export/ "mention")をご利用ください。

</details>

## 共同編集

<details>

<summary>共有スペースにするには、どうしたらいいですか？</summary>

![](<../../../../.gitbook/assets/Space Settings_Shared Space Creation.png>)

新しく作成したスペースは、初期設定では _非公開_ スペースになっています。

他のユーザーと共同編集するには、スペース設定から「メンバーを招待する」を開き、招待リンクを作成します。これにより、_共有_ スペースに切り替わり、ユーザーを招待できるようになります。

</details>

<details>

<summary>共有スペースのアクセス権限について</summary>

共有スペースのメンバーには、以下の3種類のアクセス権限（役割）を設定できます。

* **スペース所有者**
  * スペースの作成者です。
  * スペース内のオブジェクト、スペース名、設定のすべてを変更できます。
  * メンバーの追加・削除ができる唯一の権限です。

* **編集権限**
  * スペース内のすべてのオブジェクトを編集できます。
  * スペース名を変更できます。

* **閲覧権限**
  * スペース内のすべてのコンテンツを閲覧できますが、編集はできません。

</details>

<details>

<summary>どうやってスペースに他の人を招待できますか？</summary>

![](<../../../../.gitbook/assets/Anytype Space Sharing_Invite Link.png>)

スペース所有者は、以下の手順でメンバーを招待、管理できます。

1.  **招待リンクの作成**: スペース設定を開き、「メンバーを招待する」に行き、招待リンクを作成します。
2.  **招待リンクの共有**: 作成した招待リンクを、招待したい相手に伝えます。
3.  **参加リクエストの確認**: 招待リンクを受け取った人は参加リクエストを送信できます。送信されると、あなたに通知が届きます。
4.  **承認と権限設定**: 参加リクエストを承認または拒否します。承認する場合、そのメンバーの権限を「編集許可」または「閲覧許可」から選択して設定します。

</details>

<details>

<summary>招待リンクの仕組みについて</summary>

共有した招待リンクは、招待相手の状況に応じて、最適な案内を自動的に行います。

**すでにAnytypeをインストールしている場合は、**
招待リンクを開くと、アプリ内で参加リクエストを送信するかの確認画面が表示されます。参加リクエストが送信されると、スペース所有者に通知が届きます。このとき、プロフィールを見て、適切な相手かどうか判断します。

**まだAnytypeを使っていない場合は、**
招待リンクを開くと、インストール手順が記載された専用のダウンロードページが表示されます。インストール後、もう一度招待リンクを開く必要があります。その後、表示された画面から参加リクエストを送信できます。

</details>

<details>

<summary>スペースに招待できる人数について</summary>

共有スペースに招待できる人数は、ご利用のプランによって異なります。

Explorersプランでは、1つの共有スペースにつき最大2名まで編集権限のメンバーを招待できます。

BuildersおよびCo-creatorsプランでは、最大9名まで編集権限のメンバーを招待でき、閲覧権限のメンバーは無制限に招待することが可能です。

</details>

<details>

<summary>ローカルモードのまま共同編集はできますか？</summary>

例外的なケースを除いて、難しいです。

共有スペースの内容をメンバー間で同期する必要があるため、Anytypeネットワークの接続が必要です。

ただし、参加しているメンバー全員が同じローカルネットワークに接続しているのであれば、例外的に可能です。

</details>

### メンバーシップ

<details>

<summary>メンバーシップを更新しなかった場合、共有スペースはどうなりますか？</summary>

メンバーシップの更新は、次回の更新日より前であれば「いつでも停止」できます。お手続きは、お支払いに利用された決済プロバイダー（Stripe、App Store、Google Playなど）のサイトにて行ってください。

**あなたのANY名**

メンバーシップの初回購入から1年または3年（プランによります）が経過すると、ANY名は解放され、他の人が取得できるようになります。

**共有スペース**

メンバー全員（あなたを含む）にスペースを「削除」または「エクスポート」するか尋ねる通知画面が表示されます。データを残すには、各メンバーが各自でデータをエクスポートし、新しいスペースとしてインポートし直す必要があります。ただし、新しいスペースでは、他のメンバーとの同期は行われません。

**データの削除について**

Anytypeのバックアップノードに保存されていたデータは、30日後に削除されます。

</details>

<details>

<summary>利用可能なお支払い方法について</summary>

お支払いには、主要な各種クレジットカードをご利用いただけます。

デスクトップ版からメンバーシップをご契約される場合、価格は米ドル（USD）で設定されています。お支払い時に、決済サービス（Stripe）の換算レートを用いて、お客様の現地通貨に換算された金額が請求されます。

iOSまたはAndroidアプリからご契約される場合、お支払いはApp StoreまたはPlayストアによって行われます。価格は、各プラットフォームに準じて、お客様の現地通貨で表示、決済されます。

</details>

<details>

<summary>招待できるメンバーをさらに増やすことはできますか？</summary>

現在、法人および教育機関向けに新しいメンバーシッププランを準備しています。1つのスペースに最大20名まで編集権限のメンバーを追加できるようになる予定です。

</details>

<details>

<summary>ストレージや同期の上限に達すると、データはどうなりますか？</summary>

Anytypeのバックアップノードを介した同期が停止します。データはデバイス内での保存され、ローカルネットワークを通した同期のみが有効な状態になります。

</details>

<details>

<summary>返金のお手続きについて</summary>

返金をご希望の場合は、お支払いから5日以内に[support@anytype.io](mailto:support@anytype.io)までメールでご連絡ください。

ネットワークのANY名登録費用は払い戻しされないため、返金できるのはメンバーシップ料金の25%のみとなります。あらかじめご了承ください。

</details>

<details>

<summary>学生・教育機関向けの割引はありますか？</summary>

はい、提供しております。大学などの教育機関から発行されたメールアドレスを使用して[membership-upgrade@anytype.io](mailto:membership-upgrade@anytype.io)までご連絡いただいた方には、メンバーシップ料金の50%割引を提供しております。

</details>

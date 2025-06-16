# インポートとエクスポート

{% hint style="warning" %}
この機能は、デスクトップ版のみ対応しています。
{% endhint %}

スペースのインポート、エクスポートは、以下の3つの方法から行えます。

1. メニューバーの**Anytype > 設定 > スペースにインポート / スペースをエクスポート**から
<figure><img src="../../../../.gitbook/assets/image (83) (1).png" alt="" width="375"><figcaption></figcaption></figure>

2. [スペース設定](../../../advanced/settings/space-settings.md#integrations)の連携画面から
<figure><img src="../../../../.gitbook/assets/image (106).png" alt=""><figcaption></figcaption></figure>

3. 検索メニューで「インポート」または「エクスポート」と入力して、機能を直接呼び出す

### インポート

現在、以下のファイル形式のインポートに対応しています。

* **MD (マークダウン):** `.md`ファイル単体、または複数のMarkdownファイルを含むzipファイル。※現時点ではプロパティはインポートには対応していません。
* **HTML**
* **TXT**
* **CSV:** 列名を「電話」「Eメール」のような既存のプロパティ名と同じにすることで、データを自動的に取り込むことができます。
* **Any-Block**:
    * **Protobuf**
    * **JSON**

インポートが完了すると、サイドバーのお気に入りウィジェットに新しいコレクションが作成されます。その中にインポートされたすべてのオブジェクトがまとめられます。

<figure><img src="../../../../.gitbook/assets/image (2) (1).png" alt="" width="324"><figcaption></figcaption></figure>

また、インポートしたファイルの中から、どのオブジェクトを「お気に入り」に追加するかを尋ねられます。

<figure><img src="../../../../.gitbook/assets/image (93).png" alt="" width="375"><figcaption></figcaption></figure>

### エクスポート

現在、以下の形式のエクスポートに対応しています。

* **Markdown**
* **Any-Block** (ProtobufとJSONの両方)
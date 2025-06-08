# カスタムCSS

この記事は、[LavaC](https://community.anytype.io/u/LavaC)氏がコミュニティフォーラムに投稿した内容を元にしてます。

{% embed url="https://community.anytype.io/t/tutorial-of-custom-css/14234" %}

この記事の内容やCSSの記述についてご不明な点があれば、お気軽に上記の投稿でご質問ください。

### カスタムCSSの有効化と場所 <a href="#where-1" id="where-1"></a>

カスタムCSSを有効にするには、`メニュー > ファイル > カスタムCSSの適用` をオンにします。

<figure><img src="../../../.gitbook/assets/image (5) (1).png" alt=""><figcaption></figcaption></figure>

カスタムCSSのファイルを編集するには、`メニュー > ファイル > 開く > カスタムCSS` をクリックします。

<figure><img src="../../../.gitbook/assets/image (4) (1).png" alt="" width="375"><figcaption></figcaption></figure>

### 手順 <a href="#how-2" id="how-2"></a>

まず初めに、この記事はCSSに慣れていない初心者の方を対象としています。そのため、CSSの知識がある方は、ご自身のレベルに合わせて必要な箇所のみお読みください。

#### テーマカラーを変更する <a href="#theme-color-3" id="theme-color-3"></a>

ソフトウェアを開発する際、まず、配色のベースとなるスタイル変数の設定から始まります。同様に、独自のスタイルに変更したい場合も、スタイル変数の値を変更することから始めるのが一般的です。

これらの変数は通常 `:root` セレクタの下にあり、開発者ツールで確認できます。

<figure><img src="https://community-static.anytype.io/optimized/2X/8/8c798a22e6bddd7bd190043a2ec7c226fcf5cf24_2_690x408.png" alt=""><figcaption></figcaption></figure>

例えば、`--color-text-primary` は最も暗い黒色のテキストカラー変数のようなので、custom.cssファイルに以下のように記述します。

<figure><img src="https://community-static.anytype.io/original/2X/b/bbefbe5a417032384cde12b1e80e4b2f480ded68.png" alt=""><figcaption></figcaption></figure>

そして、内容を保存し、`(Command/Ctrl) + r`を押してAnytypeをリフレッシュします。

> もちろん、開発者ツールで直接変更して効果を確認することもできます。

そうすると、先ほど記述した赤色がデフォルトの値を上書きし、テキストがすべて赤色になっているはずです。

<figure><img src="https://community-static.anytype.io/optimized/2X/0/0e16feda708cfeee241bc7128caa3f802a09c66d_2_690x384.png" alt=""><figcaption></figcaption></figure>

以下は、[Solarized](https://en.wikipedia.org/wiki/Solarized)を参考に私が修正したcustom.cssの一部です。これは実は穴埋め問題のようなもので、これらの変数を変更してみて、どこに影響が出るかを確認することで、次に何を修正すればよいかがわかります。

<figure><img src="https://community-static.anytype.io/optimized/2X/0/0a67ca485d41ba2d1e72dd5b30b5cae7f489f82e_2_690x394.jpeg" alt=""><figcaption></figcaption></figure>

```css
:root {
    --color-text-primary: #002b36;
    --color-text-secondary:	#586e75;
    --color-text-tertiary: 	#839496;
    --color-text-inversion: #eee8d5;
    --color-shape-primary: 	#586e75;
    --color-shape-secondary: 	#eee8d5;
    --color-shape-tertiary: 	#eee8d5;
    --color-shape-highlight-medium: rgba(79, 79, 79, 0.08);
    --color-shape-highlight-light: rgba(79, 79, 79, 0.04);
    --color-control-accent: #252525;
    --color-control-active: #b6b6b6;
    --color-control-inactive: #dcdcdc;
    --color-control-bg: #fff;
    --color-bg-primary: #fdf6e3;
    --color-bg-loader: rgba(255,255,255,0.7);
    --color-system-accent-100: #ffb522;
    --color-system-accent-50: #ffd15b;
    --color-system-accent-25: #ffee94;
    --color-system-selection: rgba(24, 163, 241, 0.15);
    --color-system-drop-zone: rgba(255, 187, 44, 0.25);
    --color-yellow: #ecd91b;
    --color-orange: #ffb522;
    --color-red: #f55522;
    --color-pink: #e51ca0;
    --color-purple: #ab50cc;
    --color-blue: #3e58eb;
    --color-ice: #2aa7ee;
    --color-teal: #0fc8ba;
    --color-lime: #5dd400;
    --color-green: #66B395;
}
```

#### フォント <a href="#fonts-4" id="fonts-4"></a>

CSSでフォントに関連する属性は、[font-family](https://developer.mozilla.org/ja/docs/Web/CSS/font-family)と呼ばれます。すべてのテキストに同じフォントが適用されるように、通常は `body` タグにスタイルを設定します。

```css
body {
    font-family: "霞鹜文楷", "jetBrainsMono";
}
```

もちろん、これが有効になる前提として、お使いのコンピュータにそのフォントがインストールされている必要があります。もしインストールされていない場合は、コンピュータにフォントをインストールするか、外部フォントをインポートすることもできます。

{% hint style="info" %}

{% endhint %}

<details>

<summary>外部フォントをインポートする</summary>

[<img src="https://community-static.anytype.io/optimized/2X/d/d1348ecf28fafeb4c079d5cd9ba343b30ee6f9d2_2_690x494.png" alt="image" data-size="original">](https://community-static.anytype.io/original/2X/d/d1348ecf28fafeb4c079d5cd9ba343b30ee6f9d2.png)\
[![image](https://community-static.anytype.io/optimized/2X/a/aaf23f71f95b30839021c2489a9153cc46f2b8be_2_690x271.png)](https://community-static.anytype.io/original/2X/a/aaf23f71f95b30839021c2489a9153cc46f2b8be.png)\
[![image](https://community-static.anytype.io/optimized/2X/d/d29da78fce6ac4d052c0b030fd322fab4fef2a1a_2_690x458.png)](https://community-static.anytype.io/original/2X/d/d29da78fce6ac4d052c0b030fd322fab4fef2a1a.png)\
[![image](https://community-static.anytype.io/optimized/2X/8/87c8c15932c29ee8bd91d58928d2958209db39e3_2_690x107.png)](https://community-static.anytype.io/original/2X/8/87c8c15932c29ee8bd91d58928d2958209db39e3.png)\
[![image](https://community-static.anytype.io/optimized/2X/6/690391b23293397bb0844789dee9d500300a3028_2_690x435.png)](https://community-static.anytype.io/original/2X/6/690391b23293397bb0844789dee9d500300a3028.png)

</details>

#### ダークモード <a href="#dark-mode-5" id="dark-mode-5"></a>

ダークモードのスタイルは `html.themeDark` で囲む必要があります。

```css
/* デフォルトはライトモードに適用されます */
.blocks {
    .block.blockText.textCallout>.wrapContent{
        border-radius: 30px;
    }
}

html.themeDark {
    /* ダークモードに適用されます */
    --color-text-primary: red;
    .blocks {
        .block.blockText.textCallout>.wrapContent{
            border-radius: 2px;
        }
    }
}

```

#### その他の要素 <a href="#other-elements-6" id="other-elements-6"></a>

特定の要素を修正したい場合は、左上の開発者ツール機能を使用し、修正したい要素を選択すると、**Styles**列に関連するスタイルが表示されます。

<figure><img src="https://community-static.anytype.io/optimized/2X/3/3d111c1232f10345c8584f5a2cf15ec36cba8864_2_690x460.png" alt=""><figcaption></figcaption></figure>

内部の値を直接変更して、どう効果が現れるか試すことができます。

<figure><img src="https://community-static.anytype.io/optimized/2X/6/6ec5d48153fd5abfd34274a2c9cfb736de865a14_2_690x283.png" alt=""><figcaption></figcaption></figure>

納得できる内容になったら、その内容をすべてcustom.cssスタイルシートにコピーして保存します。

<figure><img src="https://community-static.anytype.io/original/2X/8/8c83f1c7406a1a651cac26da10c6429bd59f2dcb.png" alt=""><figcaption></figcaption></figure>

#### アイコンの変更 <a href="#change-icons-7" id="change-icons-7"></a>

AnytypeのアイコンはSVGを使用して実装されています。

<details>

<summary>リレーションアイコンの例</summary>

[<img src="https://community-static.anytype.io/optimized/2X/6/6d596177b0b332db51cd793630c415891538f8f7_2_672x500.png" alt="image" data-size="original">](https://community-static.anytype.io/original/2X/6/6d596177b0b332db51cd793630c415891538f8f7.png)

`data:image/svg...`で始まるテキストは、SVGをBase64に変換したデータです。

[このウェブサイト](https://base64.guru/converter/decode/image/svg)からSVG画像にデコードすることができます。
</details>

独自のアイコンをカスタマイズしたい場合は、SVGをBase64形式に変換する必要があります。変換は、[このウェブサイト](https://base64.guru/converter/encode/image/svg)から行えます。

SVGアイコンは、個人的には[このウェブサイト](https://pictogrammers.com/libraries/)がおすすめです。

> あまり複雑すぎるSVGは選ばないようにしてください。変換後のBase64のテキストがその分、長くなりすぎてしまいます。

変換したBase64テキストを取得して置き換えると、置き換え作業は完了です。

```css
.header .icon.relation {
  background-image: url(data:image/svg+xml;base64,PD94bWwgdmVyc2lvb......);
}
```

![image](https://community-static.anytype.io/original/2X/3/30b788e54c7daa2db54352ca4ff721ecc6d2e027.png)

**少し複雑ですが、元のアイコンのまま、色だけ変えることもできます。**

```css
.header .icon.relation {
  // このurlの部分は、変更したいアイコンの`background-image`属性の内容をそのまま持ってきたものです。
  mask-image: url(data:image/svg+xml;base64,.......);
  mask-repeat: no-repeat;
  background: red; // 好きな色
}
```

Photoshopのマスク機能をご存知であれば、それに似たようなことをしています。ただし、仕上がりはPhotoshopほど滑らかではないです。


<figure><img src="https://community-static.anytype.io/original/2X/7/72dbdcf71ef643f5873aa7ea1ea814bf282dfec5.png" alt=""><figcaption></figcaption></figure>

### その他の例

{% embed url="https://community.anytype.io/t/anytype-mist-light-dark-a-brand-new-anytype-theme/16329" %}



# AdType (enum)

AdTypeは、広告タイプを表します。なお、選択した配信先デバイスにより、指定可能な広告の文字数は異なる場合があります。

#### Service

+ [AdGroupAdService](../../services/AdGroupAdService.md)

#### Namespace

[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

| Enumeration  |       Type       |          Description          |
| ------------ | ---------------- | ----------------------------- |
| TEXT_LONG_AD1 | xsd:string | 「タイトル15文字、説明文19文字-19文字」のテキスト広告です。PC、スマートフォン・タブレット端末の場合にご利用いただけます。（推奨） |
| TEXT_LONG_AD2 | xsd:string | 「タイトル15文字、説明文33文字」のテキスト広告です。<br/>PC、スマートフォン・タブレット端末の場合にご利用頂けます。 |
| TEXT_SHORT_AD1 | xsd:string | 「タイトル12文字、説明文12文字」のショートテキスト広告です。<br/>モバイルの場合にご利用いただけます。<br/>※現在、こちらの広告タイプでは入稿できません。 |
| TEXT_SHORT_AD2 | xsd:string | 「タイトル14文字、説明文19文字」のショートテキスト広告です。<br/>モバイルの場合にご利用いただけます。<br/>※現在、こちらの広告タイプでは入稿できません。 |
| POS_AD | xsd:string | 「説明文33文字」の掲載位置指定テキストです。 |
| RESPONSIVE_IMAGE_AD | xsd:string | 配信される広告表示枠の形に合わせて画像のサイズ変更およびトリミングが行われるレスポンシブ広告です。 |
| STATIC_FRAME_AD | xsd:string | 配信される広告表示枠の形に合わせて3種類のレイアウトが利用可能な広告枠サイズ固定広告です。<br/>※レイアウトの仕様につきましては<a href="/yahoojp-marketing/ydn-api-documents/blob/master/docs/ja/api_reference/data/AdGroupAd/AdLayout.md">AdLayout</a>を参照して下さい。 |
| RESPONSIVE_VIDEO_AD | xsd:string | 入稿内容（テキスト、動画、ボタンなど）の構成要素を組み合わせ、多様なデバイスや広告掲載面に対応したクリエイティブを表示できる広告です。 |
| DYNAMIC_AD | xsd:string | ウェブサイトや表示するデバイスに合わせて、画像の大きさや商品の組み合わせなど、さまざまな形式で商品を表示する広告です。 |
| BANNER_IMAGE_AD | xsd:string | 画像で構成される広告です。 |
| BANNER_VIDEO_AD | xsd:string | 動画で構成される広告です。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

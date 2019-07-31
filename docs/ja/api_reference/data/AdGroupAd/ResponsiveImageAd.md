

# ResponsiveImageAd

ResponsiveImageAdオブジェクトは、レスポンシブ広告の情報を表します。

### Service

+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace

[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

### Inheritance

+ [Ad](./Ad.md)

| Field | Type | Description | response | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| headline | xsd:string | タイトルです。 | yes | Requirement | Optional | Ignore | |
| description | xsd:string | 説明文です。 | yes | Requirement | Optional | Ignore | |
| url | xsd:string | リンク先URLです。 | yes | Requirement | Optional | Ignore | |
| displayUrl | xsd:string | 表示URLです。 | yes | Optional<br><br>※Default値<br>-標準キャンペーン：<br>入力必須<br>-アプリキャンペーン（iOS）：<br>「itunes.apple.com」<br>-アプリキャンペーン（Android）：<br>「play.google.com」 | Optional<br/>Updatable<br><br>  ※入力許可<br>  -アプリキャンペーン（iOS）：<br>  「itunes.apple.com」のみ可能<br>  -アプリキャンペーン（Android）：<br>  「play.google.com」のみ可能<br> | Ignore | |
| buttonText | enum [ButtonText](./ButtonText.md) | 広告に表示するボタンのテキストです。<br/>※Default値：FOR_MORE_INFO | yes | Optional | Optional | Ignore | |
| principal | xsd:string | 主体者表記です。 | yes | Requirement | Optional | Ignore | |
| logoMediaId | xsd:long | ロゴ画像のメディアIDです。 | yes | Optional | Optional | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>



# BannerVideoAd

BannerVideoAdオブジェクトは、動画で構成される広告の情報を表します。

### Service

+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace

[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

### Inheritance

+ [Ad](./Ad.md)

| Field | Type | Description | response | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| url | xsd:string | リンク先URL | yes | Requirement | Optional | Ignore | |
| displayUrl | xsd:string | 表示URL | yes | Requirement | Optional | Ignore | |
| thumbnailMediaId | xsd:long | サムネイルID | yes | Requirement | Optional | Ignore | |
| videoStartBeaconUrls[0..2] | xsd:string | 再生開始ビーコンURL<br/>※set時はすべて上書きされる<br/>※httpsのURLのみ設定可能 | yes | Optional | Optional<br/>Updatable | Ignore | |
| isRemoveVideoStartBeaconUrls | enum [isRemoveFlg](./isRemoveFlg.md) | 再生開始ビーコンURL<br/>削除<br/>videoStartBeaconUrlが設定されている場合も、こちらが優先される | yes | Ignore | Optional<br/>Updatable | Ignore | |
| video3SecBeaconUrls[0..2] | xsd:string | 3秒視聴ビーコンURL<br/>※set時はすべて上書きされる<br/>※httpsのURLのみ設定可能 | yes | Optional | Optional<br/>Updatable | Ignore | |
| isRemoveVideo3SecBeaconUrls | enum [isRemoveFlg](./isRemoveFlg.md) | 3秒視聴ビーコンURL<br/>削除<br/>video3SecBeaconUrlが設定されている場合も、こちらが優先される | yes | Ignore | Optional<br/>Updatable | Ignore | |
| videoPaidBeaconUrls[0..2] | xsd:string | 課金視聴ビーコンURL<br/>※set時はすべて上書きされる<br/>※httpsのURLのみ設定可能 | yes | Optional | Optional<br/>Updatable | Ignore | |
| isRemoveVideoPaidBeaconUrls | enum [isRemoveFlg](./isRemoveFlg.md) | 課金視聴ビーコンURL<br/>削除<br/>videoPaidBeaconUrlが設定されている場合も、こちらが優先される | yes | Ignore | Optional<br/>Updatable | Ignore | |
| videoCompleteBeaconUrls[0..2] | xsd:string | 再生完了ビーコンURL<br/>※set時はすべて上書きされる<br/>※httpsのURLのみ設定可能 | yes | Optional | Optional<br/>Updatable | Ignore | |
| isRemoveVideoCompleteBeaconUrls | enum [isRemoveFlg](./isRemoveFlg.md) | 再生完了ビーコンURL<br/>削除<br/>videoCompleteBeaconUrlが設定されている場合も、こちらが優先される | yes | Ignore | Optional<br/>Updatable | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

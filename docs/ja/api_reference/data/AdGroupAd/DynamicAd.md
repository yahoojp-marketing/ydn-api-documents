

# DynamicAd

DynamicAdオブジェクトは、動的ディスプレイ広告の情報を表します。

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
| buttonText | enum [ButtonText](./ButtonText.md) | 広告のボタンに表示されるテキスト | yes | Optional<br/>*Default：FOR_MORE_INFO | Optional | Ignore | |
| principal | xsd:string | 広告の主体者表記 | yes | Requirement | Optional | Ignore | |
| logoMediaId | xsd:long | ロゴ画像のメディアID | yes | Requirement | Optional | Ignore | |
| logoMediaId2 | xsd:long | ロゴ画像のメディアID 2 | yes | Requirement | Optional | Ignore | |
| logoMediaId3 | xsd:long | ロゴ画像のメディアID 3 | yes | Requirement | Optional | Ignore | |
| prefix | xsd:string | プレフィックス | yes | Optional | Optional | Ignore | |
| suffix | xsd:string | サフィックス | yes | Optional | Optional | Ignore | |
| brandColor | xsd:string | ブランドカラー<br/>RGB、HEX指定<br/>設定例：#FFFFFF | yes | Optional | Optional | Ignore | |
| campaignBannerUrl | xsd:string | キャンペーンバナーURL | yes | Optional<br>設定する場合は<br>- campaignBannerMediaId<br> - campaignBannerMediaId2<br> - campaignBannerMediaId3<br> - campaignBannerMediaId4<br>いずれかの指定が必要 | Optional | Ignore | |
| isRemoveCampaignBannerUrl | enum [isRemoveFlg](./isRemoveFlg.md) | キャンペーンバナーURL 設定解除 | yes | Ignore | Optional | Ignore | |
| campaignBannerMediaId | xsd:long | キャンペーンバナー画像のメディアID | yes | Optional | Optional | Ignore | |
| isRemoveCampaignBannerMediaId | enum [isRemoveFlg](./isRemoveFlg.md) | キャンペーンバナー画像のメディアID 設定解除 | yes | Ignore | Optional | Ignore | |
| campaignBannerMediaId2 | xsd:long | キャンペーンバナー画像のメディアID 2 | yes | Optional | Optional | Ignore | |
| isRemoveCampaignBannerMediaId2 | enum [isRemoveFlg](./isRemoveFlg.md) | キャンペーンバナー画像のメディアID 2 設定解除 | yes | Ignore | Optional | Ignore | |
| campaignBannerMediaId3 | xsd:long | キャンペーンバナー画像のメディアID 3 | yes | Optional | Optional | Ignore | |
| isRemoveCampaignBannerMediaId3 | enum [isRemoveFlg](./isRemoveFlg.md) | キャンペーンバナー画像のメディアID 3 設定解除 | yes | Ignore | Optional | Ignore | |
| campaignBannerMediaId4 | xsd:long | キャンペーンバナー画像のメディアID 4 | yes | Optional | Optional | Ignore | |
| isRemoveCampaignBannerMediaId4 | enum [isRemoveFlg](./isRemoveFlg.md) | キャンペーンバナー画像のメディアID 4 設定解除 | yes | Ignore | Optional | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

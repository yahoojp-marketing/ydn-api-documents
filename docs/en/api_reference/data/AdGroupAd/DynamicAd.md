

# DynamicAd

DynamicAd object describes information regarding dynamic ads for display.

### Service

+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace

[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

### Inheritance

+ [Ad](./Ad.md)

| Field | Type | Description | response | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| url | xsd:string | Destination URL. | yes | Requirement | Optional | Ignore | |
| displayUrl | xsd:string | Display URL. | yes | Requirement | Optional | Ignore | |
| buttonText | enum [ButtonText](./ButtonText.md) | Text for display ad button. | yes | Optional<br/>*Default：FOR_MORE_INFO | Optional | Ignore | |
| principal | xsd:string | Advertiser Indication. | yes | Requirement | Optional | Ignore | |
| logoMediaId | xsd:long | Media ID of logo image. | yes | Requirement | Optional | Ignore | |
| logoMediaId2 | xsd:long | Media ID of logo image 2. | yes | Requirement | Optional | Ignore | |
| logoMediaId3 | xsd:long | Media ID of logo image 3. | yes | Requirement | Optional | Ignore | |
| prefix | xsd:string | Prefix. | yes | Optional | Optional | Ignore | |
| suffix | xsd:string | Suffix.  | yes | Optional | Optional | Ignore | |
| brandColor | xsd:string | Brand color<br/>Format :RGB or HEX<br/>e.g.：#FFFFFF | yes | Optional | Optional | Ignore | |
| campaignBannerUrl | xsd:string | Campaign banner URL | yes | Optional<br>Optional<br>For setting, one of the following is required:<br/>-campaignBannerMediaId<br/>-campaignBannerMediaId2<br/>-campaignBannerMediaId3<br/>-campaignBannerMediaId4 | Optional | Ignore | |
| isRemoveCampaignBannerUrl | enum [isRemoveFlg](./isRemoveFlg.md) | Remove campaign banner URL | yes | Ignore | Optional | Ignore | |
| campaignBannerMediaId | xsd:long | Campaign banner media ID | yes | Optional | Optional | Ignore | |
| isRemoveCampaignBannerMediaId | enum [isRemoveFlg](./isRemoveFlg.md) | Remove campaign banner media ID | yes | Ignore | Optional | Ignore | |
| campaignBannerMediaId2 | xsd:long | Campaign banner media ID 2 | yes | Optional | Optional | Ignore | |
| isRemoveCampaignBannerMediaId2 | enum [isRemoveFlg](./isRemoveFlg.md) | Remove campaign banner media ID 2 | yes | Ignore | Optional | Ignore | |
| campaignBannerMediaId3 | xsd:long | Campaign banner media ID 3 | yes | Optional | Optional | Ignore | |
| isRemoveCampaignBannerMediaId3 | enum [isRemoveFlg](./isRemoveFlg.md) | Remove campaign banner media ID 3 | yes | Ignore | Optional | Ignore | |
| campaignBannerMediaId4 | xsd:long | Campaign banner media ID 4 | yes | Optional | Optional | Ignore | |
| isRemoveCampaignBannerMediaId4 | enum [isRemoveFlg](./isRemoveFlg.md) | Remove campaign banner media ID 4 | yes | Ignore | Optional | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

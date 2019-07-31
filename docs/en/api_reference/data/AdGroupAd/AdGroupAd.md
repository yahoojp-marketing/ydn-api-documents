

# AdGroupAd

The AdGroupAd object is a container for storing ad information.

### Service

+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace

[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| accountId | xsd:long | Account ID. | yes | - | Requirement | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | |
| campaignId | xsd:long | Campaign ID. | yes | - | Requirement | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | |
| campaignName | xsd:string | Campaign name. | yes | - | Ignore | Ignore | Ignore | |
| adGroupId | xsd:long | Ad group ID. | yes | - | Requirement | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | |
| adGroupName | xsd:string | Ad group name. | yes | - | Ignore | Ignore | Ignore | |
| adId | xsd:long | Ad ID. | yes | - | Ignore | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | |
| adName | xsd:string | Ad name. | yes | - | Requirement | Optional<br/>Updatable | Ignore | |
| adStyle | enum [AdStyle](./AdStyle.md) | Type of ad style.<br/>*Default value : TEXT | yes | - | Ignore | Ignore | Ignore | |
| mediaId | xsd:long | Media ID (Image ID). | yes | - | Optional | Optional<br/>Updatable | Ignore | |
| userStatus | enum [UserStatus](./UserStatus.md) | Display status. | yes | - | Requirement | Optional<br/>Updatable | Ignore | |
| approvalStatus | enum [ApprovalStatus](./ApprovalStatus.md) | Editorial review status. | yes | - | Ignore | Ignore | Ignore | |
| disapprovalReasonCodes | xsd:string | Reject reason on editorial review. | yes | - | Ignore | Ignore | Ignore | |
| bid | [AdGroupAdBid](./AdGroupAdBid.md)<br>inherited [ManualCPCAdGroupAdBid](./ManualCPCAdGroupAdBid.md)<br>inherited [ManualCPVAdGroupAdBid](./ManualCPVAdGroupAdBid.md) | Bid value. | yes | - | Optional | Optional<br/>Updatable | Ignore | |
| ad | [Ad](./Ad.md)<br>inherited [TextAd](./TextAd.md)<br>inherited [MobileAd](./MobileAd.md)<br>inherited [PosAd](./PosAd.md)<br>inherited [ResponsiveImageAd](./ResponsiveImageAd.md)<br>inherited [StaticFrameAd](./StaticFrameAd.md)<br>inherited [ResponsiveVideoAd](./ResponsiveVideoAd.md)<br>inherited [DynamicAd](./DynamicAd.md)<br>inherited [BannerVideoAd](./BannerVideoAd.md)<br>inherited [BannerImageAd](./BannerImageAd.md) | Container including ad. | yes | - | Requirement | Optional<br/>Updatable | Ignore | |
| impressionBeaconUrls[0..2] | xsd:string | Impression beacon URL. | yes | - | Optional | Optional<br/>Updatable | Ignore | |
| isRemoveBeaconUrls | enum [isRemoveFlg](./isRemoveFlg.md) | Remove flag of impression beacon URL.<br/>If set &#39;TRUE&#39;, the set value on the impression beacon URL is invalid. | - | - | Ignore | Optional<br/>Updatable | Ignore | |
| labels[0..1000] | [Label](./Label.md) | Label | yes | - | Ignore | Ignore | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

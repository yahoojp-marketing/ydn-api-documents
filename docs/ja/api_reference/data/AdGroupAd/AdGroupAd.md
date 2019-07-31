

# AdGroupAd

AdGroupAdオブジェクトは、広告の情報を格納するコンテナです。

### Service

+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace

[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| accountId | xsd:long | アカウントID | yes | - | Requirement | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | |
| campaignId | xsd:long | キャンペーンID | yes | - | Requirement | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | |
| campaignName | xsd:string | キャンペーン名 | yes | - | Ignore | Ignore | Ignore | |
| adGroupId | xsd:long | 広告グループID | yes | - | Requirement | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | |
| adGroupName | xsd:string | 広告グループ名 | yes | - | Ignore | Ignore | Ignore | |
| adId | xsd:long | 広告ID | yes | - | Ignore | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | |
| adName | xsd:string | 広告名 | yes | - | Requirement | Optional<br/>Updatable | Ignore | |
| adStyle | enum [AdStyle](./AdStyle.md) | 掲載フォーマットの種別<br/>※デフォルト値は「TEXT」 | yes | - | Ignore | Ignore | Ignore | |
| mediaId | xsd:long | 画像ID | yes | - | Optional | Optional<br/>Updatable | Ignore | |
| userStatus | enum [UserStatus](./UserStatus.md) | 配信状況 | yes | - | Requirement | Optional<br/>Updatable | Ignore | |
| approvalStatus | enum [ApprovalStatus](./ApprovalStatus.md) | 審査状況 | yes | - | Ignore | Ignore | Ignore | |
| disapprovalReasonCodes | xsd:string | 掲載拒否の理由 | yes | - | Ignore | Ignore | Ignore | |
| bid | [AdGroupAdBid](./AdGroupAdBid.md)<br>inherited [ManualCPCAdGroupAdBid](./ManualCPCAdGroupAdBid.md)<br>inherited [ManualCPVAdGroupAdBid](./ManualCPVAdGroupAdBid.md) | 入札価格 | yes | - | Optional | Optional<br/>Updatable | Ignore | |
| ad | [Ad](./Ad.md)<br>inherited [TextAd](./TextAd.md)<br>inherited [MobileAd](./MobileAd.md)<br>inherited [PosAd](./PosAd.md)<br>inherited [ResponsiveImageAd](./ResponsiveImageAd.md)<br>inherited [StaticFrameAd](./StaticFrameAd.md)<br>inherited [ResponsiveVideoAd](./ResponsiveVideoAd.md)<br>inherited [DynamicAd](./DynamicAd.md)<br>inherited [BannerVideoAd](./BannerVideoAd.md)<br>inherited [BannerImageAd](./BannerImageAd.md) | 広告を含むコンテナ | yes | - | Requirement | Optional<br/>Updatable | Ignore | |
| impressionBeaconUrls[0..2] | xsd:string | インプレッションビーコンURL | yes | - | Optional | Optional<br/>Updatable | Ignore | |
| isRemoveBeaconUrls | enum [isRemoveFlg](./isRemoveFlg.md) | インプレッションビーコンURL<br/>削除フラグです。<br/>設定値が「TRUE」の場合、設定されている<br/>インプレッションビーコンURLの<br/>値が無効になります。 | - | - | Ignore | Optional<br/>Updatable | Ignore | |
| labels[0..1000] | [Label](./Label.md) | ラベル | yes | - | Ignore | Ignore | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

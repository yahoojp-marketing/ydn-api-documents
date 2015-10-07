# AdGroupAd
The AdGroupAd object is a container for storing ad information.
### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

| Field | Data Type | Description | 
|---|---|---|
| accountId| xsd:long| The account ID. |
| campaignId| xsd:long| The campaign ID. |
| campaignName| xsd:string| The campaign name. |
| adGroupId| xsd:long| The ad group ID. |
| adGroupName| xsd:string| The ad group name. |
| adId| xsd:long| The ad ID. |
| adName| xsd:string| The ad name. |
| adStyle| enum <a href="../data/AdStyle.md">AdStyle</a>| The ad style. <br>Default is “TEXT”. |
| mediaId| xsd:long| The media ID. |
| userStatus| enum <a href="../data/UserStatus.md">UserStatus</a>| Display status. |
| approvalStatus| enum <a href="../data/ApprovalStatus.md">ApprovalStatus</a>| Approval status. |
| disapprovalReasonCodes| xsd:string| Reason for disapproval. |
| bid| AdGroupAdBid<br>inherited <a href="../data/ManualCPCAdGroupAdBid.md">ManualCPCAdGroupAdBid</a>| Bid value. |
| ad| <a href="../data/Ad.md">Ad</a><br>inherited <a href="../data/TextAd.md">TextAd</a><br>inherited <a href="../data/MobileAd.md">MobileAd</a><br>inherited <a href="../data/PosAd.md">PosAd</a><br>inherited <a href="../data/ResponsiveAd.md">ResponsiveAd</a><br>inherited <a href="../data/StaticFrameAd.md">StaticFrameAd</a><br>inherited <a href="../data/None.md">None</a>| Container including ads. |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

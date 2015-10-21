# AdGroupAd
AdGroupAdオブジェクトは、広告の情報を格納するコンテナです。
### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| accountId| xsd:long| アカウントIDです。 |
| campaignId| xsd:long| キャンペーンIDです。 |
| campaignName| xsd:string| キャンペーン名です。 |
| adGroupId| xsd:long| 広告グループIDです。 |
| adGroupName| xsd:string| 広告グループ名です。 |
| adId| xsd:long| 広告IDです。 |
| adName| xsd:string| 広告名です。 |
| adStyle| enum <a href="../data/AdStyle.md">AdStyle</a>| 掲載フォーマットの種別です。<br>デフォルト値は「TEXT」です。 |
| mediaId| xsd:long| 画像IDです。 |
| userStatus| enum <a href="../data/UserStatus.md">UserStatus</a>| 配信状況です。 |
| approvalStatus| enum <a href="../data/ApprovalStatus.md">ApprovalStatus</a>| 審査状況です。 |
| disapprovalReasonCodes| xsd:string| 掲載拒否の理由です。 |
| bid| AdGroupAdBid<br>inherited <a href="../data/ManualCPCAdGroupAdBid.md">ManualCPCAdGroupAdBid</a>| 入札価格です。 |
| ad| <a href="../data/Ad.md">Ad</a><br>inherited <a href="../data/TextAd.md">TextAd</a><br>inherited <a href="../data/MobileAd.md">MobileAd</a><br>inherited <a href="../data/PosAd.md">PosAd</a><br>inherited <a href="../data/ResponsiveAd.md">ResponsiveAd</a><br>inherited <a href="../data/StaticFrameAd.md">StaticFrameAd</a><br>inherited <a href="../data/None.md">None</a>| 広告を含むコンテナです。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

# Campaign
The Campaign object is a container for storing campaign information.
### Service
+ [CampaignService](../services/CampaignService.md)

| Field | Data Type | Description | 
|---|---|---|
| accountId| xsd:long| The account ID. |
| campaignId| xsd:long| The campaign ID. |
| campaignName| xsd:string| The campaign name. |
| userStatus| enum <a href="../data/UserStatus.md">UserStatus</a>| Ad Delivery status that can be set by an user. |
| servingStatus| enum <a href="../data/CampaignServingStatus.md">CampaignServingStatus</a>| Delivery status in campaign level.<br>Display the campaign status, regardless of userStatus setting. |
| startDate| xsd:string| The start date. |
| endDate| xsd:string| The end date. |
| budget| <a href="../data/Budget.md">Budget</a>| Container including budget. |
| biddingStrategy| <a href="../data/BiddingStrategy.md">BiddingStrategy</a>| Container including bidding strategy. |
| adProductType| xsd:string|  Ad Product Type.|
| frequencyCap| <a href="../data/FrequencyCap.md">FrequencyCap</a>| Frequency Cap |
| conversionOptimize| <a href="../data/ConversionOptimizer.md">ConversionOptimizer</a>| Conversion Optimization setting |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

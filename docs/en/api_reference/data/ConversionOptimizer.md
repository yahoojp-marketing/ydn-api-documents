# ConversionOptimizer
The CampaignPage object serves retrieved campaign entry.
### Service
+ [CampaignService](../../services/CampaignService.md)

### Namespace
[CampaignService#Namespace](../../services/CampaignService.md#namespace)

| Field | Data Type | Description | 
|---|---|---|
| Page(inherited)|||
| targetCpa| xsd:long| Target CPA<br>※Default: 0<br>※Setting range: 0 - 9,999,999,999<br>※"0": Conversion Optimization is invalid<br>※"1" or more: Conversion Optimization is valid<br>※If "Conversion Optimization Availability" is DISABLE, target value cannot be changed from "0" to "1" or more.<br>※If Conversion Optimization is performing, bid that been set manually will be invalid. |
| eligibilityFlg| enum <a href="./ConversionOptimizerEligibilityFlg.md">ConversionOptimizerEligibilityFlg</a>| Conversion Optimization Availability<br>※Default: DISABLE<br>※Less than 15 conversion in the past 30 days: DISABLE<br>※15 or more conversion in the past 30 days: ENABLE |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

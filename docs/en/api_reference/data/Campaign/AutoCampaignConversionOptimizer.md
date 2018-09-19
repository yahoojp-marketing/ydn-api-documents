# AutoCampaignConversionOptimizer
AutoCampaignConversionOptimizer retains conversion optimization settings.
### Service
+ [CampaignService](../../services/CampaignService.md)

### Namespace
[CampaignService#Namespace](../../services/CampaignService.md#namespace)

| Field | Type | response| add| set| remove| Description|
|---|---|---|---|---|---|---|
|<a href="CampaignConversionOptimizer.md">CampaignConversionOptimizer</a> (inherited)|||||||
| targetCpa| xsd:long| yes| Ignore| Optional| Ignore| This field is desired conversion cost value.<br>※Settable range：1 - 9,999,999,999<br>※If function of conversion optimization is running, manual bid settings is invalid.|
| eligibilityFlg| enum <a href="./ConversionOptimizerEligibilityFlg.md">ConversionOptimizerEligibilityFlg</a>| yes| Ignore| Ignore| Ignore| Availability of conversion optimization.<br>If this field value is 'DISABLE',this Campaign cannot use Auto Bigging(Conversion Optimization).|

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

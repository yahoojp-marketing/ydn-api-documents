

# AutoCampaignConversionOptimizer

AutoCampaignConversionOptimizer retains conversion optimization settings.

### Service

+ [CampaignService](../../services/CampaignService.md)

### Namespace

[CampaignService#Namespace](../../services/CampaignService.md#namespace)

### Inheritance

+ [CampaignConversionOptimizer](./CampaignConversionOptimizer.md)

| Field | Type | Description | response | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| targetCpa | xsd:long | This field is desired conversion cost value.<br>* Settable range：1 - 9,999,999,999<br>* If function of conversion optimization is running, manual bid settings is invalid.<br> | yes | Ignore | Optional | Ignore | |
| eligibilityFlg | enum [ConversionOptimizerEligibilityFlg](./ConversionOptimizerEligibilityFlg.md) | Availability of conversion optimization.<br>If this field value is &#39;DISABLE&#39;,this Campaign cannot use Auto Bidding(Conversion Optimization). | yes | Ignore | Ignore | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

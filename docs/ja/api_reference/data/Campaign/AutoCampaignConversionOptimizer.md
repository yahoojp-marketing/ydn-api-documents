

# AutoCampaignConversionOptimizer

AutoCampaignConversionOptimizerオブジェクトは、コンバージョン最適化設定情報を表します。

### Service

+ [CampaignService](../../services/CampaignService.md)

### Namespace

[CampaignService#Namespace](../../services/CampaignService.md#namespace)

### Inheritance

+ [CampaignConversionOptimizer](./CampaignConversionOptimizer.md)

| Field | Type | Description | response | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| targetCpa | xsd:long | コンバージョン単価の目標値です。<br>※設定範囲：1 - 9,999,999,999<br>※コンバージョン最適化機能が動作している場合には、手動で設定されている入札設定は無効になります。<br> | yes | Ignore | Optional | Ignore | |
| eligibilityFlg | enum [ConversionOptimizerEligibilityFlg](./ConversionOptimizerEligibilityFlg.md) | コンバージョン最適化使用可否です。<br>※DISABLEの場合は自動入札（コンバージョン最適化）は使えません。 | yes | Ignore | Ignore | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

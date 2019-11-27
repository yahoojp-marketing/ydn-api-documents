

# AutoAdGroupConversionOptimizer

AutoAdGroupConversionOptimizerは、コンバージョン最適化「自動入札」設定を保持するオブジェクトです。<br>
* 目的ありのキャンペーン配下の広告グループでは設定不可


### Service

+ [AdGroupService](../../services/AdGroupService.md)

### Namespace

[AdGroupService#Namespace](../../services/AdGroupService.md#namespace)

### Inheritance

+ [AdGroupConversionOptimizer](./AdGroupConversionOptimizer.md)

| Field | Type | Description | response | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| targetCpa | xsd:long | コンバージョン単価の目標値です。<br/>※設定範囲：1 - 9,999,999,999<br/>※コンバージョン最適化機能が動作している場合には、手動で設定されている入札設定は無効になります。 | yes | Optional | Optional | Ignore | |
| eligibilityFlg | enum [ConversionOptimizerEligibilityFlg](./ConversionOptimizerEligibilityFlg.md) | コンバージョン最適化利用可否です。<br/>※DISABLEの場合は自動入札（コンバージョン最適化）は使えません。 | yes | Ignore | Ignore | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

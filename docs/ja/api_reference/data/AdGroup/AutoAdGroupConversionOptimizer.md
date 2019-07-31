# AutoAdGroupConversionOptimizer
AutoAdGroupConversionOptimizerは、コンバージョン最適化「自動入札」設定を保持するオブジェクトです。
### Service
+ [AdGroupService](../../services/AdGroupService.md)

### Namespace
[AdGroupService#Namespace](../../services/AdGroupService.md#namespace)

| Field | Type |response | add | set | remove | Description |
|---|---|---|---|---|---|---|
| <a href="AdGroupConversionOptimizer.md">AdGroupConversionOptimizer</a>(inherited)||||||
| targetCpa| xsd:long | yes| Required| Optional| Ignore|コンバージョン単価の目標値です。<br>※設定範囲：1 - 9,999,999,999<br>※コンバージョン最適化機能が動作している場合には、手動で設定されている入札設定は無効になります。|
| eligibilityFlg| enum <a href="ConversionOptimizerEligibilityFlg.md">ConversionOptimizerEligibilityFlg</a> | yes| Ignore| Ignore| Ignore|コンバージョン最適化利用可否です。<br>※DISABLEの場合は自動入札（コンバージョン最適化）は使えません。|

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

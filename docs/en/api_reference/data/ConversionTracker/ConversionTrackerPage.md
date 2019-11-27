

# ConversionTrackerPage

ConversionTrackerPage object contains the results (a list of all entities) for get method.

### Service

+ [ConversionTrackerService](../../services/ConversionTrackerService.md)

### Namespace

[ConversionTrackerService#Namespace](../../services/ConversionTrackerService.md#namespace)

### Inheritance

+ [Page](../Common/Page.md)

| Field | Type | Description | response |
| ----- | ---- | ----------- | -------- |
| totalConversions | xsd:long | Total of conversions | yes | |
| totalConversionValue | xsd:string | Total of conv. value | yes | |
| totalConversionsViaAdClick | xsd:long | Total of conversions (via click) | yes | |
| totalConversionValueViaAdClick | xsd:string | Total of conv. value (via click) | yes | |
| totalAllConversions | xsd:long | Total of conversions (all) | yes | |
| totalAllConversionValue | xsd:string | Total of conv. value (all) | yes | |
| totalCrossDeviceConversions | xsd:long | Total of cross-device conv. | yes | |
| period | [Period](./Period.md) | Update date of statistics | yes | |
| values[0...1000] | [ConversionTrackerValues](./ConversionTrackerValues.md) | The results for get method | yes | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

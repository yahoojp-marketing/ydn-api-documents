# ConversionTrackerPage
ConversionTrackerPage object contains the results (a list of all entities) for get method.

### Service
+ [ConversionTrackerService](../../services/ConversionTrackerService.md)

### Namespace
[ConversionTrackerService#Namespace](../../services/ConversionTrackerService.md#namespace)

### Inheritance
+ [Page](../Common/Page.md)

| Field | Type | Description |
|---|---|---|
| totalConversions | xsd:long | Total number of Conversions<br>&lowast;Contains cross-device conversions (including video view)|
| totalConversionValue | xsd:string | Total values of Conversions<br>&lowast;Contains cross-device conversions (including video view) |
| totalAllConversions | xsd:long | Conversion count of Auto bidding + Negative conversion count |
| totalAllConversionValue | xsd:string | Conversion value of Auto bidding + Negative conversion value |
| period | <a href="./Period.md">Period</a> | Update date of statistics |
| values[0...1000] | <a href="./ConversionTrackerValues.md">ConversionTrackerValues</a> | The results for get method |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

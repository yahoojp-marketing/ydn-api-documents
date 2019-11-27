

# ConversionTrackerPage

ConversionTrackerPageオブジェクトは、getメソッドの実行結果（全Entityのリスト）を保持します。

### Service

+ [ConversionTrackerService](../../services/ConversionTrackerService.md)

### Namespace

[ConversionTrackerService#Namespace](../../services/ConversionTrackerService.md#namespace)

### Inheritance

+ [Page](../Common/Page.md)

| Field | Type | Description | response |
| ----- | ---- | ----------- | -------- |
| totalConversions | xsd:long | コンバージョン数の合計 | yes | |
| totalConversionValue | xsd:string | コンバージョンの価値の合計 | yes | |
| totalConversionsViaAdClick | xsd:long | コンバージョン数の合計（クリック経由） | yes | |
| totalConversionValueViaAdClick | xsd:string | コンバージョンの価値の合計（クリック経由） | yes | |
| totalAllConversions | xsd:long | コンバージョン数（全て）の合計 | yes | |
| totalAllConversionValue | xsd:string | コンバージョンの価値（全て）の合計 | yes | |
| totalCrossDeviceConversions | xsd:long | クロスデバイスコンバージョン数の合計 | yes | |
| period | [Period](./Period.md) | 統計情報更新日。 | yes | |
| values[0...1000] | [ConversionTrackerValues](./ConversionTrackerValues.md) | getメソッドの実行結果。 | yes | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

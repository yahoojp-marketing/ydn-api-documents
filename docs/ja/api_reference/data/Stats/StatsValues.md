

# StatsValues

StatsValuesオブジェクトは、get/mutateメソッドの統計情報1件あたりの実行結果（1 Entity）を保持します。

### Service

+ [StatsService](../../services/StatsService.md)

### Namespace

[StatsService#Namespace](../../services/StatsService.md#namespace)

### Inheritance

+ [ReturnValue](../Common/ReturnValue.md)

| Field | Type | Description | response | get |
| ----- | ---- | ----------- | -------- | --------- |
| accountId | xsd:long | アカウントIDです。 | yes | - | |
| statsPeriod | enum [StatsPeriod](./StatsPeriod.md) | 統計情報の集計期間です。 | yes | - | |
| statsPeriodCustomDate | [StatsPeriodCustomDate](./StatsPeriodCustomDate.md) | 統計情報の任意日付指定です。<br/>CUSTOM_DATEの場合は必須 | yes | - | |
| statsType | enum [StatsType](./StatsType.md) | 統計種別です。 | yes | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

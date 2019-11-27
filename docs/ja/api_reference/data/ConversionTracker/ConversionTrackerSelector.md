

# ConversionTrackerSelector

ConversionTrackerSelectorオブジェクトは、getメソッドの検索条件（実行パラメータ）を保持します。

### Service

+ [ConversionTrackerService](../../services/ConversionTrackerService.md)

### Namespace

[ConversionTrackerService#Namespace](../../services/ConversionTrackerService.md#namespace)

| Field | Type | Description | response | get |
| ----- | ---- | ----------- | -------- | --------- |
| accountId | xsd:long | アカウントID。 | yes | Requirement | |
| conversionTrackerIds[0..1000] | xsd:long | コンバージョントラッカーのID。 | yes | Optional | |
| conversionTrackerTypes[0..2] | enum [ConversionTrackerType](./ConversionTrackerType.md) | コンバージョン種別。 | yes | Optional | |
| statuses[0..2] | enum [ConversionTrackerStatus](./ConversionTrackerStatus.md) | コンバージョントラッカーのステータス。 | yes | Optional | |
| categories[0..7] | enum [ConversionTrackerCategory](./ConversionTrackerCategory.md) | トラッキング対象となるコンバージョンのカテゴリー。 | yes | Optional | |
| appIds[0..1000] | xsd:string | アプリID。 | yes | Optional | |
| countingType | enum [ConversionCountingType](./ConversionCountingType.md) | 計測方法。 | yes | Optional | |
| excludeFromBidding | enum [ExcludeFromBidding](./ExcludeFromBidding.md) | 自動入札から除外するかどうかのフラグ。 | yes | Optional | |
| appPlatform | enum [AppConversionPlatform](./AppConversionPlatform.md) | アプリコンバージョンの対象プラットフォーム。 | yes | Optional | |
| statsPeriod | enum [StatsPeriod](./StatsPeriod.md) | 統計情報の集計期間。<br>※指定なし：REALTIME_TODAY | yes | Optional | |
| statsPeriodCustomDate | [StatsPeriodCustomDate](./StatsPeriodCustomDate.md) | 統計情報の集計期間。年月日で指定可能。<br>※StatsPeriodが「CUSTOM_DATE」の時は入力が必須。 | yes | Optional | |
| paging | [Paging](../Common/Paging.md) | データの取得範囲。 | yes | Optional | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>



# ConversionTrackerSelector

ConversionTrackerSelector object contains a set of criteria (parameters) for get method.

### Service

+ [ConversionTrackerService](../../services/ConversionTrackerService.md)

### Namespace

[ConversionTrackerService#Namespace](../../services/ConversionTrackerService.md#namespace)

| Field | Type | Description | response | get |
| ----- | ---- | ----------- | -------- | --------- |
| accountId | xsd:long | Account ID. | yes | Requirement | |
| conversionTrackerIds[0..1000] | xsd:long | Conversion Tracker ID. | yes | Optional | |
| conversionTrackerTypes[0..2] | enum [ConversionTrackerType](./ConversionTrackerType.md) | Conversion Type. | yes | Optional | |
| statuses[0..2] | enum [ConversionTrackerStatus](./ConversionTrackerStatus.md) | Conversion Tracker Status. | yes | Optional | |
| categories[0..7] | enum [ConversionTrackerCategory](./ConversionTrackerCategory.md) | Conversion Category subjected to Tracking. | yes | Optional | |
| appIds[0..1000] | xsd:string | App ID. | yes | Optional | |
| countingType | enum [ConversionCountingType](./ConversionCountingType.md) | Method of measurement conversion. | yes | Optional | |
| excludeFromBidding | enum [ExcludeFromBidding](./ExcludeFromBidding.md) | Setting for exclude from Bidding. | yes | Optional | |
| appPlatform | enum [AppConversionPlatform](./AppConversionPlatform.md) | Platform subjected to App Conversion. | yes | Optional | |
| statsPeriod | enum [StatsPeriod](./StatsPeriod.md) | Summarized period of statistics.<br>∗None : REALTIME_TODAY. | yes | Optional | |
| statsPeriodCustomDate | [StatsPeriodCustomDate](./StatsPeriodCustomDate.md) | Summarized period of statistics. Can be specified by year, month and day.<br>∗Specification is required if StatsPeriod is &#34;CUSTOM_DATE&#34;. | yes | Optional | |
| paging | [Paging](../Common/Paging.md) | Page returned as response. | yes | Optional | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>



# ConversionTracker

ConversionTracker object shows ConversionTracker information such as ConversionTag and performance data by tag.

### Service

+ [ConversionTrackerService](../../services/ConversionTrackerService.md)

### Namespace

[ConversionTrackerService#Namespace](../../services/ConversionTrackerService.md#namespace)

| Field | Type | Description | response | add | set |
| ----- | ---- | ----------- | -------- | --------- | --------- |
| accountId | xsd:long | Account ID | yes | Ignore | Ignore | |
| conversionTrackerId | xsd:long | Conversion Tracker ID | yes | Ignore | Required | |
| conversionTrackerName | xsd:string | Conversion Tracker Name | yes | Required | Optional<br>Updatable | |
| status | enum [ConversionTrackerStatus](./ConversionTrackerStatus.md) | Conversion Tracker Status | yes | Required | Optional<br>Updatable | |
| category | enum [ConversionTrackerCategory](./ConversionTrackerCategory.md) | Conversion category for tracking | yes | Required | Optional<br>Updatable | |
| userRevenueValue | xsd:long | Revenue value for Conversions | yes | Optional<br>*Default : 0 | Optional<br>Updatable | |
| conversionTrackerType | enum [ConversionTrackerType](./ConversionTrackerType.md) | Conversion Type | yes | Required | Required | |
| countingType | enum [ConversionCountingType](./ConversionCountingType.md) | The selected option for counting type for Conversion tracking. | yes | Optional | Optional | |
| measurementPeriod | xsd:int | Counting period (Unit: Day)<br>∗within the range of 7 to 90 days | yes | Optional<br>*Default : 30 | Optional | |
| measurementPeriodView | xsd:int | Counting period (Video view)<br>∗within the range of 1 to 30 | yes | Optional<br>*Default : 1 | Optional | |
| excludeFromBidding | enum [ExcludeFromBidding](./ExcludeFromBidding.md) | Describes whether using the item for auto bidding setting or not.<br>*&#39;Conversion Counting&#39; setting | yes | Opitonal<br>*Default : FALSE(include) | Optional | |
| conversions | xsd:long | Conversions | yes | Ignore | Ignore | |
| conversionValue | xsd:string | Conv. value/conv. | yes | Ignore | Ignore | |
| conversionsViaAdClick | xsd:long | Conversions (via click) | yes | Ignore | Ignore | |
| conversionValueViaAdClick | xsd:string | Conv. value (via click) | yes | Ignore | Ignore | |
| allConversions | xsd:long | Conversions (all) | yes | Ignore | Ignore | |
| allConversionValue | xsd:string | Conv. value (all) | yes | - | - | |
| crossDeviceConversions | xsd:long | Cross-device conv. | yes | Ignore | Ignore | |
| mostRecentConversionDate | xsd:string | The date of the most recent conversion<br>(YYYYMMDD) | yes | Ignore | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

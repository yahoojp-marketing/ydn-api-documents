

# StatsSelector

StatsSelector object is a container that includes the search conditions (execution parameters) of get methods.

### Service

+ [StatsService](../../services/StatsService.md)

### Namespace

[StatsService#Namespace](../../services/StatsService.md#namespace)

| Field | Type | Description | response | get |
| ----- | ---- | ----------- | -------- | --------- |
| accountId | xsd:long | Account ID. | yes | Requirement | |
| campaignIds[0...500] | xsd:long | Campaign ID.<br/>Available only when &#34;CAMPAIGN&#34; or &#34;ADGROUP&#34; or &#34;AD&#34; or &#34;TARGET&#34; is specified for statsType. | yes | Optional | |
| adGroupIds[0..500] | xsd:long | Ad group ID.<br/>Available only when &#34;ADGROUP&#34; or &#34;AD&#34; or &#34;TARGET&#34; is specified for statsType. | yes | Optional | |
| adIds[0..500] | xsd:long | Ad ID.<br/>Available only when &#34;AD&#34; is specified for statsType. | yes | Optional | |
| mediaIds[0..500] | xsd:long | Media ID.<br/>Available only when "MEDIA" is specified for statsType. | yes | Optional | |
| targetTypes[0..1] | enum [TargetType](./TargetType.md) | Target Type.<br/>Specification is required when statsType is &#34;TARGET&#34;. | yes | Optional | |
| statsPeriod | enum [StatsPeriod](./StatsPeriod.md) | Aggregation period of statistics.<br/>Default is &#34;REALTIME_MONTH&#34;. | yes | Optional | |
| statsPeriodCustomDate | [StatsPeriodCustomDate](./StatsPeriodCustomDate.md) | Aggregation period of statistics. Can be specified by year, month and day.<br/>∗ Specification is required when StatsPeriod is &#34;CUSTOM_DATE&#34;. | yes | Optional | |
| statsType | enum [StatsType](./StatsType.md) | Type of statistics.<br/>Default is &#34;CAMPAIGN&#34;. | yes | Optional | |
| paging | [Paging](../Common/Paging.md) | Paging for the response. | yes | Optional | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

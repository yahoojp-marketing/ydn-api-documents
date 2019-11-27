

# TargetStatsValues

TargetStatsValuesオブジェクトは、ターゲティングの統計情報を保持します。

### Service

+ [StatsService](../../services/StatsService.md)

### Namespace

[StatsService#Namespace](../../services/StatsService.md#namespace)

### Inheritance

+ [StatsValues](./StatsValues.md)

| Field | Type | Description | response |
| ----- | ---- | ----------- | -------- |
| campaignId | xsd:long | キャンペーンID | yes | |
| campaignName | xsd:string | キャンペーン名 | yes | |
| adGroupId | xsd:long | 広告グループID | yes | |
| adGroupName | xsd:string | 広告グループ名 | yes | |
| target | [Target](./Target.md)<br>inherited [AdScheduleTarget](./AdScheduleTarget.md)<br>inherited [GeoTarget](./GeoTarget.md)<br>inherited [AgeTarget](./AgeTarget.md)<br>inherited [GenderTarget](./GenderTarget.md)<br>inherited [InterestCategoryTarget](./InterestCategoryTarget.md)<br>inherited [SearchTarget](./SearchTarget.md)<br>inherited [SiteCategoryTarget](./SiteCategoryTarget.md)<br>inherited [SiteRetargetingTarget](./SiteRetargetingTarget.md)<br>inherited [PlacementTarget](./PlacementTarget.md)<br>inherited [DeviceTarget](./DeviceTarget.md)<br>inherited [CarrierTarget](./CarrierTarget.md)<br>inherited [AppTarget](./AppTarget.md)<br>inherited [OsTarget](./OsTarget.md)<br>inherited [OsVersionTarget](./OsVersionTarget.md)<br>inherited [AudienceCategoryTarget](./AudienceCategoryTarget.md) | ターゲティング情報 | yes | |
| stats | [Stats](./Stats.md) | 統計情報 | yes | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

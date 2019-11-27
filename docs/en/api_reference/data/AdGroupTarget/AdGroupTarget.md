

# AdGroupTarget

The AdGroupTargets object is a container for storing targeting information specified ad group.<br/>

The following targets are not available for campaign goal.<br/>
- InterestCategoryTarget
- OsVersionTarget(Available for Account with APP_PROMOTION authority)
- CarrierTarget

        

### Service

+ [AdGroupTargetService](../../services/AdGroupTargetService.md)

### Namespace

[AdGroupTargetService#Namespace](../../services/AdGroupTargetService.md#namespace)

| Field | Type | Description | response | add | set | remove | replace |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| accountId | xsd:long | Account ID. | yes | Ignore | Ignore | Ignore | Ignore | |
| campaignId | xsd:long | Campaign ID. | yes | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | |
| adGroupId | xsd:long | Ad group ID. | yes | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | |
| bidMultiplier | xsd:double | Bid adjustment.<br/>∗If bid adjustment is unable to set targeting, not returned. | yes | Optional | Optional | Ignore | Optional | |
| target | [Target](./Target.md)<br>inherited [AdScheduleTarget](./AdScheduleTarget.md)<br>inherited [GeoTarget](./GeoTarget.md)<br>inherited [AgeTarget](./AgeTarget.md)<br>inherited [GenderTarget](./GenderTarget.md)<br>inherited [InterestCategoryTarget](./InterestCategoryTarget.md)<br>inherited [SearchTarget](./SearchTarget.md)<br>inherited [SiteCategoryTarget](./SiteCategoryTarget.md)<br>inherited [SiteRetargetingTarget](./SiteRetargetingTarget.md)<br>inherited [PlacementTarget](./PlacementTarget.md)<br>inherited [DeviceTarget](./DeviceTarget.md)<br>inherited [CarrierTarget](./CarrierTarget.md)<br>inherited [AppTarget](./AppTarget.md)<br>inherited [OsTarget](./OsTarget.md)<br>inherited [OsVersionTarget](./OsVersionTarget.md)<br>inherited [AudienceCategoryTarget](./AudienceCategoryTarget.md) | Targeting information of ad group. | yes | Requirement | Requirement | Requirement | Requirement | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

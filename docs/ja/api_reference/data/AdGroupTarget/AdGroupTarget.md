

# AdGroupTarget

AdGroupTargetオブジェクトは、広告グループに設定されているターゲティング情報を格納します。<br/>

以下のターゲットはキャンペーン目的では利用出来ません。<br/>
- InterestCategoryTarget
- OsVersionTarget(APP_PROMOTIOM権限のあるAccountの場合は利用可能)
- CarrierTarget

        

### Service

+ [AdGroupTargetService](../../services/AdGroupTargetService.md)

### Namespace

[AdGroupTargetService#Namespace](../../services/AdGroupTargetService.md#namespace)

| Field | Type | Description | response | add | set | remove | replace |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| accountId | xsd:long | アカウントIDです。 | yes | Ignore | Ignore | Ignore | Ignore | |
| campaignId | xsd:long | キャンペーンIDです。 | yes | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | |
| adGroupId | xsd:long | 広告グループIDです。 | yes | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | |
| bidMultiplier | xsd:double | 入札価格調整率です。<br/>※入札価格調整率が設定できないターゲティングの場合は返却されません。 | yes | Optional | Optional | Ignore | Optional | |
| target | [Target](./Target.md)<br>inherited [AdScheduleTarget](./AdScheduleTarget.md)<br>inherited [GeoTarget](./GeoTarget.md)<br>inherited [AgeTarget](./AgeTarget.md)<br>inherited [GenderTarget](./GenderTarget.md)<br>inherited [InterestCategoryTarget](./InterestCategoryTarget.md)<br>inherited [SearchTarget](./SearchTarget.md)<br>inherited [SiteCategoryTarget](./SiteCategoryTarget.md)<br>inherited [SiteRetargetingTarget](./SiteRetargetingTarget.md)<br>inherited [PlacementTarget](./PlacementTarget.md)<br>inherited [DeviceTarget](./DeviceTarget.md)<br>inherited [CarrierTarget](./CarrierTarget.md)<br>inherited [AppTarget](./AppTarget.md)<br>inherited [OsTarget](./OsTarget.md)<br>inherited [OsVersionTarget](./OsVersionTarget.md)<br>inherited [AudienceCategoryTarget](./AudienceCategoryTarget.md) | 広告グループのターゲティング情報です。 | yes | Requirement | Requirement | Requirement | Requirement | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

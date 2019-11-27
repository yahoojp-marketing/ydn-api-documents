

# Target

The Target object is a container for storing targeting settings.

### Service

+ [AdGroupTargetService](../../services/AdGroupTargetService.md)

### Namespace

[AdGroupTargetService#Namespace](../../services/AdGroupTargetService.md#namespace)

| Field | Type | Description | response | add | set | remove | replace |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| type | enum [TargetType](./TargetType.md) | Targeting type | yes | Requirement | Requirement | Requirement | Requirement | |
| targetId | xsd:string | Target ID<br><br>            ∗1<br>            TargetId indicates the following items in Ver.6.0 and earlier.<br>            ‐SiteRetargeting: targetListId<br>            ‐PlacementTarget: placementUrlListId<br>            ‐SearchTarget: searchKeywordListId<br>            ‐GeoTarget: IM area code(geo)<br>            ‐InterestCategory: category code(category)<br>            ‐SiteCategory: category code(category)<br>            ‐OsVersionTarget: osVersion<br>             | yes | Optional<br><br>※2<br>Required if type is one of the following<br>‐SITE_RETARGETING<br>‐PLACEMENT_TARGET<br>‐SEARCH_TARGET<br>‐GEO_TARGET<br>‐INTEREST_CATEGORY<br>‐SITE_CATEGORY<br>‐AUDIENCE_CATEGORY<br> | Requirement | Requirement | Optional<br>∗3<br>Not required if isRemove is true. | |
| isRemove | xsd:boolean | If true, delete all targeting types. | ‐ | Ignore | Ignore | Ignore | Optional | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

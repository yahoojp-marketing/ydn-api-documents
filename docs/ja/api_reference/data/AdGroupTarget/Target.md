

# Target

Targetオブジェクトは、ターゲティング設定情報を保持します。

### Service

+ [AdGroupTargetService](../../services/AdGroupTargetService.md)

### Namespace

[AdGroupTargetService#Namespace](../../services/AdGroupTargetService.md#namespace)

| Field | Type | Description | response | add | set | remove | replace |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| type | enum [TargetType](./TargetType.md) | ターゲティング種別です。 | yes | Requirement | Requirement | Requirement | Requirement | |
| targetId | xsd:string | ターゲットIDです。<br><br>            ※1<br>            targetIdはVer.6.0以前における以下の項目を示します。<br>            ‐SiteRetargeting：targetListId<br>            ‐PlacementTarget：placementUrlListId<br>            ‐SearchTarget：searchKeywordListId<br>            ‐GeoTarget：IM地域コード(geo)<br>            ‐InterestCategory: カテゴリーコード(category)<br>            ‐SiteCategory: カテゴリーコード(category)<br>            ‐OsVersionTarget:osVersion<br>             | yes | Optional<br><br>※2<br>typeが以下のいずれかの場合、設定必須<br>‐SITE_RETARGETING<br>‐PLACEMENT_TARGET<br>‐SEARCH_TARGET<br>‐GEO_TARGET<br>‐INTEREST_CATEGORY<br>‐SITE_CATEGORY<br>‐AUDIENCE_CATEGORY<br> | Requirement | Requirement | Optional<br>※3<br>isRemoveがtrueの場合、設定不要 | |
| isRemove | xsd:boolean | trueの場合、ターゲティング種別をすべて削除します。 | ‐ | Ignore | Ignore | Ignore | Optional | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

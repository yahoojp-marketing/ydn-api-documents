# PlacementUrlList
The objects to keep Placement Url Information.
### Service
+ [PlacementUrlListService](../services/PlacementUrlListService.md)

| name | type | maxOccurs | minOccurs | response | add | set | remove | description | 
|---|---|---|---|---|---|---|---|---|
| accountId| long| 1| 1| ○| Requirement| RequirementNonUpdatable| RequirementNonUpdatable| Account ID |
| urlListId| long| 1| 0| ○| -| RequirementNonUpdatable| RequirementNonUpdatable| Url List ID |
| urlListName| string| 1| 0| ○| Requirement| OptionalUpdatable| -| Url List Name |
| description| string| 1| 0| ○| Optional| OptionalUpdatable| -| Url List Description |
| isUnknownDomain| enum <a href="./UnknownDomainFlg%20.md">UnknownDomainFlg</a>| 1| 0| ○| OptionalUpdatable| OptionalUpdatable| -| Unknown Domain  Flg default:FALSE |
| urls[0...1000]| <a href="./UrlList.md">UrlList</a>| unbounded| 0| ○| Requirement| OptionalUpdatable| -| Url List |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

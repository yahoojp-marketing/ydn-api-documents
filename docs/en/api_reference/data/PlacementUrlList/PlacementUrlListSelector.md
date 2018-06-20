# PlacementUrlListSelector
The objects to keep get method search conditions (execution parameter).
### Service
+ [PlacementUrlListService](../../services/PlacementUrlListService.md)

### Namespace
[PlacementUrlListService#Namespace](../../services/PlacementUrlListService.md#namespace)

| name | type | maxOccurs | minOccurs | response | add | set | remove | description |
|---|---|---|---|---|---|---|---|---|
| accountId| long| 1| 1| -| -| -| -| Search Condition: Account ID |
| urlListIds[0...500]| long[]| unbounded| 0| -| -| -| -| Search Condition: Placement Url List ID |
| paging| <a href="../Common/Paging.md">Paging</a>| 1| 0| -| -| -| -| Search Condition: Acquired Range |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

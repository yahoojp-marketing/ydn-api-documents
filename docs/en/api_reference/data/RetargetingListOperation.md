# RetargetingListOperation
RetargetingListOperation object displays operation of target list for site retargeting.
### Service
+ [RetargetingListService](../services/RetargetingListService.md)

| name | type | maxOccurs | minOccurs | response | add | set | remove | description | 
|---|---|---|---|---|---|---|---|---|
| accountId| long| 1| 1| -| Requirement| Requirement| Requirement| Account ID |
| targetListType| enum <a href="./TargetListType.md">TargetListType</a>| 1| 0| -| Requirement| Requirement| Requirement| Target List Type |
| operand| <a href="./RetargetingList.md">RetargetingList</a>| unbounded| 1| -| Requirement| Requirement| Requirement| Operation Target List |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

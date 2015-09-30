# CombinationTargetList
CombinationTargetList object is a containerfor storing list of combination of target list information.
### Service
+ [RetargetingListService](../services/RetargetingListService.md)

| Field | Data Type | Description | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| TargetList(inherited)||||||
| targetListType| Enum <a href="./TargetListType.md">TargetListType</a>| Types of target list.| Req| Req| — |
| CombinarionTargetList||||||
| combinations[]| <a href="./Combination.md">Combination</a>| Combination of target list.| Req| Req| — |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

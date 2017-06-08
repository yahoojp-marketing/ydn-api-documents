# RetargetingTagReturnValue
RetargetingTagReturnValue object is a container that holds tag information of site retargeting.

### Service
+ [RetargetingTagService](../services/RetargetingTagService.md)

| Field | Type | maxOccurs | minOccurs | response | add | set | remove | Description | 
|---|---|---|---|---|---|---|---|---|
| ListReturnValue(inherited)|||||||||
| ListReturnValue.Type| xsd: string||||||| This field indicates the subtype of ListReturnValue of this instance.|
| Operation.Type| xsd: string||||||| It is the mutate operation.|
| RetargetingTagReturnValue|||||||||
| values| <a href="./RetargetingTagValues.md">RetargetingTagValues</a>| unbounded|0|○|-|-|-| Process result of mutate method with information of site retargeting tag. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

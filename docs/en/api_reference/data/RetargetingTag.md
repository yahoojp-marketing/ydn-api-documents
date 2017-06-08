# RetargetingTag
RetargetingTag objects displays tag information for site retargeting.
### Service
+ [RetargetingTagService](../services/RetargetingTagService.md)

| Field | Data Type | maxOccurs | minOccurs | response | add | set | remove | Description | 
|---|---|---|---|---|---|---|---|---|
| retargetingTagId| xsd:string|1|1|○|-|-|-| Tag ID for site retargeting. |
| accountId| xsd:long|1|1|○|-|-|-| Account ID. |
| approvalStatus|enum <a href="./RetargetingTagApprovalStatus.md">RetargetingTagApprovalStatus</a>|1|0|○|-|-|-|  Status of site retargeting.  |
| tag| xsd:string|1|0|○|-|-|-| Tag details for site retargeting. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

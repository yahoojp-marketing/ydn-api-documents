# FeedHolderRecord
FeedHolderRecord object contains FeedHolder informaton.

### Service
+ [FeedHolderService](../../services/FeedHolderService.md)

### Namespace
[FeedHolderService#Namespace](../../services/FeedHolderService.md#namespace)

| Field | Type | Description | response | add | set | remove |
|---|---|---|---|---|---|---|
| accountId | xsd:long | AccountId | yes | Requirement | Requirement | Requirement |
| feedHolderId | xsd:long | ID for identifying FeedHolder | yes | Ignore | Requirement | Requirement |
| feedHolderName | xsd:string| Name for identifying FeedHolder | yes | Requirement | Optional | Ignore |
| itemCount| xsd:long| Number of items | yes | Ignore | Ignore | Ignore |
| approvedItemCount| xsd:long| Number of approved items | yes | Ignore | Ignore | Ignore |
| disApprovedItemCount| xsd:long| Number of disapproved items | yes | Ignore | Ignore | Ignore |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

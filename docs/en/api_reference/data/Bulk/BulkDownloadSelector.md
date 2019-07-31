# BulkDownloadSelector
The BulkDownloadSelector defines bulk download targets.
### Service
+ [BulkService](../../services/BulkService.md)

### Namespace
[BulkService#Namespace](../../services/BulkService.md#namespace)

| Field | Data Type | Description | Restriction | 
|---|---|---|---|
| accountId| xsd:long| The account ID.| Req |
| campaignIds| xsd:long| The campaign ID.| Opt |
| adGroupIds| xsd:long| The ad group ID.| Opt |
| adIds| xsd:long| The ad ID.| Opt |
| mediaIds| xsd:long| The media ID.| Opt |
| campaignUserStatuses| enum <a href="./UserStatus.md">UserStatus</a>| This field specifies campaign status| Opt |
| adGroupUserStatuses| enum <a href="./UserStatus.md">UserStatus</a>| This field specifies Ad Group status.| Opt |
| adGroupAdUserStatuses| enum <a href="./UserStatus.md">UserStatus</a>| This field specifies Ad status.| Opt |
| mediaUserStatuses| enum <a href="./UserStatus.md">UserStatus</a>| The media display status.| Opt |
| AdGroupAdApporovalStatuses| enum <a href="./ApprovalStatus.md">ApprovalStatus</a>| This field specifies Ad Group Approval status.| Opt |
| mediaApprovalStatuses| enum <a href="./MediaApprovalStatus.md">MediaApprovalStatus</a>| The media approval status.| Opt |
| entityTypes| enum <a href="./EntityType.md">EntityType</a>| This field specifies Entity.| Opt |
| downloadBulkJob| <a href="./DownloadBulkJob.md">DownloadBulkJob</a>| Assignment of bulk download jobs.| Opt |
| downloadType| enum <a href="./BulkDownloadType.md">BulkDownloadType</a>| The download type.| Req |
| lang| enum <a href="./BulkLang.md">BulkLang</a>| This field indicates language.| Opt |
| output| enum <a href="./BulkOutput.md">BulkOutput</a>| This field specifies output format.| Req |
| encoding| enum <a href="./BulkEncoding.md">BulkEncoding</a>| This field specifies character code for bulk sheet.| Req |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

# DownloadBulkJob
DownloadBulkJob serves bulk process definitions.
### Service
+ [BulkService](../../services/BulkService.md)

### Namespace
[BulkService#Namespace](../../services/BulkService.md#namespace)

| Field | Data Type | Description | 
|---|---|---|
| accountId| xsd:long| The account ID. |
| downloadBulkJobId| xsd:long| The download bulk ID. |
| downloadBulkJobName| xsd: string| The download bulk name. |
| downloadBulkUserName| xsd: string| The download user name. |
| downloadBulkStartDate| xsd: string| The download start date (YYYY-MM-DDTHH:MI:SS+9:00). |
| downloadBulkEndDate| xsd: string| The download end date (YYYY-MM-DDTHH:MI:SS+9:00). |
| downloadJobStatus| enum <a href="DownloadBulkJobStatus.md">DownloadBulkJobStatus</a>| The download status. |
| progress| xsd: int| Displays progress in integers from 1 to 100. |
| downloadBulkDownloadUrl| xsd: string| The download URL. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

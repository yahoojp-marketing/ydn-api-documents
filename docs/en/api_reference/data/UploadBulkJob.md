# UploadBulkJob
UploadBulkJob serves the content of bulk upload job.
### Service
+ [BulkService](../services/BulkService.md)

| Field | Data Type | Description | 
|---|---|---|
| accountId| xsd:long| The account ID. |
| uploadBulkJobId| xsd:long| The bulk id of bulk upload. |
| uploadBulkJobName| xsd: string| The bulk name of bulk upload. |
| uploadBulkUserName| xsd: string| The user name of bulk upload. |
| uploadBulkStartDate| xsd: string| The start date of bulk upload. (YYYY-MM-DDTHH:MI:SS+9:00) |
| uploadBulkEndDate| xsd: string| The dnd date of bulk upload. (YYYY-MM-DDTHH:MI:SS+9:00) |
| uploadJobStatus| enum <a href="../data/UploadBulkJobStatus.md">UploadBulkJobStatus</a>| The status of bulk upload. |
| processingItemsCount|enum <a href="../data/ProcessingItemsCount.md">ProcessingItemsCount</a> | The number of process of bulk upload. |
| progress| xsd: int| The parcentage of bulk upload process. It is integral from 1 to 100. |
| downloadBulkUploadFileUrl| xsd: string| The file URL of bulk upload. |
| downloadBulkUploadErrorFileUrl| xsd: string| The error file URL of bulk upload. |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

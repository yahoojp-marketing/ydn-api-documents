

# FeedDataRecord

FeedDataRecord object retains status of uploaded item list(file format).

### Service

+ [FeedDataService](../../services/FeedDataService.md)

### Namespace

[FeedDataService#Namespace](../../services/FeedDataService.md#namespace)

| Field | Type | Description | response |
| ----- | ---- | ----------- | -------- |
| accountId | xsd:long | Account ID. | yes | |
| feedHolderId | xsd:long | FeedHolder ID. | yes | |
| itemListUploadId | xsd:long | Uploaded item list ID. | yes | |
| itemListUploadType | enum [ItemListUploadType](./ItemListUploadType.md) | Type of uploaded item list. | yes | |
| itemListUploadStatus | enum [FileUploadStatus](./FileUploadStatus.md) | Status of uploaded item list. | yes | |
| uploadDate | xsd:string | Upload date.<br>Format: yyyyMMdd | yes | |
| completeDate | xsd:string | Complete date.<br>Format: yyyyMMdd | yes | |
| errorCount | xsd:long | Number of item list with error. | yes | |
| errorRate | xsd:double | Error rate. | yes | |
| errorListDownloadUrl | xsd:string | Temporary download URL of item list with error. | yes | |
| itemListUploadSrc | enum [FileUploadSrc](./FileUploadSrc.md) | File upload source. | yes | |
| isDebug | xsd:boolean | "true" means to run in debug mode. | yes | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

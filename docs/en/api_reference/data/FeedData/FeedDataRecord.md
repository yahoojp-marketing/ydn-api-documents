# FeedDataRecord
FeedDataRecord object retains status of uploaded item list(file format).

### Service
+ [FeedDataService](../../services/FeedDataService.md)

### Namespace
[FeedDataService#Namespace](../../services/FeedDataService.md#namespace)

| Field | Type | Description |
|---|---|---|
| accountId| xsd:long| Account ID. |
| feedHolderId| xsd:long| FeedHolder ID. |
| itemListUploadId| xsd:long| Uploaded item list ID. |
| itemListUploadType| [ItemListUploadType](ItemListUploadType.md)| Type of uploaded item list. |
| itemListUploadStatus| [FileUploadStatus](FileUploadStatus.md)| Status of uploaded item list. |
| uploadDate| xsd:string| Upload date.<br>Format:yyyyMMdd |
| errorCount| xsd:long| Number of item list with error. |
| errorListDownloadUrl| xsd:long| Temporary download URL of item list with error. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

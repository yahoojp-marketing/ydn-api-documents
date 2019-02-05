# FeedDataSelector
FeedDataSelector object retains search condition of getUploadStatus operation.

### Service
+ [FeedDataService](../../services/FeedDataService.md)

### Namespace
[FeedDataService#Namespace](../../services/FeedDataService.md#namespace)

| Field | Type | Description |
|---|---|---|
| accountId| xsd: long| Account ID |
| feedHolderIds[1..200] |  xsd:long| FeedHolderID |
| itemListUploadIds[1..200] |  xsd:long| Uploaded item list ID. |
| uploadStatuses[] | [FileUploadStatus](FileUploadStatus.md) | Status of file upload.
| dateRange | [FileUploadDataRange](FileUploadDataRange.md) | Specify term of file upload date.
| paging| [Paging](../Common/Paging.md)| Specify paging specific parameters for paging the return list.  |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>



# FeedDataSelector

FeedDataSelector object retains search condition of getUploadStatus operation.

### Service

+ [FeedDataService](../../services/FeedDataService.md)

### Namespace

[FeedDataService#Namespace](../../services/FeedDataService.md#namespace)

| Field | Type | Description | response |
| ----- | ---- | ----------- | -------- |
| accountId | xsd:long | Account ID | yes | |
| feedHolderIds[1..200] | xsd:long | FeedHolderID | yes | |
| itemListUploadIds[1..200] | xsd:long | Uploaded item list ID. | yes | |
| uploadStatuses[] | enum [FileUploadStatus](./FileUploadStatus.md) | Status of file upload. | yes | |
| dateRange | [FileUploadDateRange](./FileUploadDateRange.md) | Specify term of file upload date. | yes | |
| paging | [Paging](../Common/Paging.md) | Specify paging specific parameters for paging the return list. | yes | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

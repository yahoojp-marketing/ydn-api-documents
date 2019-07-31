

# FeedDataSelector

getUploadStatus操作の検索条件を保持するオブジェクト

### Service

+ [FeedDataService](../../services/FeedDataService.md)

### Namespace

[FeedDataService#Namespace](../../services/FeedDataService.md#namespace)

| Field | Type | Description | response |
| ----- | ---- | ----------- | -------- |
| accountId | xsd:long | アカウントID | yes | |
| feedHolderIds[1..200] | xsd:long | FeedHolderID | yes | |
| itemListUploadIds[1..200] | xsd:long | アップロードした商品情報ID | yes | |
| uploadStatuses[] | enum [FileUploadStatus](./FileUploadStatus.md) | ファイルアップロード状況 | yes | |
| dateRange | [FileUploadDateRange](./FileUploadDateRange.md) | ファイルアップロード日の期間指定 | yes | |
| paging | [Paging](../Common/Paging.md) | ページング情報 | yes | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

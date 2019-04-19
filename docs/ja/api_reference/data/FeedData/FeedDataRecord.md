# FeedDataRecord
FeedDataRecordオブジェクトは、アップロードした商品情報(ファイル形式)の状態を保持する。

### Service
+ [FeedDataService](../../services/FeedDataService.md)

### Namespace
[FeedDataService#Namespace](../../services/FeedDataService.md#namespace)

| Field | Type | Description |
|---|---|---|
| accountId| xsd:long| アカウントID |
| feedHolderId| xsd:long| FeedHolderを識別するId |
| itemListUploadId| xsd:long| アップロードした商品情報を識別するID |
| itemListUploadType| [ItemListUploadType](ItemListUploadType.md)| 取り込み種別 |
| itemListUploadStatus| [FileUploadStatus](FileUploadStatus.md)| 商品情報の処理状態 |
| uploadDate| xsd:string| アップロード日(yyyyMMdd) |
| errorCount| xsd:long| 不備がある商品情報の件数 |
| errorListDownloadUrl| xsd:long| 不備がある商品情報をダウンロードする一時URL |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

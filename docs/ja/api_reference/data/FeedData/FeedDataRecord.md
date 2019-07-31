

# FeedDataRecord

FeedDataRecordオブジェクトは、アップロードした商品情報(ファイル形式)の状態を保持する。

### Service

+ [FeedDataService](../../services/FeedDataService.md)

### Namespace

[FeedDataService#Namespace](../../services/FeedDataService.md#namespace)

| Field | Type | Description | response |
| ----- | ---- | ----------- | -------- |
| accountId | xsd:long | アカウントID | yes | |
| feedHolderId | xsd:long | FeedHolderを識別するId | yes | |
| itemListUploadId | xsd:long | アップロードした商品情報を識別するID | yes | |
| itemListUploadType | enum [ItemListUploadType](./ItemListUploadType.md) | 取り込み種別 | yes | |
| itemListUploadStatus | enum [FileUploadStatus](./FileUploadStatus.md) | 商品情報の処理状態 | yes | |
| uploadDate | xsd:string | アップロード日(yyyyMMdd) | yes | |
| completeDate | xsd:string | 取り込み完了日(yyyyMMdd) | yes | |
| errorCount | xsd:long | 不備がある商品情報の件数 | yes | |
| errorRate | xsd:double | エラー率 | yes | |
| errorListDownloadUrl | xsd:string | 不備がある商品情報をダウンロードする一時URL | yes | |
| itemListUploadSrc | enum [FileUploadSrc](./FileUploadSrc.md) | ファイルアップロード元 | yes | |
| isDebug | xsd:boolean | trueはデバッグモードでの実行を意味します。 | yes | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

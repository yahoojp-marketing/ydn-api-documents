# UploadBulkJob
UploadBulkJobオブジェクトは、一括アップロードジョブの内容を表します。
### Service
+ [BulkService](../services/BulkService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| accountId| xsd:long| アカウントIDです。 |
| uploadBulkJobId| xsd:long| 一括アップロードのバルクIDです。 |
| uploadBulkJobName| xsd: string| 一括アップロードのバルク名です。 |
| uploadBulkUserName| xsd: string| 一括アップロードのユーザー名です。 |
| uploadBulkStartDate| xsd: string| 一括アップロードの開始日時(YYYY-MM-DDTHH:MI:SS+9:00)です。 |
| uploadBulkEndDate| xsd: string| 一括アップロードの完了日時(YYYY-MM-DDTHH:MI:SS+9:00)です。 |
| uploadJobStatus|enum <a href="../data/UploadBulkJobStatus.md">UploadBulkJobStatus</a>| 一括アップロードのステータスです。 |
| processingItemsCount| enum <a href="../data/ProcessingItemsCount.md">ProcessingItemsCount</a>| 一括アップロードの処理数です。 |
| progress| xsd: int| 作業進捗率を示します。1-100の整数です。 |
| downloadBulkUploadFileUrl| xsd: string| 一括アップロードのファイルURLです。 |
| downloadBulkUploadErrorFileUrl| xsd: string| 一括アップロードのエラーファイルURLです。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

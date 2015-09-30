# DownloadBulkJob
DownloadBulkJobは、バルク処理の定義を表します。
### Service
+ [BulkService](../services/BulkService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| accountId| xsd:long| アカウントIDです。 |
| downloadBulkJobId| xsd:long| ダウンロードのバルクIDです。 |
| downloadBulkJobName| xsd: string| ダウンロードのバルク名です。 |
| downloadBulkUserName| xsd: string| ダウンロードのユーザー名です。 |
| downloadBulkStartDate| xsd: string| ダウンロードの開始日時(YYYY-MM-DDTHH:MI:SS+9:00)です。 |
| downloadBulkEndDate| xsd: string| ダウンロードの完了日時(YYYY-MM-DDTHH:MI:SS+9:00)です。 |
| downloadJobStatus| enum <a href="../data/DownloadBulkJobStatus.md">DownloadBulkJobStatus</a>| ダウンロードのステータスです。 |
| progress| xsd: int| 進捗率を示します。1-100の整数です。 |
| downloadBulkDownloadUrl| xsd: string| ダウンロードURLです。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

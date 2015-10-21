# BulkDownloadStatusSelector
The BulkDownloadStatusSelector object serves bulk download status.
### Service
+ [BulkService](../services/BulkService.md)

| Field | Data Type | Description | Restriction | 
|---|---|---|---|
| accountId| xsd: long| The account ID.| Req |
| downloadBulkJobIds| xsd: long[]| The bulk ID for downloads retrieved with getBulkDownload. If selected with more than 200 downloads,  error will be returned. | Req |
| downloadBulkJobStatus| enum <a href="./DownloadBulkJobStatus.md">DownloadBulkJobStatus</a>[]| The bulk process status. <br>                        If none are selected, status is shown for all. | Opt |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

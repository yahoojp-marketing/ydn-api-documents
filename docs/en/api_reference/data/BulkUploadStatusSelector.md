# BulkUploadStatusSelector
BulkUploadStatusSelectorobject is a container for storing operation result of upload.
### Service
+ [BulkService](../services/BulkService.md)

| Field | Data Type | Description | 制限 | 
|---|---|---|---|
| accountId| xsd: long| The account ID.| Req |
| uploadBulkJobIds| xsd: long[]| Bulk job ID for uploading.| Opt |
| uploadBulkJobStatus| enum <a href="./UploadBulkJobStatus.md">uploadBulkJobStatus</a>[]| Bulk job status for uploading.<br>                        All status will be output if not specified.| Req |
| lang| enum　<a href="./BulkLang.md">BulkLang</a>| Indicate language for bulk error file.| Opt |
| output| enum　<a href="./BulkOutput.md">BulkOutput</a>| Indicate output format for bulk error file.| Req |
| encoding| enum　<a href="./BulkEncoding.md">BulkEncoding</a>| Indicate character in bulk error file.| Req |
| paging| <a href="./Paging.md">Paging</a>| The page that is being back as a respons.| Opt |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

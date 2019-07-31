# BulkUploadStatusSelector
BulkUploadStatusSelecto object contains a set of criteria (parameters) for getBulkUploadStatus method.

### Service
+ [BulkService](../../services/BulkService.md)

### Namespace
[BulkService#Namespace](../../services/BulkService.md#namespace)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>get</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>Account ID</td>
  <td>Required</td>
 </tr>
 <tr>
  <td>uploadBulkJobIds[1...500]</td>
  <td>xsd:long</td>
  <td>Job ID of bulk upload</td>
  <td>Required</td>
 </tr>
 <tr>
  <td>uploadBulkJobStatus[0...5]</td>
  <td>enum　<a href="./UploadBulkJobStatus.md">UploadBulkJobStatus</a></td>
  <td>Job status of bulk upload<br>&lowast;All status will be output if not specified.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>paging</td>
  <td><a href="../Common/Paging.md">Paging</a></td>
  <td>Page returned as response</td>
  <td>Optional</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

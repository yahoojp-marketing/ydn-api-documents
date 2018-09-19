# UploadBulkJob
UploadBulkJob describes the content of bulk upload job.
### Service
+ [BulkService](../../services/BulkService.md)

### Namespace
[BulkService#Namespace](../../services/BulkService.md#namespace)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>add（upload）</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>Account ID</td>
  <td>yes</td>
  <td>Required</td>
 </tr>
 <tr>
  <td>uploadBulkJobId</td>
  <td>xsd:long</td>
  <td>Job ID of bulk upload</td>
  <td>yes</td>
  <td>Ignore</td>
 </tr>
  <tr>
  <td>uploadBulkJobName</td>
  <td>xsd:string</td>
  <td>Job name of bulk upload</td>
  <td>yes</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>uploadBulkUserName</td>
  <td>xsd:string</td>
  <td>User name of bulk upload</td>
  <td>yes</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>uploadBulkStartDate</td>
  <td>xsd:string</td>
  <td>Start date of bulk upload</td>
  <td>yes</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>uploadBulkEndDate</td>
  <td>xsd:string</td>
  <td>End date of bulk upload</td>
  <td>yes</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>uploadBulkJobStatus</td>
  <td>enum <a href="UploadBulkJobStatus.md">UploadBulkJobStatus</a></td>
  <td>Job Status of bulk upload</td>
  <td>yes</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>processingItemsCount</td>
  <td><a href="ProcessingItemsCount.md">ProcessingItemsCount</a></td>
  <td>Number of process of bulk upload</td>
  <td>yes</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>progress</td>
  <td>xsd: int</td>
  <td>Percentage of bulk upload process</td>
  <td>yes</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>downloadBulkUploadFileUrl</td>
  <td>xsd:string</td>
  <td>URL to get the uploaded file</td>
  <td>yes</td>
  <td>Ignore</td>
 </tr>
 </table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

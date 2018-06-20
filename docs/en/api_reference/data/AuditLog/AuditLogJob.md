# AuditLogJob
AuditLogJob object is a container for storing the download operation history job information.
 
### Service
+ [AuditLogService](../../services/AuditLogService.md)

### Namespace
[AuditLogService#Namespace](../../services/AuditLogService.md#namespace)
 
<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>getDownload</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>The account ID.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>auditLogJobId</td>
  <td>xsd:long</td>
  <td>The operation history job ID.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>auditLogJobName</td>
  <td>xsd:string</td>
  <td>The operation history job name.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>auditLogJobUserName</td>
  <td>xsd:string</td>
  <td>The user name who executes the operation history job.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>auditLogJobStartDate</td>
  <td>xsd:string</td>
  <td>The job start date (YYYY-MM-DDTHH:MI:SS+9:00).</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>auditLogJobEndDate</td>
  <td>xsd:string</td>
  <td>The job end date (YYYY-MM-DDTHH:MI:SS+9:00).</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>auditLogJobStatus</td>
  <td>enum <br><a href="./AuditLogDownloadJobStatus.md">AuditLogDownloadJobStatus</a></td>
  <td>The job status.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>progress</td>
  <td>xsd:int</td>
  <td>Displays progress in integers from 1 to 100.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
  <tr>
  <td>downloadAuditLogDownloadUrl</td>
  <td>xsd:string</td>
  <td>The URL to get download job result.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>
 
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">
<img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" />
</a><br />
この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">
クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>


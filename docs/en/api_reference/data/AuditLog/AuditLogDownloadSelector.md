# AuditLogDownloadSelector
AuditLogDownloadSelector object is a container for storing the download job information for getDownload method (execution parameter).
 
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
  <td>Account ID.</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>campaignIds[1...500]</td>
  <td>xsd:long</td>
  <td>Campaign ID of the download object.</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>updateSources[1...2]</td>
  <td>enum <br><a href="./AuditLogUpdateSource.md">AuditLogUpdateSource</a></td>
  <td>Update source of the download object.</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>dateRange</td>
  <td><a href="./AuditLogDateRange.md">AuditLogDateRange</a></td>
  <td>Date range of the download object.</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>auditLogJob</td>
  <td><a href="./AuditLogJob.md">AuditLogJob</a></td>
  <td>Job information of the download object.</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>lang</td>
  <td>enum <br><a href="./AuditLogLang.md">AuditLogLang</a></td>
  <td>Language setting of the download information.</td>
  <td>-</td>
  <td>Optional</td>
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


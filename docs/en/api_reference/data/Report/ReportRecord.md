# ReportRecord
ReportRecord object serves report information.

### Service
+ [ReportService](../../services/ReportService.md)

### Namespace
[ReportService#Namespace](../../services/ReportService.md#namespace)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>add</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>Account ID</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>reportJobId</td>
  <td>xsd:long</td>
  <td>Report Job Id</td>
  <td>yes<br>&lowast;Returned only when using remove operation.
  </td>
  <td>Ignore</td>
  <td>Required<br>NonUpdatable</td>
 </tr>
 <tr>
  <td>reportId</td>
  <td>xsd:long</td>
  <td>Report Id</td>
  <td>yes</td>
  <td>Required</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>reportName</td>
  <td>xsd:string</td>
  <td>Report Name</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>requestTime</td>
  <td>xsd:string</td>
  <td>The date and time of Job request</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>completeTime</td>
  <td>xsd:string</td>
  <td>The date and time of Job completion</td>
  <td>yes<br>&lowast;Returned after completion of job registration.</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>dateRangeType</td>
  <td>enum <a href="./ReportDateRangeType.md">ReportDateRangeType</a></td>
  <td>The type of report target period</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>dateRange</td>
  <td><a href="./ReportDateRange.md">ReportDateRange</a></td>
  <td>Report Target Period</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>status</td>
  <td>enum <a href="./ReportJobStatus.md">ReportJobStatus</a></td>
  <td>Job Status</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>jobErrorDetail</td>
  <td>xsd:string</td>
  <td>Job Error Detail</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>reportDownloadUrl</td>
  <td>xsd:string</td>
  <td>Download URL for report<br>&lowast;The value is set if the status is COMPLETED</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

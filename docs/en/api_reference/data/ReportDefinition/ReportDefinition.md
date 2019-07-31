# ReportDefinition
The ReportDefinition object serves report definitions.

### Service
+ [ReportDefinitionService](../../services/ReportDefinitionService.md)

### Namespace
[ReportDefinitionService#Namespace](../../services/ReportDefinitionService.md#namespace)

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
  <td>reportJobStatus</td>
  <td>enum <a href="./ReportJobStatus.md">ReportJobStatus</a></td>
  <td>Job Status</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>reportJobErrorDetail</td>
  <td>xsd:string</td>
  <td>Job Error Detail</td>
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
  <td>reportDownloadURL</td>
  <td>xsd:string</td>
  <td>Download URL for report<br>&lowast;The value is set if the status is COMPLETED</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>reportName</td>
  <td>xsd:string</td>
  <td>Report name.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>dateRangeType</td>
  <td>enum<br><a href="./ReportDateRangeType.md">ReportDateRangeType</a></td>
  <td>Compilation target period for a defined report.</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>dateRange</td>
  <td>enum<br><a href="./ReportDateRange.md">ReportDateRange</a></td>
  <td>The date range for report compilation.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>frequencyRange</td>
  <td>enum<br><a href="./ReportFrequencyRange.md">ReportFrequencyRange</a></td>
  <td>Performance range of frequency.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>filters[0..6]</td>
  <td><a href="./ReportFilter.md">ReportFilter</a></td>
  <td>Filter of report.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>sortFields[]</td>
  <td>xsd:string</td>
  <td>Can select the fields to sort.<br>
  ・Up to select 5 types of field to sort.<br>
  ・Add "+" before the field name to arrange in ascending order.<br>
  ・Add "-" before the field name to arrange in descending order.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>fields[]</td>
  <td>xsd:string</td>
  <td>Select the fields. <br>Confirm the available field name from <a href="../../appendix/reports.md">Report Fields Page</a>.</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>format</td>
  <td>enum<br><a href="./ReportDownloadFormat.md">ReportDownloadFormat</a></td>
  <td>File format for the defined download report.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>encode</td>
  <td>enum<br><a href="./ReportDownloadEncode.md">ReportDownloadEncode</a></td>
  <td>Encoding for the defined download report.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>compress</td>
  <td>enum<br><a href="./ReportZip.md">ReportZip</a></td>
  <td>Whether or not a compressed file exists for the defined report.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>language</td>
  <td>enum<br><a href="./ReportLang.md">ReportLang</a></td>
  <td>Reporting language for the defined column name.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

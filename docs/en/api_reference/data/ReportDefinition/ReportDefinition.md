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
 <tr>
  <td>reportId</td>
  <td>xsd:long</td>
  <td>Report ID.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Requirement<br>(Not updatable)</td>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>Account ID.</td>
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
  <td>zip</td>
  <td>enum<br><a href="./ReportZip.md">ReportZip</a></td>
  <td>Whether or not a compressed file exists for the defined report.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>lang</td>
  <td>enum<br><a href="./ReportLang.md">ReportLang</a></td>
  <td>Reporting language for the defined column name.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>intervalType</td>
  <td>enum<br><a href="./ReportIntervalType.md">ReportIntervalType</a></td>
  <td>Selects a timing (interval type) to create a report.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>specifyDay</td>
  <td>xsd:int</td>
  <td>Selects day to create a report.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>addTemplate</td>
  <td>enum<br><a href="./ReportAddTemplate.md">ReportAddTemplate</a></td>
  <td>Set the definition for a template flag.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

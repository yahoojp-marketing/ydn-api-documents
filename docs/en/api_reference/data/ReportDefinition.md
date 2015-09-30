# ReportDefinition
The ReportDefinition object serves report definitions.
### Service
+ [ReportDefinitionService](../services/ReportDefinitionService.md)

| Field | Data Type | maxOccurs | minOccurs | response | add | set | remove | Description | 
|---|---|---|---|---|---|---|---|---|
| reportId| long| 1| 0| ○| Ignore| -| Requirement<br>(Not updatable)| Report definition ID. |
| accountId| long| 1| 0| ○| Ignore| -| Ignore| Account ID. |
| reportName| string| 1| 0| ○| Optional| -| Ignore| Report name.| 
| dateRangeType| enum <a href="./ReportDateRangeType.md">ReportDateRangeType</a>| 1| 0| ○| Requirement| -| Ignore| Compilation target period for a defined report. |
| dateRange| <a href="./ReportDateRange.md">ReportDateRange</a>| 1| 0| ○| Optional| -| Ignore| The date range for report compilation to be set by user.<br>This item is required when ReportDateRangeType is set as "CUSTOM_DATE".|
| frequencyRange|  enum <a href="./ReportDateRangeType.md">ReportDateRangeType</a>| 1| 0| ○| Optional| -|Ignore|Performance range of frequency.。 |
| sortFields[]| string| unbounded| 0| ○| Optional| -| Ignore| Can select the fields to sort.<br>・Up to select 5 types of field to sort.<br>・Add "+" before the field name to arrange in ascending order.<br>・Add "-" before the field name to arrange in descending order. |
| fields[]| string| unbounded| 0| ○| Requirement| -| Ignore|Select the fields. <br>Confirm the available field name from <a href="../appendix/reports.md">Report Fields Page</a>. |
| format| enum <a href="./ReportDownloadFormat.md">ReportDownloadFormat</a>| 1| 0| ○| Optional| -| Ignore| File format for the defined download report. |
| encode| enum <a href="./ReportDownloadEncode.md">ReportDownloadEncode</a>| 1| 0| ○| Optional| -| Ignore| Encoding for the defined download report. |
| zip| enum <a href="./ReportZip.md">ReportZip</a>| 1| 0| ○| Optional| -| Ignore| Whether or not a compressed file exists for the defined report. |
| lang| enum <a href="./ReportLang.md">ReportLang</a>| 1| 0| ○| Optional| -| Ignore| Language for the defined column name. |
| intervalType| enum <a href="./ReportIntervalType.md">ReportIntervalType</a>| 1| 0| ○| Optional| -| Ignore| Selects day to create report. |
| specifyDay| int| 1| 0| ○| Optional| -| Ignore| Selects day for report. |
| addTemplate| enum <a href="./ReportAddTemplate.md">ReportAddTemplate</a>| 1| 0| ○| Optional| -| Ignore| Set the definition for a template flag.|
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

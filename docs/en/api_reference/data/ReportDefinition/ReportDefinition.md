

# ReportDefinition

The ReportDefinition object serves report definitions.<br>
TC-CI-00000073 is the geo code that shows "Other". It cannot be obtained by getGeographicLocation of DictionaryService, and cannot be specified as geo targeting.

### Service

+ [ReportDefinitionService](../../services/ReportDefinitionService.md)

### Namespace

[ReportDefinitionService#Namespace](../../services/ReportDefinitionService.md#namespace)

| Field | Type | Description | response | get | add | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| accountId | xsd:long | Account ID | yes | - | Ignore | Ignore | |
| reportJobId | xsd:long | Report Job Id | yes | - | Ignore | Requirement<br>NonUpdatable | |
| reportJobStatus | enum [ReportJobStatus](./ReportJobStatus.md) | Job Status | yes | - | Ignore | Ignore | |
| reportJobErrorDetail | xsd:string | Job Error Detail | yes | - | Ignore | Ignore | |
| requestTime | xsd:string | The date and time of Job request | yes | - | Ignore | Ignore | |
| completeTime | xsd:string | The date and time of Job completion | yes | <br>*Returned after job registration is complete. | Ignore | Ignore | |
| reportDownloadUrl | xsd:string | Report download url. | yes | - | Ignore | Ignore | |
| reportName | xsd:string | Report name. | yes | - | Optional | Ignore | |
| dateRangeType | enum [ReportDateRangeType](./ReportDateRangeType.md) | Compilation target period for a defined report. | yes | - | Requirement | Ignore | |
| dateRange | [ReportDateRange](./ReportDateRange.md) | The date range for report compilation. | yes | - | Optional | Ignore | |
| frequencyRange | enum [ReportFrequencyRange](./ReportFrequencyRange.md) | Performance range of frequency. | yes | - | Optional | Ignore | |
| filters[0..6] | [ReportFilter](./ReportFilter.md) | Filter of report. | yes | - | Optional | Ignore | |
| sortFields[] | xsd:string | Can select the fields to sort.<br>・Up to select 5 types of field to sort.<br>・Add &#34;+&#34; before the field name to arrange in ascending order.<br>・Add &#34;-&#34; before the field name to arrange in descending order. | yes | - | Optional | Ignore | |
| fields[] | xsd:string | Select the fields.<br>Confirm the available field name from [Report Fields Page](../../appendix/reports.md). | yes | - | Requirement | Ignore | |
| format | enum [ReportDownloadFormat](./ReportDownloadFormat.md) | File format for the defined download report. | yes | - | Optional | Ignore | |
| encode | enum [ReportDownloadEncode](./ReportDownloadEncode.md) | Encoding for the defined download report. | yes | - | Optional | Ignore | |
| compress | enum [ReportZip](./ReportZip.md) | Whether or not a compressed file exists for the defined report. | yes | - | Optional | Ignore | |
| language | enum [ReportLang](./ReportLang.md) | Reporting language for the defined column name. | yes | - | Optional | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

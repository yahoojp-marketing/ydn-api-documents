# ReportRecord
The ReportRecord object serves report information.
### Service
+ [ReportService](../services/ReportService.md)

| Field | Data Type | Description | ADD | REMOVE | 
|---|---|---|---|---|
| accountId| xsd: long| The account ID.| -| - |
| reportJobId| xsd: long| The job ID.| -| Req<br>                            notupdatable |
| reportId| xsd: long| The report ID.| Req| - |
| reportName| xsd: string| The report name.| -| - |
| requestTime| xsd: string| The request time stamp.| -| - |
| completeTime| xsd: string| The job completion date and time.| -| - |
| dateRangeType| enum <a href="../data/ReportDateRangeType.md">ReportDateRangeType</a>| The report target period.| -| - |
| dateRange| <a href="../data/ReportDateRange.md">ReportDateRange</a>| The report target period.| -| - |
| status| enum <a href="../data/ReportJobStatus.md">ReportJobStatus</a>| The report process status.| -| - |
| jobErrorDetail| string| Job error details| Ignore| Ignore |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

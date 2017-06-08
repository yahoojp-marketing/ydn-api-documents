# ReportClosedDateRecord
ReportClosedDateRecord object serves the details of end date for report compilation.

### Service
+ [ReportService](../services/ReportService.md)

| Field | Data Type | Description | 
|---|---|---|
| key| xsd: string| Key of end date for report compilation. <br>* Either of elements below will return.<br>- FREQ_REPORT_CLOSED_DATE: Retrieve recent data of Frequency Report.<br>- REPORT_CLOSED_DATE：Retrieve recent data of performance report.|
| closedDate| xsd: string| End date of reporting. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

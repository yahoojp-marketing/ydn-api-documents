# ReportDateRangeType (enum)
ReportDateRangeType serves the report compilation target period.
### Service
+ [ReportDefinitionService](../../services/ReportDefinitionService.md)

### Namespace
[ReportDefinitionService#Namespace](../../services/ReportDefinitionService.md#namespace)

| Value | Description | 
|---|---|
| CUSTOM_DATE| Reports are generated for the date range specified byDateRange. If select CUSTOM_DATE, DatRange must be input. |
| YESTERDAY| Reports are generated for yesterday only. |
| LAST_7_DAYS| Reports are generated for the last 7 days not including today. |
| LAST_WEEK| Reports are generated for the seven-day period starting with previous Monday. |
| LAST_BUSINESS_WEEK| Reports are generated for the 5 day business week starting with previous Monday. |
| LAST_14_DAYS| Reports are generated for the last 14 days not including today. |
| LAST_30_DAYS| Reports are generated for the last 30 days not including today. |
| THIS_MONTH| Reports are generated for all days in the current month not including today. |
| LAST_MONTH| Reports are generated for all days in the previous month. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

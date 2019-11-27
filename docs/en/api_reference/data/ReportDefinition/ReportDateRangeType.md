

# ReportDateRangeType (enum)

ReportDateRangeType serves the report compilation target period.

#### Service

+ [ReportDefinitionService](../../services/ReportDefinitionService.md)

#### Namespace

[ReportDefinitionService#Namespace](../../services/ReportDefinitionService.md#namespace)

| Enumeration  |       Type       |          Description          |
| ------------ | ---------------- | ----------------------------- |
| CUSTOM_DATE | xsd:string | Reports are generated for the date range specified byDateRange. If select CUSTOM_DATE, DateRange must be input.<br>* CUSTOM_DATE cannot be specified if ReportType = REACH. |
| YESTERDAY | xsd:string | Reports are generated for yesterday only. |
| LAST_7_DAYS | xsd:string | Reports are generated for the last 7 days not including today. |
| LAST_WEEK | xsd:string | Reports are generated for the seven-day period starting with previous Monday. |
| LAST_BUSINESS_WEEK | xsd:string | Reports are generated for the 5 day business week starting with previous Monday. |
| LAST_14_DAYS | xsd:string | Reports are generated for the last 14 days not including today. |
| LAST_30_DAYS | xsd:string | Reports are generated for the last 30 days not including today. |
| THIS_MONTH | xsd:string | Reports are generated for all days in the current month not including today. |
| LAST_MONTH | xsd:string | Reports are generated for all days in the previous month. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

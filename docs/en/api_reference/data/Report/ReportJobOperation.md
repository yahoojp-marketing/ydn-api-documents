# ReportOperation
The ReportOperation object serves operation target report and operation content.
### Service
+ [ReportService](../../services/ReportService.md)

### Namespace
[ReportService#Namespace](../../services/ReportService.md#namespace)

| Field | Data Type | Description | Restriction |
|---|---|---|---|
| Operation(inherited)||||
| operator| enum Operator| The operator that displays processes.| Req |
| ReportOperation||||
| accountId| xsd: long| The account ID.| Req |
| operand| <a href="ReportRecord.md">ReportRecord[]</a>| The ReportRecord object arrangments. Process target report information is included in the arrangements.| Req |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

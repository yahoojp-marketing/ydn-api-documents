# ReportDefinitionOperation
The ReportDefinitionOperation object serves operation target report definitions and operation content.
### Service
+ [ReportDefinitionService](../services/ReportDefinitionService.md)

| Field | Data Type | Description | Restriction | 
|---|---|---|---|
| Operation(inherited)||||
| operator| enum <a href="./Operator.md%0D%0A">Operator</a>| The operator that displays processes.| Req |
| ReportDefinitionOperation||||
| accountId| xsd: long| The account ID.| Req |
| operand| <a href="../data/ReportDefinition.md">ReportDefinition</a>| The Report definition object.| Req |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

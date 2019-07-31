# ReportDefinitionSelector
ReportDefinitionSelector object serves the report definition for the target of operation.
### Service
+ [ReportDefinitionService](../../services/ReportDefinitionService.md)

### Namespace
[ReportDefinitionService#Namespace](../../services/ReportDefinitionService.md#namespace)

| Field | Data Type | Description | Restriction |
|---|---|---|---|
| accountId| xsd: long| Account ID.| Req |
| reportJobIds[]| xsd: long| Report ID.| Opt |
| reportJobStatuses[]| xsd: [ReportJobStatus](./ReportJobStatus.md)| Report Job Status. | Opt |
| paging| <a href="../Common/Paging.md">Paging</a>| Page returned as reposnse.| Opt |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

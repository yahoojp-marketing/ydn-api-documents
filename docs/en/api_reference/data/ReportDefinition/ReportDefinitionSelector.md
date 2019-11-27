

# ReportDefinitionSelector

ReportDefinitionSelector object serves the report definition for the target of operation.

### Service

+ [ReportDefinitionService](../../services/ReportDefinitionService.md)

### Namespace

[ReportDefinitionService#Namespace](../../services/ReportDefinitionService.md#namespace)

| Field | Type | Description | response |
| ----- | ---- | ----------- | -------- |
| accountId | xsd:long | Account ID. | yes | |
| reportJobIds[] | xsd:long | Report ID. | yes | |
| reportJobStatuses[] | enum [ReportJobStatus](./ReportJobStatus.md) | Report Job Status. | yes | |
| paging | [Paging](../Common/Paging.md) | Page returned as reposnse. | yes | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

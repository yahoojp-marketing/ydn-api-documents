

# ReportFilter

ReportFilterオブジェクトは、フィルター定義を表します。

### Service

+ [ReportDefinitionService](../../services/ReportDefinitionService.md)

### Namespace

[ReportDefinitionService#Namespace](../../services/ReportDefinitionService.md#namespace)

| Field | Type | Description | response | get | add | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| field | xsd:string | フィルター対象となるフィールドです。<br>※getReportFieldsのレスポンスで「filterable=true」<br>のフィールドのみ指定可能 | yes | - | Requirement | - | |
| operator | enum [FilterOperator](./FilterOperator.md) | フィルター演算子です。 | yes | - | Requirement | - | |
| values[1..10] | xsd:string | 条件値です。 | yes | - | Requirement | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

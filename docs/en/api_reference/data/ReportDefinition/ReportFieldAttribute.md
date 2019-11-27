

# ReportFieldAttribute

ReportFieldAttribute holds the result (1 FieldEntity) of getReportFields method.

### Service

+ [ReportDefinitionService](../../services/ReportDefinitionService.md)

### Namespace

[ReportDefinitionService#Namespace](../../services/ReportDefinitionService.md#namespace)

| Field | Type | Description | response |
| ----- | ---- | ----------- | -------- |
| fieldName | xsd:string | Field Name | yes | |
| displayFieldNameJA | xsd:string | Field Name for the Downloaded Report (JA) | yes | |
| displayFieldNameEN | xsd:string | Field Name for the Downloaded Report (EN) | yes | |
| xmlAttributeName | xsd:string | XML attribute for the Downloaded Report | yes | |
| fieldType | xsd:string | Field type (number, string, ENUM, etc.) | yes | |
| filterable | xsd:boolean | Whether the field filter can be specified or not. (true: Filter can be specified.)  | yes | |
| impossibleCombinationFields | xsd:string | Invalid field combinations. | yes | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

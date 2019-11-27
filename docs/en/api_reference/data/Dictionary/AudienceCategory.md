

# AudienceCategory

AudienceCategory object contains audience category information.

### Service

+ [DictionaryService](../../services/DictionaryService.md)

### Namespace

[DictionaryService#Namespace](../../services/DictionaryService.md#namespace)

| Field | Type | Description | response |
| ----- | ---- | ----------- | -------- |
| code | xsd:string | Category code | yes | |
| name | xsd:string | Sub-category name | yes | |
| fullName | xsd:string | Category name (A formal name including category name and sub category name.) | yes | |
| reach | xsd:long | Reach record number | yes | |
| categoryType | enum [AudienceCategoryType](./AudienceCategoryType.md) | Category type | yes | |
| child[] | [AudienceCategory](./AudienceCategory.md) | Child category | yes | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>



# AudienceCategory

AudienceCategoryオブジェクトは、オーディエンスカテゴリー情報を格納するコンテナです。

### Service

+ [DictionaryService](../../services/DictionaryService.md)

### Namespace

[DictionaryService#Namespace](../../services/DictionaryService.md#namespace)

| Field | Type | Description | response |
| ----- | ---- | ----------- | -------- |
| code | xsd:string | カテゴリコードです。 | yes | |
| name | xsd:string | サブカテゴリ名称です。 | yes | |
| fullName | xsd:string | カテゴリ名称です。（カテゴリ名称、サブカテゴリ名称を含めた正式名称です。） | yes | |
| reach | xsd:long | リーチ数です。 | yes | |
| categoryType | enum [AudienceCategoryType](./AudienceCategoryType.md) | カテゴリータイプです。 | yes | |
| child[] | [AudienceCategory](./AudienceCategory.md) | 子カテゴリーです。 | yes | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

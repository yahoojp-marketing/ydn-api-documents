

# FeedItemGoogleProductCategory

FeedItemGoogleProductCategoryオブジェクトは、FeedItemGoogleProductCategoryを格納するコンテナです。

### Service

+ [DictionaryService](../../services/DictionaryService.md)

### Namespace

[DictionaryService#Namespace](../../services/DictionaryService.md#namespace)

| Field | Type | Description | response |
| ----- | ---- | ----------- | -------- |
| id | xsd:string | Google商品カテゴリのIDです。 | yes | |
| parent | xsd:string | 上位のGoogle商品カテゴリIDです。 | yes | |
| order | xsd:string | 並び順を示す番号です。 | yes | |
| name | xsd:string | Google商品カテゴリの名前です。 | yes | |
| fullName | xsd:string | 上位階層を含むGoogle商品カテゴリの名称です。 | yes | |
| child[] | [FeedItemGoogleProductCategory](./FeedItemGoogleProductCategory.md) | 下位階層のGoogle商品カテゴリです。 | yes | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

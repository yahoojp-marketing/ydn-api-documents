

# GeographicLocation

GeographicLocationオブジェクトは、地域情報を表します。

### Service

+ [DictionaryService](../../services/DictionaryService.md)

### Namespace

[DictionaryService#Namespace](../../services/DictionaryService.md#namespace)

| Field | Type | Description | response |
| ----- | ---- | ----------- | -------- |
| code | xsd:string | 地域コードです。<br>「その他」の地域コード(TC-CI-00000073)は、地域ターゲティングでは利用できません。 | yes | |
| parent | xsd:string | 上位階層の地域コードです。 | yes | |
| order | xsd:string | 並び順を示す番号です。 | yes | |
| name | xsd:string | 市区町村名です。 | yes | |
| fullName | xsd:string | 都道府県名を含む地域名です。 | yes | |
| child[] | [GeographicLocation](./GeographicLocation.md) | 下位階層の地域構造です。 | yes | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>



# ColorSetValues

ColorSetValuesオブジェクトは、 getColorSetメソッドの実行結果（1 Entity）を保持するコンテナです。

### Service

+ [DictionaryService](../../services/DictionaryService.md)

### Namespace

[DictionaryService#Namespace](../../services/DictionaryService.md#namespace)

### Inheritance

+ [ReturnValue](../Common/ReturnValue.md)

| Field | Type | Description | response |
| ----- | ---- | ----------- | -------- |
| colorSetId | xsd:long | カラーテーマIDです。 | ○ | |
| name | xsd:string | カラーテーマ名です。 | ○ | |
| colorSet[1..*] | [ColorSet](./ColorSet.md) | カラーテーマです。 | ○ | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

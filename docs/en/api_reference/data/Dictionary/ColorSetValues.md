# ColorSetValues
ColorSetValues stores one entity of results of getColorSet method.
### Service
+ [DictionaryService](../../services/DictionaryService.md)

### Namespace
[DictionaryService#Namespace](../../services/DictionaryService.md#namespace)

| Field | Data type | maxOccurs | minOccurs | response | add | set | remove | Description | 
|---|---|---|---|---|---|---|---|---|
| colorSetId| long| 1| 0| ○| Ignore| Ignore| Ignore| Color set ID. |
| name| string| 1| 0| ○| Ignore| Ignore| Ignore| Colors set name. |
| colorSet[1..*]| <a href="./ColorSet.md">ColorSet</a>| unbounded| 0| ○| Ignore| Ignore| Ignore| Color set. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

# CategoryChildValues
CategoryChildValuesオブジェクトは、1?5階層までのカテゴリー情報を格納するコンテナです。
### Service
+ [DictionaryService](../../services/DictionaryService.md)

### Namespace
[DictionaryService#Namespace](../../services/DictionaryService.md#namespace)

| フィールド | データ型 | maxOccurs | minOccurs | response | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| code| string| 1| 1| ○| -| -| -| カテゴリコードです。 |
| name| string| 1| 1| ○| -| -| -| サブカテゴリ名称です。 |
| fullName| string| 1| 1| ○| -| -| -| カテゴリ名称です。（カテゴリ名称、サブカテゴリ名称を含めた正式名称です。） |
| reachDesktop| long| 1| 1| ○| -| -| -| PCのリーチ実績数です。 |
| reachSmartphone| long| 1| 1| ○| -| -| -| スマホのリーチ実績数です。 |
| reachTablet| long| 1| 1| ○| -| -| -| タブレットのリーチ実績数です。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

# RetargetingTagReturnValue
RetargetingTagReturnValueオブジェクトは、サイトリターゲティングタグの情報を格納するコンテナです。

### Service
+ [RetargetingTagService](../services/RetargetingTagService.md)

| フィールド | データ型 | maxOccurs | minOccurs | response | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| ListReturnValue(inherited)|||||||||
| ListReturnValue.Type| xsd: string||||||| このインスタンスの ListReturnValue のサブタイプを示します。 |
| Operation.Type| xsd: string||||||| mutate処理の内容です。 |
| RetargetingTagReturnValue|||||||||
| values| <a href="./RetargetingTagValues.md">RetargetingTagValues</a>| unbounded|0|○|-|-|-| サイトリターゲティングのタグに関する情報を含めたmutateメソッドの実行結果です。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

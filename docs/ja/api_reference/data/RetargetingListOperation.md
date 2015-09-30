# RetargetingListOperation
RetargetingListOperationオブジェクトは、操作対象となるサイトリターゲティングのターゲットリスト情報を表します。
### Service
+ [RetargetingListService](../services/RetargetingListService.md)

| フィールド | データ型 | 説明 | 制限 | 
|---|---|---|---|
| Operation(inherited)||||
| operator| enum <a href="./Operator.md">Operator</a>| 処理を表す演算子です。| Req |
| RetargetingListOperation||||
| accountId| xsd: long| アカウントIDです。| Req |
| targetListType| enum <a href="./TargetListType.md">TargetListType</a>| ターゲティングリストの種類です。| — |
| operand| <a href="./RetargetingList.md">RetargetingList</a>| ターゲットリストです。|  |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

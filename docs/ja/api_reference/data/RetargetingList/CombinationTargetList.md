# CombinationTargetList
CombinationTargetListオブジェクトは、ターゲットリストの組み合わせ情報のリストを表します。
### Service
+ [RetargetingListService](../../services/RetargetingListService.md)

### Namespace
[RetargetingListService#Namespace](../../services/RetargetingListService.md#namespace)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| TargetList(inherited)||||||
| targetListType| Enum <a href="./TargetListType.md">TargetListType</a>| ターゲットリストの種類です。| Req| Req| — |
| CombinarionTargetList||||||
| combinations[]| <a href="./Combination.md">Combination</a>| ターゲットリストの組み合わせ情報です。| Req| Req| — |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

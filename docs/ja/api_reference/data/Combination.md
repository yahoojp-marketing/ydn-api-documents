# Combination
Combinationオブジェクトは、ターゲットリストの組み合わせに関する情報を格納するコンテナです。
### Service
+ [RetargetingListService](../services/RetargetingListService.md)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| logicalOperator| enum <a href="./LogicalOperator.md">LogicalOperator</a>| ターゲットリストの条件の種類です。| Req| Req| — |
| targetListDatas[]| <a href="./TargetListData.md">TargetListData</a>| ターゲティングリストのデータです| Req| Req| — |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

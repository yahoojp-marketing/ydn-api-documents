# RuleCondition
RuleConditionオブジェクトは、ターゲットリストに設定可能な条件を表します。
### Service
+ [RetargetingListService](../services/RetargetingListService.md)

| フィールド | データ型 | ADD | SET | REMOVE | 説明 | 
|---|---|---|---|---|---|
| type| enum <a href="./RuleType.md">RuleType</a>| Req| Req| —| ルールの種類（URL , ラベル，リファラURL）です。 |
| compareOperator| enum <a href="./CompareOperator.md">CompareOperator</a>| Req| Req| —| ルールに設定するオペレーターです。 |
| value| xsd: string| Req| Req| —| ルールで評価する値です。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

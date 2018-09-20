# RuleCondition
RuleConditionオブジェクトは、ターゲットリストに設定可能な条件を表します。

### Service
+ [RetargetingListService](../../services/RetargetingListService.md)

### Namespace
[RetargetingListService#Namespace](../../services/RetargetingListService.md#namespace)

| フィールド | データ型 | ADD | SET | REMOVE | 説明 | 
|---|---|---|---|---|---|
| type| enum <a href="./RuleType.md">RuleType</a>| Requirement | Requirement | Ignore | ルールの種類。 |
| compareOperator| enum <a href="./CompareOperator.md">CompareOperator</a>| Requirement | Requirement | Ignore | ルールに設定するオペレーター。 |
| value| xsd: string| Requirement | Requirement | Ignore | ルールで評価する値。<br>※type=EVENT_TYPEの場合、<a href="/docs/ja/api_reference/appendix/eventtypes.md">イベント種別</a>に記載の値のみ指定可能。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

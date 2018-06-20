# RuleCondition
RuleCondition object displays the possible conditions to set for target list.
### Service
+ [RetargetingListService](../../services/RetargetingListService.md)

### Namespace
[RetargetingListService#Namespace](../../services/RetargetingListService.md#namespace)

| Field | Data Type | Description | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| type| enum <a href="./RuleType.md">RuleType</a>| Types of rule.| Req| Req| — |
| compareOperator| enum <a href="./CompareOperator.md">CompareOperator</a>| Operator to set the rules.| Req| Req| — |
| value| xsd: string| Values.| Req| Req| — |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

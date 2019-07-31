# RuleCondition
RuleCondition object displays the possible conditions to set for target list.
### Service
+ [RetargetingListService](../../services/RetargetingListService.md)

### Namespace
[RetargetingListService#Namespace](../../services/RetargetingListService.md#namespace)

| Field | Data Type | Description | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| type| enum <a href="./RuleType.md">RuleType</a>| Types of rule.| Requirement | Requirement | Ignore |
| compareOperator| enum <a href="./CompareOperator.md">CompareOperator</a>| Operator to set the rules.| Requirement | Requirement | Ignore |
| value| xsd: string| Matching Rules Value.<br>&lowast;In case of type = EVENT_TYPE, only the values listed in <a href="/docs/en/api_reference/appendix/eventtypes.md">Event Type</a> can be specified. | Requirement | Requirement | Ignore |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

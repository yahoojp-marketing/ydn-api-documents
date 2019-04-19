# Condition
Condition object contains OR conditional retrieval of feedset information.

### Service
+ [FeedSetService](../../services/FeedSetService.md)

### Namespace
[FeedSetService#Namespace](../../services/FeedSetService.md#namespace)

| Field | Type | Description | response | add | remove |
|---|---|---|---|---|---|
| operator | [CompareOperator](./CompareOperator.md)| Operator of setting conditions | yes | Requirement | Ignore |
| value | string | Value<br/>If [ConditionType](ConditionType.md):BADGE, the values which is available for "Badge" in the "Data feed (item list)" part of the guideline page "[Dynamic Ads for Display](https://support-marketing.yahoo.co.jp/promotionalads/ydn/articledetail?lan=en&aid=22325)" can be specified. | yes | Requirement | Ignore |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

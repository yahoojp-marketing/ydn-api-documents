# Condition
Conditionオブジェクトは、商品セット情報のOR条件を保持します。

### Service
+ [FeedSetService](../../services/FeedSetService.md)

### Namespace
[FeedSetService#Namespace](../../services/FeedSetService.md#namespace)

| Field | Type | Description | response | add | remove 
|---|---|---|---|---|---|
| operator | [CompareOperator](./CompareOperator.md)| 設定条件 | ○ | Requirement | Ignore
| value | string | 値<br/>[ConditionType](ConditionType.md):BADGEの場合は、<br/>[データフィードのファイルフォーマット](https://support-marketing.yahoo.co.jp/promotionalads/ydn/articledetail?lan=ja&aid=36277)の「商品リストファイルの入力項目」にある「Badge」で利用できる値のみ指定できます。 | ○ | Requirement | Ignore

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

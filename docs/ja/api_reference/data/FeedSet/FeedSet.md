# FeedSet
FeedSetオブジェクトは、商品セット情報を保持します。

### Service
+ [FeedSetService](../../services/FeedSetService.md)

### Namespace
[FeedSetService#Namespace](../../services/FeedSetService.md#namespace)

| Field | Type | Description | response | add | remove 
|---|---|---|---|---|---|
| accountId| xsd:long| アカウントID | ○ | Ignore |　Ignore 
| feedHolderId| xsd:long| FeedHolderを識別するId | ○ | Requirement | Requirement
| feedSetId| xsd:long| 商品セットID | ○ | Ignore | Requirement
| feedSetName| xsd:string| 商品セット名を識別する名称 |  ○ | Requirement | Ignore
| isDefaultSet| xsd:boolean| デフォルトセット判定 | ○ | Ignore | Ignore
| itemCount| xsd:long| 商品セットの条件に含まれるアイテム数 | ○ | Ignore | Ignore
| conditionSets[0..10]| [ConditionSet](./ConditionSet.md)| 商品セットの条件 | ○ | Requirement | Ignore

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

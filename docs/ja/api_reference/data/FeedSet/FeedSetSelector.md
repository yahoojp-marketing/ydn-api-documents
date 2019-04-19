# FeedSetSelector
get操作の検索条件を保持するオブジェクト

### Service
+ [FeedSetService](../../services/FeedSetService.md)

### Namespace
[FeedSetService#Namespace](../../services/FeedSetService.md#namespace)

| Field | Type | Description |
|---|---|---|
| accountId| xsd: long| アカウントID |
| feedHolderId| xsd:long| FeedHolderID |
| feedSetIds [0..30]| xsd:long| 商品セットID |
| includeItemCount| xsd:boolean | 商品セットのアイテム件数を表示<br>trueの場合は、アイテム件数を表示<br> ※デフォルト値はfalse:表示しない。|

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

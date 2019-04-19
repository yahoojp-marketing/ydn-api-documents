# FeedSetSelector
FeedSetSelector object contains search condition of get operation.

### Service
+ [FeedSetService](../../services/FeedSetService.md)

### Namespace
[FeedSetService#Namespace](../../services/FeedSetService.md#namespace)

| Field | Type | Description |
|---|---|---|
| accountId| xsd: long| Account ID. |
| feedHolderId| xsd:long| FeedHolder ID. |
| feedSetIds [0..30]| xsd:long| Item Set ID. |
| includeItemCount| xsd:boolean | Describes number of items of Item Set.<br>If true, the number of items is described.<br>&lowast; Default is false: Not described. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

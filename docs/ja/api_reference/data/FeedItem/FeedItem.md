

# FeedItem

FeedItemオブジェクトは、商品の情報を格納するコンテナです。

### Service

+ [FeedItemService](../../services/FeedItemService.md)

### Namespace

[FeedItemService#Namespace](../../services/FeedItemService.md#namespace)

| Field | Type | Description | response | set |
| ----- | ---- | ----------- | -------- | --------- |
| feedHolderId | xsd:long | FeedHolderを識別するId | - | Requirement<br/>NotUpdatable | |
| itemId | xsd:string | 商品ID | - | Requirement<br/>NotUpdatable | |
| inStock | xsd:long | 在庫情報<br/>0:在庫なし、1:在庫あり | - | Optional<br/>Updatable | |
| capacity | xsd:long | 在庫数 | - | Optional<br/>Updatable | |
| isRemoveCapacity | enum [isRemoveFlg](./isRemoveFlg.md) | 在庫数を削除するフラグです。<br/>設定値が「TRUE」の場合、設定されている在庫数の値が無効になります。 | - | Optional<br/>Updatable | |
| price | xsd:long | 価格 | - | Optional<br/>Updatable | |
| isRemovePrice | enum [isRemoveFlg](./isRemoveFlg.md) | 価格を削除するフラグです。<br/>設定値が「TRUE」の場合、設定されている価格の値が無効になります。 | - | Optional<br/>Updatable | |
| salePrice | xsd:long | セール価格 | - | Optional<br/>Updatable | |
| isRemoveSalePrice | enum [isRemoveFlg](./isRemoveFlg.md) | セール価格を削除するフラグです。<br/>設定値が「TRUE」の場合、設定されているセール価格の値が無効になります。 | - | Optional<br/>Updatable | |
| formattedPrice | xsd:string | 文字列の価格 | - | Optional<br/>Updatable | |
| isRemoveFormattedPrice | enum [isRemoveFlg](./isRemoveFlg.md) | 文字列の価格を削除するフラグです。<br/>設定値が「TRUE」の場合、設定されている文字列の価格の値が無効になります。 | - | Optional<br/>Updatable | |
| formattedSalePrice | xsd:string | 文字列のセール価格 | - | Optional<br/>Updatable | |
| isRemoveFormattedSalePrice | enum [isRemoveFlg](./isRemoveFlg.md) | 文字列のセール価格を削除するフラグです。<br/>設定値が「TRUE」の場合、設定されている文字列のセール価格の値が無効になります。 | - | Optional<br/>Updatable | |
| displaySettings | xsd:long | 配信設定<br/>0:配信しない、1:配信する | - | Optional<br/>Updatable | |
| availability | enum [Availability](./Availability.md) | 在庫状況 | - | Optional<br/>Updatable | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

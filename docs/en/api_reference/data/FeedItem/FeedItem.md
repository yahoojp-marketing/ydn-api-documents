

# FeedItem

FeedItem object contain information about the product.

### Service

+ [FeedItemService](../../services/FeedItemService.md)

### Namespace

[FeedItemService#Namespace](../../services/FeedItemService.md#namespace)

| Field | Type | Description | response | set |
| ----- | ---- | ----------- | -------- | --------- |
| feedHolderId | xsd:long | ID for identifying FeedHolder. | - | Requirement<br/>NotUpdatable | |
| itemId | xsd:string | Item ID. | - | Requirement<br/>NotUpdatable | |
| inStock | xsd:long | Inventory information. <br> 0: Out of order, 1: In stock | - | Optional<br/>Updatable | |
| capacity | xsd:long | Stock quantity. | - | Optional<br/>Updatable | |
| isRemoveCapacity | enum [isRemoveFlg](./isRemoveFlg.md) | Flag to delete stock quantity.<br>When the setting value is "TRUE", the value of the stock quantity will become invalid. | - | Optional<br/>Updatable | |
| price | xsd:long | Price. | - | Optional<br/>Updatable | |
| isRemovePrice | enum [isRemoveFlg](./isRemoveFlg.md) | Flag to delete price.<br>When the setting value is "TRUE", the value of the price will become invalid. | - | Optional<br/>Updatable | |
| salePrice | xsd:long | Sale price. | - | Optional<br/>Updatable | |
| isRemoveSalePrice | enum [isRemoveFlg](./isRemoveFlg.md) | Flag to delete sale price.<br>When the setting value is "TRUE", the value of the sale price will become invalid. | - | Optional<br/>Updatable | |
| formattedPrice | xsd:string | Text strings price. | - | Optional<br/>Updatable | |
| isRemoveFormattedPrice | enum [isRemoveFlg](./isRemoveFlg.md) | Flag to delete text strings price.<br>When the setting value is "TRUE", the value of the text strings price will become invalid. | - | Optional<br/>Updatable | |
| formattedSalePrice | xsd:string | Sale price of text strings. | - | Optional<br/>Updatable | |
| isRemoveFormattedSalePrice | enum [isRemoveFlg](./isRemoveFlg.md) | Flag to delete sale price of text strings.<br>When the setting value is "TRUE", the value of the sale price of text strings will become invalid. | - | Optional<br/>Updatable | |
| displaySettings | xsd:long | Display settings.<br>0: Off, 1: On | - | Optional<br/>Updatable | |
| availability | enum [Availability](./Availability.md) | Stock status. | - | Optional<br/>Updatable | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

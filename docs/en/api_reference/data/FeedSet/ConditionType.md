

# ConditionType (enum)

ConditionType object describes the type of items available for condition of Item Set.

#### Service

+ [FeedSetService](../../services/FeedSetService.md)

#### Namespace

[FeedSetService#Namespace](../../services/FeedSetService.md#namespace)

| Enumeration  |       Type       |          Description          |
| ------------ | ---------------- | ----------------------------- |
| CATEGORY_ID | xsd:string | Category ID |
| STOCK_QUANTITY | xsd:string | Stock quantity |
| PRICE | xsd:string | Price |
| SALE_PRICE | xsd:string | Sale price |
| RATING | xsd:string | Rating |
| REVIEWS | xsd:string | Number of reviews |
| BADGE | xsd:string | Type of badge<br>Available values on [Condition](Condition.md):<br>The values which is available for "Badge" in the "Data feed (item list)" part of the guideline page "[Dynamic Ads for Display](https://support-marketing.yahoo.co.jp/promotionalads/ydn/articledetail?lan=en&aid=22325)" can be specified.<br> |
| AGE_GROUP | xsd:string |  Age group<br>Available values on [Condition](Condition.md):<br>The values which is available for "AgeGroup" in the "Data feed (item list)" part of the guideline page "[Dynamic Ads for Display](https://support-marketing.yahoo.co.jp/promotionalads/ydn/articledetail?lan=en&aid=22325)" can be specified.<br> |
| AVAILABILITY_DATE | xsd:string | Expected arrival date |
| GENDER_GROUP | xsd:string | Gender group<br>Available values on [Condition](Condition.md):<br>The values which is available for "GenderGroup" in the "Data feed (item list)" part of the guideline page "[Dynamic Ads for Display](https://support-marketing.yahoo.co.jp/promotionalads/ydn/articledetail?lan=en&aid=22325)" can be specified.<br> |
| GOOGLE_PRODUCT_CATEGORY | xsd:string | Google product category<br>Available values on [Condition](Condition.md):<br>Only Google product category ID that can be acquired in [Google product category](../../services/DictionaryService.md#getfeeditemgoogleproductcategory) can be specified.<br> |
| LOCATION | xsd:string | Location<br>Only the [Location information](../../services/DictionaryService.md#getgeographiclocation) code acquired by declaring GeographicLocationType.FEED can be specified.<br> |
| SALES_RANK | xsd:string | Sales rank |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

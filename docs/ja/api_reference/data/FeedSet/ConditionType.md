

# ConditionType (enum)

商品セットの条件に設定できる項目の種別です。

#### Service

+ [FeedSetService](../../services/FeedSetService.md)

#### Namespace

[FeedSetService#Namespace](../../services/FeedSetService.md#namespace)

| Enumeration  |       Type       |          Description          |
| ------------ | ---------------- | ----------------------------- |
| CATEGORY_ID | xsd:string | カテゴリーID |
| STOCK_QUANTITY | xsd:string | 在庫数 |
| PRICE | xsd:string | 価格 |
| SALE_PRICE | xsd:string | セール価格 |
| RATING | xsd:string | 評価 |
| REVIEWS | xsd:string | 評価件数 |
| BADGE | xsd:string | バッジ種別<br>[Condition](Condition.md)で設定可能な値:<br>[データフィードのファイルフォーマット](https://support-marketing.yahoo.co.jp/promotionalads/ydn/articledetail?lan=ja&aid=36277)の「商品リストファイルの入力項目」にある「Badge」で利用できる値のみ指定できます。<br> |
| AGE_GROUP | xsd:string | 年齢層<br>[Condition](Condition.md)で設定可能な値:<br>[データフィードのファイルフォーマット](https://support-marketing.yahoo.co.jp/promotionalads/ydn/articledetail?lan=ja&aid=36277)の「商品リストファイルの入力項目」にある「AgeGroup」で利用できる値のみ指定できます。<br> |
| AVAILABILITY_DATE | xsd:string | 入荷予定日 |
| GENDER_GROUP | xsd:string | 性別<br>[Condition](Condition.md)で設定可能な値:<br>[データフィードのファイルフォーマット](https://support-marketing.yahoo.co.jp/promotionalads/ydn/articledetail?lan=ja&aid=36277)の「商品リストファイルの入力項目」にある「GenderGroup」で利用できる値のみ指定できます。<br> |
| GOOGLE_PRODUCT_CATEGORY | xsd:string | Google商品カテゴリ<br>[Condition](Condition.md)で設定可能な値:<br>[Google商品カテゴリ](../../services/DictionaryService.md#getfeeditemgoogleproductcategory)で取得できるGoogle商品カテゴリのidのみ指定できます。<br> |
| LOCATION | xsd:string | 地域<br>GeographicLocationType.FEEDを指定して取得できる[地域情報](../../services/DictionaryService.md#getgeographiclocation)のcodeのみ指定できます。<br> |
| SALES_RANK | xsd:string | 売上順位 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

# AccountBudget
AccountBudgetオブジェクトは、アカウント予算を格納するコンテナです。
### Service
+ [AccountService](../services/AccountService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| amount| xsd:long| アカウントの予算です。 |
| limitChargeType| enum <a href="../data/LimitChargeType.md">LimitChargeType</a>| 課金タイプです。 |
| startDate| xsd:string| 開始日です。 |
| endDate| xsd:string| 終了日です。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

# Account
Accountオブジェクトは、アカウント情報を示します。
### Service
+ [AccountService](../services/AccountService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| accountId| xsd:long| アカウントIDです。 |
| accountName| xsd:string| アカウント名です。 |
| accountType| enum <a href="../data/AccountType.md">AccountType</a>| アカウントの種別です。 |
| accountStatus| enum <a href="../data/AccountStatus.md">AccountStatus</a>| アカウントの状況です。 |
| deliveryStatus| enum <a href="../data/DeliveryStatus.md">DeliveryStatus</a>| 配信状況です。 |
| budget| <a href="../data/AccountBudget.md">AccountBudget</a>| アカウントの予算です。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

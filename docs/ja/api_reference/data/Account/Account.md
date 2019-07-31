# Account
Accountオブジェクトは、アカウント情報を示します。
### Service
+ [AccountService](../../services/AccountService.md)

### Namespace
[AccountService#Namespace](../../services/AccountService.md#namespace)

| フィールド | データ型 | 説明 | SET |
|---|---|---|---|
| accountId| xsd:long| アカウントIDです。 | Req |
| accountName| xsd:string| アカウント名です。 | Opt |
| accountType| enum <a href="AccountType.md">AccountType</a>| アカウントの種別です。 | - |
| accountStatus| enum <a href="AccountStatus.md">AccountStatus</a>| アカウントの状況です。 | - |
| deliveryStatus| enum <a href="DeliveryStatus.md">DeliveryStatus</a>| 配信状況です。 | Opt |
| budget| <a href="AccountBudget.md">AccountBudget</a>| アカウントの予算です。 | - |
| autoTaggingEnabled| enum <a href="AutoTaggingEnabled.md">AutoTaggingEnabled</a>| 自動タグ設定の管理フラグです。 | Opt <br>default: FALSE |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>



# Account

Accountオブジェクトは、アカウント情報を示します。

### Service

+ [AccountService](../../services/AccountService.md)

### Namespace

[AccountService#Namespace](../../services/AccountService.md#namespace)

| Field | Type | Description | response | set |
| ----- | ---- | ----------- | -------- | --------- |
| accountId | xsd:long | アカウントIDです。 | yes | Req | |
| accountName | xsd:string | アカウント名です。 | yes | Opt | |
| accountType | enum [AccountType](./AccountType.md) | アカウントの種別です。 | yes | - | |
| accountStatus | enum [AccountStatus](./AccountStatus.md) | アカウントの状況です。 | yes | - | |
| deliveryStatus | enum [DeliveryStatus](./DeliveryStatus.md) | 配信状況です。 | yes | Opt | |
| budget | [AccountBudget](./AccountBudget.md) | アカウントの予算です。 | yes | - | |
| autoTaggingEnabled | enum [AutoTaggingEnabled](./AutoTaggingEnabled.md) | 自動タグ設定の管理フラグです。 | yes | Opt<br/>default: FALSE | |
| accountAuthorities[] | xsd:string | アカウント権限 | yes | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

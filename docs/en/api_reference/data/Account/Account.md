

# Account

Account objects serve account information.

### Service

+ [AccountService](../../services/AccountService.md)

### Namespace

[AccountService#Namespace](../../services/AccountService.md#namespace)

| Field | Type | Description | response | set |
| ----- | ---- | ----------- | -------- | --------- |
| accountId | xsd:long | Account ID | yes | Req | |
| accountName | xsd:string | Account name | yes | Opt | |
| accountType | enum [AccountType](./AccountType.md) | Account type | yes | - | |
| accountStatus | enum [AccountStatus](./AccountStatus.md) | Account status | yes | - | |
| deliveryStatus | enum [DeliveryStatus](./DeliveryStatus.md) | Delivery status | yes | Opt | |
| budget | [AccountBudget](./AccountBudget.md) | Account budget | yes | - | |
| autoTaggingEnabled | enum [AutoTaggingEnabled](./AutoTaggingEnabled.md) | Management flag of auto tag | yes | Opt<br/>default: FALSE | |
| accountAuthorities[] | xsd:string | Account authority | yes | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

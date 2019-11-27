

# AccountBudget

AccountBudgetは、アカウント予算情報を保持するオブジェクトです。

### Service

+ [AccountService](../../services/AccountService.md)

### Namespace

[AccountService#Namespace](../../services/AccountService.md#namespace)

| Field | Type | Description | response | set |
| ----- | ---- | ----------- | -------- | --------- |
| amount | xsd:long | アカウントの広告予算金額です。 | yes | Ignore | |
| limitChargeType | enum [LimitChargeType](./LimitChargeType.md) | 月額など予算に関するアカウントの種別です。 | yes | Ignore | |
| startDate | xsd:string | 掲載開始日です。 | yes | Ignore | |
| endDate | xsd:string | 掲載終了日です。 | yes | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

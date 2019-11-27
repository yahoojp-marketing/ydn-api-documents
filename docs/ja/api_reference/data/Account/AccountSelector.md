

# AccountSelector

AccountSelectorオブジェクトは、取得するアカウントを指定します。

### Service

+ [AccountService](../../services/AccountService.md)

### Namespace

[AccountService#Namespace](../../services/AccountService.md#namespace)

| Field | Type | Description | response |
| ----- | ---- | ----------- | -------- |
| accountIds[] | xsd:long | 指定しない場合は紐づくアカウントをすべて取得します。<br>※通常認証では省略できます。代行認証では必須です。 | yes | |
| accountTypes[] | enum [AccountType](./AccountType.md) | アカウント種別を指定します。 | yes | |
| accountStatuses[] | enum [AccountStatus](./AccountStatus.md) | アカウントの状況を指定します。 | yes | |
| paging | [Paging](../Common/Paging.md) | ページ設定情報です。 | yes | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

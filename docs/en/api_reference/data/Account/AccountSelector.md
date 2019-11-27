

# AccountSelector

The AccountSelector object is used to select accounts for acquisition.

### Service

+ [AccountService](../../services/AccountService.md)

### Namespace

[AccountService#Namespace](../../services/AccountService.md#namespace)

| Field | Type | Description | response |
| ----- | ---- | ----------- | -------- |
| accountIds[] | xsd:long | If nothing is selected, all accounts are retrieved.<br>* "accountIds"can also be omitted for regular authentication. Required for proxy authentication. | yes | |
| accountTypes[] | enum [AccountType](./AccountType.md) | Selects account type. | yes | |
| accountStatuses[] | enum [AccountStatus](./AccountStatus.md) | Selects account status. | yes | |
| paging | [Paging](../Common/Paging.md) | The page that is returned as a page. | yes | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

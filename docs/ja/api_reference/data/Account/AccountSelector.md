# AccountSelector
AccountSelectorオブジェクトは、取得するアカウントを指定します。
### Service
+ [AccountService](../../services/AccountService.md)

### Namespace
[AccountService#Namespace](../../services/AccountService.md#namespace)

| フィールド | データ型 | 説明 |
|---|---|---|
| accountIds[]| xsd: long| 指定しない場合は紐づくアカウントをすべて取得します。 |
| accountTypes[]| enum <a href="AccountType.md">AccountType</a>| アカウント種別を指定します。 |
| accountStatuses[]| enum <a href="AccountStatus.md">AccountStatus</a>| アカウントの状況を指定します。 |
| paging| <a href="../Common/Paging.md">Paging</a>| ページ設定情報です。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

# AdGroupAdSelector
AdGroupAdSelectorオブジェクトは、操作の対象とする広告およびフィルタ条件を表します。
### Service
+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace
[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

| フィールド | データ型 | 説明 |
|---|---|---|
| accountId| xsd:long| アカウント情報です。 |
| campaignIds[]| xsd:long| キャンペーンIDです。 |
| adGroupIds[]| xsd:long| 広告グループIDです。 |
| adIds[]| xsd:long| 広告IDです。 |
| mediaIds[]| xsd:long| 画像IDです。 |
| userStatus[]| enum <a href="UserStatus.md">UserStatus</a>| 配信の状況です。 |
| approvalStatus[]| enum <a href="ApprovalStatus.md">ApprovalStatus</a>| 審査の状況です。 |
| paging| <a href="../Common/Paging.md">Paging</a>| ページ設定情報です。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

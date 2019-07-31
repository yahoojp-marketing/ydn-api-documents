# AdGroupSelector
AdGroupSelectorオブジェクトは、指定された広告グループを表します。
### Service
+ [AdGroupService](../../services/AdGroupService.md)

### Namespace
[AdGroupService#Namespace](../../services/AdGroupService.md#namespace)


| フィールド | データ型 | 説明 |
|---|---|---|
| accountId| xsd:long| 検索条件：アカウントID |
| campaignIds[]| xsd:long| 検索条件：キャンペーンID |
| adGroupIds[]| xsd:long| 検索条件：広告グループID |
| labelIds[0..1000]| xsd:long| 検索条件 : ラベルID |
| containsLabelIdFlg| xsd:boolean| ラベルID取得フラグ |
| userStatuses[]| enum <a href="UserStatus.md">UserStatus</a> | 検索条件：広告グループのユーザー設定の配信ステータス |
| paging| <a href="../Common/Paging.md">Paging</a>| 検索条件：取得範囲 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

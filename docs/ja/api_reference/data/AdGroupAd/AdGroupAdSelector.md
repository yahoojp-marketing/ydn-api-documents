# AdGroupAdSelector
AdGroupAdSelectorオブジェクトは、操作の対象とする広告およびフィルタ条件を表します。
### Service
+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace
[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

| フィールド | データ型 | 説明 |
|---|---|---|
| accountId| xsd:long| 検索条件 : アカウント情報 |
| campaignIds[]| xsd:long| 検索条件 : キャンペーンID |
| adGroupIds[]| xsd:long| 検索条件 : 広告グループID |
| adIds[]| xsd:long| 検索条件 : 広告ID |
| mediaIds[]| xsd:long| 検索条件 : 画像ID |
| labelIds[0..1000]| xsd:long| 検索条件 : ラベルID |
| containsLabelIdFlg| xsd:boolean| ラベルID取得フラグ |
| approvalStatuses[]| enum <a href="ApprovalStatus.md">ApprovalStatus</a>| 検索条件 : 審査ステータス |
| paging| <a href="../Common/Paging.md">Paging</a>| 検索条件 : 取得範囲 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>



# AdGroupAdSelector

AdGroupAdSelectorオブジェクトは、操作の対象とする広告およびフィルタ条件を表します。

### Service

+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace

[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

| Field | Type | Description | response |
| ----- | ---- | ----------- | -------- |
| accountId | xsd:long | 検索条件 : アカウント情報 | yes | |
| campaignIds[] | xsd:long | 検索条件 : キャンペーンID | yes | |
| adGroupIds[] | xsd:long | 検索条件 : 広告グループID | yes | |
| adIds[] | xsd:long | 検索条件 : 広告ID | yes | |
| mediaIds[] | xsd:long | 検索条件 : 画像ID | yes | |
| labelIds[0..1000] | xsd:long | 検索条件 : ラベルID | yes | |
| containsLabelIdFlg | xsd:boolean | ラベルID取得フラグ | yes | |
| userStatuses | enum [UserStatus](./UserStatus.md) | 検索条件：広告のユーザー設定の配信ステータス | yes | |
| approvalStatuses[0..5] | enum [ApprovalStatus](./ApprovalStatus.md) | 検索条件 : 審査ステータス | yes | |
| paging | [Paging](../Common/Paging.md) | 検索条件 : 取得範囲 | yes | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>



# AdGroupSelector

AdGroupSelectorオブジェクトは、指定された広告グループを表します。

### Service

+ [AdGroupService](../../services/AdGroupService.md)

### Namespace

[AdGroupService#Namespace](../../services/AdGroupService.md#namespace)

| Field | Type | Description | response | get |
| ----- | ---- | ----------- | -------- | --------- |
| accountId | xsd:long | 検索条件：アカウントID | yes | - | |
| campaignIds[] | xsd:long | 検索条件：キャンペーンID | yes | - | |
| adGroupIds[] | xsd:long | 検索条件：広告グループID | yes | - | |
| labelIds[0..1000] | xsd:long | 検索条件：ラベルID | yes | - | |
| containsLabelIdFlg | xsd:boolean | 検索条件：ラベルID取得フラグ | yes | - | |
| userStatuses[] | enum [UserStatus](./UserStatus.md) | 検索条件：広告グループのユーザー設定の配信ステータス | yes | - | |
| feedSetIds | xsd:long | 検索条件：フィードセットID | yes | - | |
| paging | [Paging](../Common/Paging.md) | 検索条件：取得範囲 | yes | - | |
| campaignGoalFilterType | enum [CampaignGoalFilterType](./CampaignGoalFilterType.md) | 検索条件 : キャンペーン目的タイプ | yes | Optional | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

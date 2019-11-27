

# CampaignSelector

CampaignSelectorオブジェクトは、getメソッドの検索条件（実行パラメータ）を保持します。

### Service

+ [CampaignService](../../services/CampaignService.md)

### Namespace

[CampaignService#Namespace](../../services/CampaignService.md#namespace)

| Field | Type | Description | response | get |
| ----- | ---- | ----------- | -------- | --------- |
| accountId | xsd:long | 検索条件 : アカウントID | yes | Requirement | |
| campaignIds[0..200] | xsd:long | 検索条件 : キャンペーンID | yes | Optional | |
| labelIds[0..1000] | xsd:long | 検索条件 : ラベルID | yes | Optional | |
| containsLabelIdFlg | xsd:boolean | ラベルID取得フラグ | yes | Optional | |
| userStatus[0..2] | enum [UserStatus](./UserStatus.md) | 検索条件 : ユーザー設定の配信ステータス | yes | Optional | |
| feedHolderIds[0..10] | xsd:long | 検索条件 : フィードホルダーID | yes | Optional | |
| paging | [Paging](../Common/Paging.md) | 検索条件 : 取得範囲 | yes | Optional | |
| campaignType | enum [CampaignType](./CampaignType.md) | 検索条件 : キャンペーンタイプ | yes | Optional | |
| campaignGoalFilterType | enum [CampaignGoalFilterType](./CampaignGoalFilterType.md) | 検索条件 : キャンペーン目的タイプ | yes | Optional | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

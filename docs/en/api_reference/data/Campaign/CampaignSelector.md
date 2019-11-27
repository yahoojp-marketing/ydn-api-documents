

# CampaignSelector

The CampaignSelector object is a container for storing a set of criteria (parameters) for get method.

### Service

+ [CampaignService](../../services/CampaignService.md)

### Namespace

[CampaignService#Namespace](../../services/CampaignService.md#namespace)

| Field | Type | Description | response | get |
| ----- | ---- | ----------- | -------- | --------- |
| accountId | xsd:long | Search Condition: Account ID | yes | Requirement | |
| campaignIds[0..200] | xsd:long | Search Condition: Campaign ID | yes | Optional | |
| labelIds[0..1000] | xsd:long | Search Condition: Label ID | yes | Optional | |
| containsLabelIdFlg | xsd:boolean | Flag of contains label ID | yes | Optional | |
| userStatus[0..2] | enum [UserStatus](./UserStatus.md) | Search Condition: Delivery status of user settings | yes | Optional | |
| feedHolderIds[0..10] | xsd:long | Search Condition: Feed holder ID | yes | Optional | |
| paging | [Paging](../Common/Paging.md) | Search Condition: Data acquisition range | yes | Optional | |
| campaignType | enum [CampaignType](./CampaignType.md) | Search Condition: Campaign type | yes | Optional | |
| campaignGoalFilterType | enum [CampaignGoalFilterType](./CampaignGoalFilterType.md) | Search Condition: Campaign goal type | yes | Optional | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

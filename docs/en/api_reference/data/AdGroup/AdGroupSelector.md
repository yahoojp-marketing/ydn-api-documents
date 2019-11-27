

# AdGroupSelector

The AdGroupSelector object is a container for storing specified ad group information.

### Service

+ [AdGroupService](../../services/AdGroupService.md)

### Namespace

[AdGroupService#Namespace](../../services/AdGroupService.md#namespace)

| Field | Type | Description | response | get |
| ----- | ---- | ----------- | -------- | --------- |
| accountId | xsd:long | Search Condition: Account ID. | yes | - | |
| campaignIds[] | xsd:long | Search Condition: Campaign ID. | yes | - | |
| adGroupIds[] | xsd:long | Search Condition: Ad group ID. | yes | - | |
| labelIds[0..1000] | xsd:long | Search Condition: Label ID. | yes | - | |
| containsLabelIdFlg | xsd:boolean | Flag of contains label ID. | yes | - | |
| userStatuses[] | enum [UserStatus](./UserStatus.md) | Search Condition: Display status. | yes | - | |
| feedSetIds | xsd:long | Search Condition: Feed set ID. | yes | - | |
| paging | [Paging](../Common/Paging.md) | Search Condition: Paging. | yes | - | |
| campaignGoalFilterType | enum [CampaignGoalFilterType](./CampaignGoalFilterType.md) | Search Condition: Campaign goal type | yes | Optional | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

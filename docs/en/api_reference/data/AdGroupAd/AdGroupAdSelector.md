

# AdGroupAdSelector

The AdGroupAdSelector object is a container for storing ad information and filtering condition.

### Service

+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace

[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

| Field | Type | Description | response | get |
| ----- | ---- | ----------- | -------- | --------- |
| accountId | xsd:long | Search Condition: Account information | yes | - | |
| campaignIds[] | xsd:long | Search Condition: Campaign ID | yes | - | |
| adGroupIds[] | xsd:long | Search Condition: Ad Group ID | yes | - | |
| adIds[] | xsd:long | Search Condition: Ad ID | yes | - | |
| mediaIds[] | xsd:long | Search Condition: Media ID | yes | - | |
| labelIds[0..1000] | xsd:long | Search Condition: Label ID | yes | - | |
| containsLabelIdFlg | xsd:boolean | Flag of contains label ID | yes | - | |
| userStatuses | enum [UserStatus](./UserStatus.md) | Search Condition: Display status. | yes | - | |
| approvalStatuses[0..5] | enum [ApprovalStatus](./ApprovalStatus.md) | Search Condition: Approval status | yes | - | |
| paging | [Paging](../Common/Paging.md) | Search Condition: Paging. | yes | - | |
| campaignGoalFilterType | enum [CampaignGoalFilterType](./CampaignGoalFilterType.md) | Search Condition: Campaign goal type | yes | Optional | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

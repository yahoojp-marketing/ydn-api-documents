

# AdGroupAdSelector

The AdGroupAdSelector object is a container for storing ad information and filtering condition.

### Service

+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace

[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

| Field | Type | Description | response |
| ----- | ---- | ----------- | -------- |
| accountId | xsd:long | The account information. | yes | |
| campaignIds[] | xsd:long | The campaign ID. | yes | |
| adGroupIds[] | xsd:long | The ad group ID. | yes | |
| adIds[] | xsd:long | The ad ID. | yes | |
| mediaIds[] | xsd:long | The media ID | yes | |
| labelIds[0..1000] | xsd:long | The label ID | yes | |
| containsLabelIdFlg | xsd:boolean | Flag of contains label ID | yes | |
| userStatuses | enum [UserStatus](./UserStatus.md) | Search Condition: Display status. | yes | |
| approvalStatuses[0..5] | enum [ApprovalStatus](./ApprovalStatus.md) | The approval status. | yes | |
| paging | [Paging](../Common/Paging.md) | Paging. | yes | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

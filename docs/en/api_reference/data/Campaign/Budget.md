

# Budget

The Budget object serves campaign budgets.

### Service

+ [CampaignService](../../services/CampaignService.md)

### Namespace

[CampaignService#Namespace](../../services/CampaignService.md#namespace)

| Field | Type | Description | response | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| amount | xsd:long | The daily budget. This is a requirement for add/set if deliveryMethod is STANDARD.<br><br>* It defined "with no campaignGoal" if Campaign.campaignGoal is set NONE, otherwise defined "with campaignGoal".<br> | yes | Optional<br>* With campaignGoal: Requirement | Optional | Ignore | |
| deliveryMethod | enum [BudgetDeliveryMethod](./BudgetDeliveryMethod.md) | Ad delivery method.<br><br>* It defined "with no campaignGoal" if Campaign.campaignGoal is set NONE, otherwise defined "with campaignGoal".<br> | yes | Optional<br>* With campaignGoal: cannot be set | Optional<br>* With campaignGoal: cannot be set | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

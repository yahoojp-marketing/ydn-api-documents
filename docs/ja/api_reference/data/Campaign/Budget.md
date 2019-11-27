

# Budget

Budgetオブジェクトは、キャンペーン予算に関する情報を表します。

### Service

+ [CampaignService](../../services/CampaignService.md)

### Namespace

[CampaignService#Namespace](../../services/CampaignService.md#namespace)

| Field | Type | Description | response | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| amount | xsd:long | キャンペーンの一日にあたり予算（一日単位の利用金額）です。deliveryMethodがSTANDARDの場合はadd/set時にRequirementです。<br><br>※Campaign.campaignGoalがNONEの場合は「目的なし」、NONE以外の場合は「目的あり」と定義します。<br> | yes | Optional<br>* 目的ありの場合 : 必須 | Optional | Ignore | |
| deliveryMethod | enum [BudgetDeliveryMethod](./BudgetDeliveryMethod.md) | 広告の配信方法です。<br><br>※Campaign.campaignGoalがNONEの場合は「目的なし」、NONE以外の場合は「目的あり」と定義します。<br> | yes | Optional<br>* 目的ありの場合 : 設定不可 | Optional<br>* 目的ありの場合 : 設定不可 | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

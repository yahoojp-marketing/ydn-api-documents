# Budget
Budgetオブジェクトは、キャンペーン予算に関する情報を表します。
### Service
+ [CampaignService](../../services/CampaignService.md)

### Namespace
[CampaignService#Namespace](../../services/CampaignService.md#namespace)

| フィールド | データ型 | 説明 | 
|---|---|---|
| amount| xsd:long| キャンペーンの一日にあたり予算（一日単位の利用金額）です。deliveryMethodがSTANDARDの場合はadd/set時にRequirementです。 |
| deliveryMethod| enum <a href="BudgetDeliveryMethod.md">BudgetDeliveryMethod</a>| 広告の配信方法です。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>



# Campaign

Campaign object describes campaign information.

### About campaignGoal

- It defined "with no campaignGoal" if Campaign.campaignGoal is set NONE, otherwise defined "with campaignGoal".
- All of the campaign that making before V201911 is defined "with no campaignGoal".
- The fields that are required or updateable for "with campaignGoal" and "with no campaignGoal" campaigns are different.
The following table summarizes the required or updatable fields for "with / with no campaignGoal" and add / set.
   - * "--" mean "cannot be set".

| field name              | with no campaignGoal/<br>add | with no campaignGoal/<br>set | with campaignGoal/<br>add | with campaignGoal/<br>set |
| ---      | ---           | ---           | ---        | ---        |
| campaignType            | Optional                     | --                 | --              | --              |
| adProductType           | Required                     | --                 | --              | --              |
| frequencyCap            | Optional                     | Updatable                    | --              | --              |
| conversionOptimizer     | --                 | Updatable                    | --              | --              |
| campaignGoal            | --                 | --                 | Required                  | --              |
| viewableFrequencyCap    | --                 | --                 | Optional                  | Updatable                 |
| campaignBiddingStrategy | --                 | --                 | Required                  | Updatable                 |
| budget.amount           | Optional                     | Updatable                    | Required                  | Updatable                 |
| budget.deliveryMethod   | Optional                     | Updatable                    | --              | --              |

              

### Service

+ [CampaignService](../../services/CampaignService.md)

### Namespace

[CampaignService#Namespace](../../services/CampaignService.md#namespace)

| Field | Type | Description | response | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| accountId | xsd:long | Account ID. | yes | Requirement | Requirement<br>NotUpdatable | Requirement<br>NotUpdatable | |
| campaignId | xsd:long | Campaign ID. | yes | Ignore | Requirement<br>NotUpdatable | Requirement<br>NotUpdatable | |
| campaignName | xsd:string | Campaign Name. | yes | Requirement | Optional<br>Updatable | Ignore | |
| userStatus | enum [UserStatus](./UserStatus.md) | The setting that can adjust the presence or absence of ad delivery by user.<br>Filters will contain all ad delivery status if the userStatus is not set. | yes | Requirement | Optional<br>Updatable | Ignore | |
| servingStatus | enum [CampaignServingStatus](./CampaignServingStatus.md) | Delivery status in campaign level.<br>Display the campaign status, regardless of ad delivery setting by user. | yes | Ignore | Ignore | Ignore | |
| startDate | xsd:string | Start date. | yes | Optional | Optional<br>Updatable | Ignore | |
| endDate | xsd:string | End date. | yes | Optional | Optional<br>Updatable | Ignore | |
| budget | [Budget](./Budget.md) | Campaign Budget. | yes | Requirement | Optional<br>Updatable | Ignore | |
| biddingStrategy | [BiddingStrategy](./BiddingStrategy.md)<br>inherited [ManualCPC](./ManualCPC.md)<br>inherited [ManualCPV](./ManualCPV.md) | Bidding strategy.<br>* Not set for "with campaignGoal" campaigns. | yes | Ignore | Ignore | Ignore | |
| adProductType | xsd:string | Ad product information.<br>∗Check the available values by get operation on [AccountAdProductService](../../services/AccountAdProductService.md). | yes | Optional<br><br>* With no campaignGoal: Requirement<br>* With campaignGoal: cannot be set<br> | NotUpdatable | Ignore | |
| frequencyCap | [FrequencyCap](./FrequencyCap.md) | Frequency Cap. | yes | Optional<br>* With campaignGoal: cannot be set | Optional<br>Updatable<br>* With campaignGoal: cannot be set | Ignore | |
| conversionOptimizer | [CampaignConversionOptimizer](./CampaignConversionOptimizer.md)<br>inherited [AutoCampaignConversionOptimizer](./AutoCampaignConversionOptimizer.md)<br>inherited [ManualCampaignConversionOptimizer](./ManualCampaignConversionOptimizer.md) | Conversion Optimize.<br>* With campaignGoal: only [ManualCampaignConversionOptimizer](./ManualCampaignConversionOptimizer.md)<br> | yes | Ignore | Optional<br>Updatable<br>* With campaignGoal: cannot be set | Ignore | |
| campaignType | enum [CampaignType](./CampaignType.md) | Campaign Type. | yes | Optional<br><br>∗ Not specified: STANDARD<br>* With campaignGoal: cannot be set (only STANDARD)<br> | Ignore | Ignore | |
| appName | xsd:string | App Name. | yes | Optional<br>∗ If campaignType is set to "APP": Required. | Ignore | Ignore | |
| appId | xsd:string | iOS: APP ID.<br>Android: Package name. | yes | Optional<br>∗ If campaignType is set to "APP": Required. | Ignore | Ignore | |
| appOs | enum [DeviceOsType](./DeviceOsType.md) | Device Type of App Install Ads. | yes | Optional<br>∗ If campaignType is set to "APP": Required. | Ignore | Ignore | |
| labels[0..1000] | [Label](./Label.md) | Label. | yes | Ignore | Ignore | Ignore | |
| feedHolderId | xsd:long | Feed holder ID. | yes | Optional<br>* If AdType is Dynamic Ads for Display: Required. | Ignore | Ignore | |
| campaignGoal | xsd:string | Campaign goal.<br>* Available values can be referred to accountAuthorities field of [Account](../../data/Account/Account.md) object obtained by get operation of [AccountService](../../services/AccountService.md).<br> | yes | Optional<br><br>* With no campaignGoal: cannot be set<br>* With campaignGoal: Requirement<br> | Ignore | Ignore | |
| campaignBiddingStrategy | [CampaignBiddingStrategy](./CampaignBiddingStrategy.md) | Campaign bidding strategy. | yes | Optional<br><br>* With no campaignGoal: cannot be set<br>* With campaignGoal: Requirement<br> | Optional<br><br>* With no campaignGoal: cannot be set<br>* With campaignGoal: Requirement<br> | Ignore | |
| viewableFrequencyCap | [ViewableFrequencyCap](./ViewableFrequencyCap.md) | Viewable Frequency Cap. | yes | Optional<br><br>* With no campaignGoal: cannot be set<br>* With campaignGoal: Optional<br> | Optional<br>Updatable<br><br>* With no campaignGoal: cannot be set<br>* With campaignGoal: Optional<br> | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

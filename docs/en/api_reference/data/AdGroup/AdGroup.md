

# AdGroup

Ad Group object is a container for storing ad group information.<br/>

- The fields and values that can be specified for an ad group vary depending on whether the campaign associated with the ad group is "with campaignGoal" or "with no campaignGoal". The following table shows required or updatable fields and values depending on "with campaignGoal / with no campaignGoal" or "add / set".
   - &lowast;"--" means "cannot be set".

| Field                  | with campaignGoal<br>             | with no campaignGoal<br>CampaignType.APP | with no campaignGoal<br>CampaignType.STANDARD |
| ---     | ---                | ---                       | ---                            |
| device                 | Optional ( SMARTPHONE or TABLET ) | Optional ( SMARTPHONE or TABLET )        | Optional ( DESKTOP or WAP_MOBILE or NONE )    |
| deviceOs               | --                      | --                             | --                                  |
| smartDeviceCarriers    | --                      | Optional                                 | Optional                                      |
| dynamicImageExtensions | --                      | Optional                                 | Optional                                      |
| adGroupBiddingStrategy | Optional                          | --                             | --                                  |

        

### Service

+ [AdGroupService](../../services/AdGroupService.md)

### Namespace

[AdGroupService#Namespace](../../services/AdGroupService.md#namespace)

| Field | Type | Description | response | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| accountId | xsd:long | Account ID. | yes | Requirement | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | |
| campaignId | xsd:long | Campaign ID. | yes | Requirement | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | |
| campaignName | xsd:string | Campaign name. | yes | Ignore | Ignore | Ignore | |
| adGroupId | xsd:long | Ad group ID. | yes | Ignore | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | |
| adGroupName | xsd:string | Ad group name. | yes | Requirement | Optional<br/>Updatable | Ignore | |
| userStatus | enum [UserStatus](./UserStatus.md) | Delivery status. | yes | Requirement | Optional<br/>Updatable | Ignore | |
| bid | AdGroupBid<br>inherited [ManualCPCAdGroupBid](./ManualCPCAdGroupBid.md)<br>inherited [ManualCPVAdGroupBid](./ManualCPVAdGroupBid.md) | Bid amount. | yes | Optional<br>*For ad groups under campaigns with campaignGoal: Cannot be set | Optional<br>*For ad groups under campaigns with campaignGoal: Cannot be set | Ignore | |
| conversionOptimizer | [AdGroupConversionOptimizer](./AdGroupConversionOptimizer.md)<br>inherited [AutoAdGroupConversionOptimizer](./AutoAdGroupConversionOptimizer.md)<br>inherited [ManualAdGroupConversionOptimizer](./ManualAdGroupConversionOptimizer.md)<br>inherited [NoneAdGroupConversionOptimizer](./NoneAdGroupConversionOptimizer.md) | Conversion optimize. | yes | Optional<br/>Default : NoneAdGroupConversionOptimizer | Optional<br/>Updatable | Ignore | |
| device[0...5] | enum [DeviceType](./DeviceType.md) | Type of device for ad delivery. | yes | Requirement | Optional<br/>Updatable | Ignore | |
| deviceApp[0...3] | enum [DeviceAppType](./DeviceAppType.md) | Type of Application for ad delivery. | yes | Optional | Optional<br/>Updatable | Ignore | |
| deviceOs[0...3] | enum [DeviceOsType](./DeviceOsType.md) | Type of OS for ad delivery. | yes | Optional | Optional<br/>Updatable | Ignore | |
| smartDeviceCarriers[0...5] | enum [SmartDeviceCarrier](./SmartDeviceCarrier.md) | Type of mobile carrier for ad delivery. | yes | Optional<br>*For ad groups under campaigns with campaignGoal: Cannot be set | Optional<br/>Updatable<br>*For ad groups under campaigns with campaignGoal: Cannot be set | Ignore | |
| deviceOsVersion | xsd:string | OS version<br/>∗To specify null as deviceOsVersion: &#34;NONE&#34; | yes | Optional | Optional<br/>Updatable | Ignore | |
| dynamicImageExtensions | enum [DynamicImageExtensions](./DynamicImageExtensions.md) | Flag of Dynamic Image Extensions.<br/>∗Default is set as &#34;PAUSED&#34;. | yes | Optional<br>*For ad groups under campaigns with campaignGoal: Cannot be set | Optional<br/>Updatable<br>*For ad groups under campaigns with campaignGoal: Cannot be set | Ignore | |
| labels[0..1000] | [Label](./Label.md) | Label. | yes | Ignore | Ignore | Ignore | |
| feedSetId | xsd:long | Feed set ID | yes | Optional<br/>* If feedSetId is not specified, the default set is associated automatically. | Optional<br/>Updatable | Ignore | |
| isRemoveFeedSetId | xsd:boolean | Remove association with feed set<br/>* Association with feed set changed to required, so this feature was abolished. | yes | Ignore | Ignore | Ignore | |
| adGroupBiddingStrategy | [AdGroupBiddingStrategy](./AdGroupBiddingStrategy.md) | Ad group bid strategy | yes | Optional<br>*For ad groups under campaigns with no campaignGoal: Cannot be set | Optional<br>*For ad groups under campaigns with no campaignGoal: Cannot be set | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>



# AdGroupBiddingStrategy

AdGroupBiddingStrategy<br/>
This can only be specified for campaigns with campaignGoal.<br/>
Method to remove bid value:<br/>
```<br>
<ns1:adGroupBiddingStrategy>
  <ns1:campaignBiddingStrategyType>MAX_VCPM</ns1:campaignBiddingStrategyType>
  <ns1:maxVcpmBidValue>0</ns1:maxVcpmBidValue>
</ns1:adGroupBiddingStrategy>
```
        

### Service

+ [AdGroupService](../../services/AdGroupService.md)

### Namespace

[AdGroupService#Namespace](../../services/AdGroupService.md#namespace)

| Field | Type | Description | response | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| campaignBiddingStrategyType | enum [CampaignBiddingStrategyType](./CampaignBiddingStrategyType.md) | Campaign bid strategy type<br>* For campaigns with no campaignGoal: "NONE" is fixed | yes | Ignore | Ignore | Ignore | |
| maxVcpmBidValue | xsd:long | Ad group MAX_VCPM bid value.<br>* This can only be specified when campaignBiddingStrategyType is "MAX_VCPM"<br> | yes | Optional | Optional | Ignore | |
| maxCpcBidValue | xsd:long | Ad group MAX_CPC bid value.<br>* This can only be specified when campaignBiddingStrategyType is "MAX_CPC"<br> | yes | Optional | Optional | Ignore | |
| maxCpvBidValue | xsd:long | Ad group MAX_CPV bid value.<br>* This can only be specified when campaignBiddingStrategyType is "MAX_CPV"<br> | yes | Optional | Optional | Ignore | |
| targetCpaBidValue | xsd:long | Ad group TARGET_CPA bid value.<br>* This can only be specified when campaignBiddingStrategyType is "TARGET_CPA"<br> | yes | Optional | Optional | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>



# CampaignBiddingStrategy

CampaignBiddingStrategy object describes campaign bidding strategy.<br>
* If campaign with no purpose, cannot be set.


### Service

+ [CampaignService](../../services/CampaignService.md)

### Namespace

[CampaignService#Namespace](../../services/CampaignService.md#namespace)

| Field | Type | Description | response | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| type | enum [CampaignBiddingStrategyType](./CampaignBiddingStrategyType.md) | Current campaign bidding strategy type.<br><br>                      Only the value corresponding to the setting type applies, otherwise it does not apply to delivery.<br>                      In addition, only the cost value corresponding to type can be updated.<br>                      MAX_VCPM: Applying maxVcpmBidValue<br>                      MAX_CPC: Applying maxCpcBidValue<br>                      MAX_CPV: Applying maxCpvBidValue<br>                      TARGET_CPA: Applying targetCpaBidValue<br>                       | yes | Requirement | Requirement | Ignore | |
| maxVcpmBidValue | xsd:long | Max bid of campaign (vCPM) | yes | Optional | Optional | Ignore | |
| maxCpcBidValue | xsd:long | Max bid of campaign (CPC) | yes | Optional | Optional | Ignore | |
| maxCpvBidValue | xsd:long | Max bid of campaign (CPV) | yes | Optional | Optional | Ignore | |
| targetCpaBidValue | xsd:long | Target bid of campaign (CPA) | yes | Optional | Optional | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

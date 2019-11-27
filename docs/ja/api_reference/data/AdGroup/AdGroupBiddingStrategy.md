

# AdGroupBiddingStrategy

広告グループ入札戦略<br/>
目的ありのキャンペーンの場合のみ設定可。<br/>
単価の解除方法は、以下の通りです。<br>
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
| campaignBiddingStrategyType | enum [CampaignBiddingStrategyType](./CampaignBiddingStrategyType.md) | キャンペーン入札戦略タイプ<br>* 目的なしのキャンペーンの場合は「NONE」固定<br> | yes | Ignore | Ignore | Ignore | |
| maxVcpmBidValue | xsd:long | 広告グループ最大入札単価（vCPM）<br>* campaignBiddingStrategyTypeが「MAX_VCPM」の場合のみ指定可能<br> | yes | Optional | Optional | Ignore | |
| maxCpcBidValue | xsd:long | 広告グループ最大入札単価（CPC）<br>* campaignBiddingStrategyTypeが「MAX_CPC」の場合のみ指定可能<br> | yes | Optional | Optional | Ignore | |
| maxCpvBidValue | xsd:long | 広告グループ最大入札単価（CPV）<br>* campaignBiddingStrategyTypeが「MAX_CPV」の場合のみ指定可能<br> | yes | Optional | Optional | Ignore | |
| targetCpaBidValue | xsd:long | 広告グループ目標単価（CPA）<br>* campaignBiddingStrategyTypeが「TARGET_CPA」の場合のみ指定可能<br> | yes | Optional | Optional | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

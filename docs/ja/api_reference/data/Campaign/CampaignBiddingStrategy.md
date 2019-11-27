

# CampaignBiddingStrategy

キャンペーン入札戦略<br>
* 目的なしの場合には設定できません。


### Service

+ [CampaignService](../../services/CampaignService.md)

### Namespace

[CampaignService#Namespace](../../services/CampaignService.md#namespace)

| Field | Type | Description | response | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| type | enum [CampaignBiddingStrategyType](./CampaignBiddingStrategyType.md) | 現在のキャンペーン入札戦略タイプ<br><br>                      設定されているタイプに対応する値のみ配信に適用されます（それ以外の値は配信に適用されていません）<br>                      また、typeに対応する単価の値以外は更新できません。<br>                      MAX_VCPM   : maxVcpmBidValueを適用中<br>                      MAX_CPC    : maxCpcBidValueを適用中<br>                      MAX_CPV    : maxCpvBidValueを適用中<br>                      TARGET_CPA : targetCpaBidValueを適用中<br>                       | yes | Requirement | Requirement | Ignore | |
| maxVcpmBidValue | xsd:long | キャンペーン最大入札単価(vCPM) | yes | Optional | Optional | Ignore | |
| maxCpcBidValue | xsd:long | キャンペーン最大入札単価(CPC) | yes | Optional | Optional | Ignore | |
| maxCpvBidValue | xsd:long | キャンペーン最大入札単価(CPV) | yes | Optional | Optional | Ignore | |
| targetCpaBidValue | xsd:long | キャンペーン目標単価(CPA) | yes | Optional | Optional | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

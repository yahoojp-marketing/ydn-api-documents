# CampaignOperation
The CampaignOperation object is a container for storing campaign information and operation results.
### Service
+ [CampaignService](../../services/CampaignService.md)

### Namespace
[CampaignService#Namespace](../../services/CampaignService.md#namespace)

| Field | Data Type | Description | Restriction | 
|---|---|---|---|
| Operation(inherited)||||
| operator| enum Operator| An operator| Req |
| CampaignOperation||||
| accountId| xsd:long| The account ID.| Req |
| Operand| <a href="./Campaign.md">Campaign</a>[]| List of Campaign. It includes Campaign information.| Req |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

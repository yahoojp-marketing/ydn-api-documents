# AdGroupTargetOperation
The AdGroupTargetOperation object is a container for storing ad target information and the operation process.
### Service
+ [AdGroupTargetService](../services/AdGroupTargetService.md)

| Field | Data Type | Description | Restriction | 
|---|---|---|---|
| Operation(inherited)||||
| operator| enum <a href="./Operator.md">Operator</a>| An operator| Req |
| AdGroupTargetOperation||||
| accountId| xsd:long| The account ID.| Req |
| campaignId| xsd:long| The campaign ID.| Req |
| operand[]| <a href="./AdGroupTargets.md">AdGroupTargets</a>| List of target setting. It includes target setting information to be processed.| Req | 

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

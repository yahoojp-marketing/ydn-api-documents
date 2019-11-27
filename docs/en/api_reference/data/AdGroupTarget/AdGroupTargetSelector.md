

# AdGroupTargetSelector

The AdGroupTargetSelector object contains a set of criteria (parameters) for get method.

### Service

+ [AdGroupTargetService](../../services/AdGroupTargetService.md)

### Namespace

[AdGroupTargetService#Namespace](../../services/AdGroupTargetService.md#namespace)

| Field | Type | Description | response | get |
| ----- | ---- | ----------- | -------- | --------- |
| accountId | xsd:long | Account ID | yes | Requirement | |
| campaignIds[0..1000] | xsd:long | Campaign ID | yes | Optional | |
| adGroupIds[0..1000] | xsd:long | Ad group ID | yes | Optional | |
| targetTypes[0..7] | enum [TargetType](./TargetType.md) | Type of targeting | yes | Optional | |
| paging | [Paging](../Common/Paging.md) | Scope of the data | yes | Optional | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

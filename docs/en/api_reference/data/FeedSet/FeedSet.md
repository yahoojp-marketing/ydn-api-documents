

# FeedSet

FeedSet object contains Item Set information.

### Service

+ [FeedSetService](../../services/FeedSetService.md)

### Namespace

[FeedSetService#Namespace](../../services/FeedSetService.md#namespace)

| Field | Type | Description | response | add | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- |
| accountId | xsd:long | Account ID | ○ | Ignore | Ignore | |
| feedHolderId | xsd:long | Feed Holder ID | ○ | Requirement | Requirement | |
| feedSetId | xsd:long | Item Set ID | ○ | Ignore | Requirement | |
| feedSetName | xsd:string | Item Set name | ○ | Requirement | Ignore | |
| isDefaultSet | xsd:boolean | Default setting of Item Set or not | ○ | Ignore | Ignore | |
| itemCount | xsd:long | Number of items included in Item Set conditions | ○ | Ignore | Ignore | |
| conditionSets[0..10] | [ConditionSet](./ConditionSet.md) | Conditions on Item Set | ○ | Requirement | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

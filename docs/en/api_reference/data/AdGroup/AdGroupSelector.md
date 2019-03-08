# AdGroupSelector
The AdGroupSelector object is a container for storing specified ad group information.
### Service
+ [AdGroupService](../../services/AdGroupService.md)

### Namespace
[AdGroupService#Namespace](../../services/AdGroupService.md#namespace)

| Field | Data Type | Description |
|---|---|---|
| accountId| xsd:long| Search Condition: Account ID. |
| campaignIds[]| xsd:long| Search Condition: Campaign ID. |
| adGroupIds[]| xsd:long| Search Condition: Ad group ID. |
| labelIds[0..1000]| xsd:long| Search Condition: Label ID. |
| containsLabelIdFlg | xsd:boolean| Flag of contains label ID. |
| userStatuses| enum <a href="UserStatus.md">UserStatus[]</a>| Search Condition: Display status. |
| paging| <a href="../Common/Paging.md">Paging</a>| Search Condition: Paging. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

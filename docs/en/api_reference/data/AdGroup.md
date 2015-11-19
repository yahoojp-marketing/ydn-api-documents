# AdGroup
The Ad Group object is a container for storing ad group information.

### Service
+ [AdGroupService](../services/AdGroupService.md)

| Field | Data Type | Description | 
|---|---|---|
| accountId| xsd:long| The account ID. |
| campaignId| xsd:long| The campaign ID. |
| campaignName| xsd:string| The campaign name. |
| adGroupId| xsd:long| The ad group ID. |
| adGroupName| xsd:string| The ad group name. |
| userStatus| enum <a href="../data/UserStatus.md">UserStatus</a>| Display status. |
| bid| AdGroupBid <br>inherited <a href="../data/ManualCPCAdGroupBid.md">ManualCPCAdGroupBid</a>| The bid. |
| device| enum <a href="../data/DeviceType.md">DeviceType</a>| Name of device for display. |
| deviceApp| enum <a href="../data/DeviceAppType.md">DeviceAppType</a>| Assignment of application for display. |
| deviceOs| enum <a href="../data/DeviceOsType.md">DeviceOsType</a>| Assignment of OS for display destination. |
| smartDeviceCarriers| enum <a href="../data/SmartDeviceCarrier.md">SmartDeviceCarrier</a>| Assignment of mobile carrier. |
| dynamicImageExtensions| enum <a href="../data/DynamicImageExtensions.md">DynamicImageExtensions</a>| Flag of Dynamic Image Extensions. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

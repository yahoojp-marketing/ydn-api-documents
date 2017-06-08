# AdGroup
The Ad Group object is a container for storing ad group information.

### Service
+ [AdGroupService](../services/AdGroupService.md)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>get</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>The account ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement<br>NotUpdatable</td>
  <td>Requirement<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>campaignId</td>
  <td>xsd:long</td>
  <td>The campaign ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement<br>NotUpdatable</td>
  <td>Requirement<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>campaignName</td>
  <td>xsd:string</td>
  <td>The campaign name.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adGroupId</td>
  <td>xsd:long</td>
  <td>The ad group ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement<br>NotUpdatable</td>
  <td>Requirement<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>adGroupName</td>
  <td>xsd:string</td>
  <td>The ad group name.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>userStatus</td>
  <td>enum<br><a href="./UserStatus.md">UserStatus</a></td>
  <td>Display status.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>bid</td>
  <td>AdGroupBid<br>inherited<br>
  <a href="./ManualCPCAdGroupBid.md">ManualCPCAdGroupBid</a><br>
  <a href="./ManualCPVAdGroupBid.md">ManualCPVAdGroupBid</a><br></td>  
  <td>The bid amount.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
<tr>
  <td>device [0...5]</td>
  <td>enum<br><a href="./DeviceType.md">DeviceType</a></td>  
  <td>Type of device for ad delivery.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
<tr>
  <td>deviceApp[0...3]</td>
  <td>enum<br><a href="./DeviceAppType.md">DeviceAppType</a></td>  
  <td>Type of Application for ad delivery.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
<tr>
  <td>deviceOs [0...3]</td>
  <td>enum<br><a href="./DeviceOsType.md">DeviceOsType</a></td>  
  <td>Type of OS for ad delivery.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
<tr>
  <td>smartDeviceCarriers[0...5]</td>
  <td>enum<br><a href="./SmartDeviceCarrier.md">SmartDeviceCarrier</a></td>  
  <td>Type of mobile carrier for ad delivery.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
<tr>
  <td>dynamicImageExtensions</td>
  <td>enum<br><a href="../data/DynamicImageExtensions.md">DynamicImageExtensions</a></td>  
  <td>Flag of Dynamic Image Extensions.<br>※Default is set as "PAUSED".</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

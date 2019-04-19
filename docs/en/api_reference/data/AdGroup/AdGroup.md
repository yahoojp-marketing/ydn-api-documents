# AdGroup
The Ad Group object is a container for storing ad group information.
### Service
+ [AdGroupService](../../services/AdGroupService.md)

### Namespace
[AdGroupService#Namespace](../../services/AdGroupService.md#namespace)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>Account ID.</td>
  <td>yes</td>
  <td>Required</td>
  <td>Required<br>NotUpdatable</td>
  <td>Required<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>campaignId</td>
  <td>xsd:long</td>
  <td>Campaign ID.</td>
  <td>yes</td>
 <td>Required</td>
  <td>Required<br>NotUpdatable</td>
  <td>Required<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>campaignName</td>
  <td>xsd:string</td>
  <td>Campaign name.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>adGroupId</td>
  <td>xsd:long</td>
  <td>Ad group ID.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Required<br>NotUpdatable</td>
  <td>Required<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>adGroupName</td>
  <td>xsd:string</td>
  <td>Ad group name.</td>
  <td>yes</td>
  <td>Required</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>userStatus</td>
  <td>enum<br><a href="./UserStatus.md">UserStatus</a></td>
  <td>Delivery status.</td>
  <td>yes</td>
  <td>Required</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>bid</td>
  <td>AdGroupBid<br>
  inherited <a href="./ManualCPCAdGroupBid.md">ManualCPCAdGroupBid</a><br>
  inherited <a href="./ManualCPVAdGroupBid.md">ManualCPVAdGroupBid</a>
  </td>
  <td>Bid amount.</td>
  <td>yes</td>
  <td>Required</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
   <td>conversionOptimizer</td>
  <td>AdGroupConversionOptimizer<br>
inherited <a href="./NoneAdGroupConversionOptimizer.md">NoneAdGroupConversionOptimizer</a><br>
inherited <a href="./ManualAdGroupConversionOptimizer.md">ManualAdGroupConversionOptimizer</a><br>
inherited <a href="./AutoAdGroupConversionOptimizer.md">AutoAdGroupConversionOptimizer</a>
  </td>
  <td>Conversion optimize.</td>
  <td>yes</td>
  <td>Optional<br>Default: NoneAdGroupConversionOptimizer</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
<tr>
<tr>
  <td>device [0...5]</td>
  <td>enum<br><a href="./DeviceType.md">DeviceType</a></td>
  <td>Type of device for ad delivery.</td>
  <td>yes</td>
  <td>Required</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
<tr>
  <td>deviceApp[0...3]</td>
  <td>enum<br><a href="./DeviceAppType.md">DeviceAppType</a></td>
  <td>Type of Application for ad delivery.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
<tr>
  <td>deviceOs [0...3]</td>
  <td>enum<br><a href="./DeviceOsType.md">DeviceOsType</a></td>
  <td>Type of OS for ad delivery.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
<tr>
  <td>smartDeviceCarriers[0...5]</td>
  <td>enum<br><a href="./SmartDeviceCarrier.md">SmartDeviceCarrier</a></td>
  <td>Type of mobile carrier for ad delivery.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
<tr>
  <td>deviceOsVersion</td>
  <td>xsd:string</td>
  <td>OS version<br>&lowast;To specify null as deviceOsVersion: "NONE"</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
<tr>
  <td>dynamicImageExtensions</td>
  <td>enum<br><a href="DynamicImageExtensions.md">DynamicImageExtensions</a></td>
  <td>Flag of Dynamic Image Extensions.<br>&lowast;Default is set as "PAUSED".</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>labels[0..1000]</td>
  <td>enum<br><a href="./Label.md">Label</a></td>
  <td>Label.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
  <tr>
  <td>feedSetId</td>
  <td>xsd:long</td>
  <td>Feed set ID</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable<</td>
  <td>Ignore</td>
  </tr>
  <tr>
   <td>isRemoveFeedSetId</td>
   <td>xsd:boolean</td>
   <td>Remove association with feed set &lowast;Stop delivery</td>
   <td>yes</td>
   <td>Optional</td>
   <td>Optional<br>Updatable<</td>
   <td>Ignore</td>
  </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

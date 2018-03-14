# Campaign
Campaign object describes campaign information.
### Service
+ [CampaignService](../services/CampaignService.md)

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
  <td>Account ID </td>
  <td>yes</td>
  <td>Required</td>
  <td>Required<br>NotUpdatable</td>
  <td>Required<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>campaignId</td>
  <td>xsd:long</td>
  <td>Campaign ID</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Required<br>NotUpdatable</td>
  <td>Required<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>campaignName</td>
  <td>xsd:string</td>
  <td>Campaign Name</td>
  <td>yes</td>
  <td>Required</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>userStatus</td>
  <td>enum <a href="./UserStatus.md">UserStatus</a></td>
  <td>The setting that can adjust the presence or absence of ad delivery by user.
<br>Filters will contain all ad delivery status if the userStatus is not set.
  </td>
  <td>yes</td>
  <td>Required</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>servingStatus</td>
  <td>enum <a href="./CampaignServingStatus.md">CampaignServingStatus</a></td>
  <td>Delivery status in campaign level<br>
  Display the campaign status, regardless of ad delivery setting by user</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>startDate</td>
  <td>xsd:string</td>
  <td>The start date</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>endDate</td>
  <td>xsd:string</td>
  <td>The end date</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>budget</td>
  <td><a href="./Budget.md">Budget</a></td>
  <td>Campaign Budget</td>
  <td>yes</td>
  <td>Required</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>biddingStrategy</td>
  <td><a href="./BiddingStrategy.md">BiddingStrategy</a></td>
  <td>Container including bidding strategy</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>adProductType</td>
  <td>xsd:string</td>
  <td>Ad product information<br>*Check the available values by get operation on <a href="../services/AccountAdProductService.md">AccountAdProductService</a>.</td>
  <td>yes</td>
  <td>Required</td>
  <td>NotUpdatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>frequencyCap</td>
  <td><a href="./FrequencyCap.md">FrequencyCap</a></td>
  <td>Frequency Cap</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>conversionOptimizer</td>
  <td><a href="./ConversionOptimizer.md">ConversionOptimizer</a></td>
  <td>Conversion Optimize</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>campaignType</td>
  <td>enum <a href="./CampaignType.md">CampaignType </a></td>
  <td>Campaign Type </td>
  <td>yes</td>
  <td>Optional<br>&lowast;Not specified :STANDARD</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>appName</td>
  <td>xsd:string</td>
  <td>App Name</td>
  <td>yes</td>
  <td>Optional<br>&lowast;If campaignType is set to "APP": Required.
  </td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>appId</td>
  <td>xsd:string</td>
  <td>iOS:APP ID<br>Android:Package name</td>
  <td>yes</td>
  <td>Optional<br>&lowast;If campaignType is set to "APP": Required.</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>appOs</td>
  <td>enum <a href="./DeviceOsType.md">DeviceOsType</a></td>
  <td>Device Type of App Install Ads</td>
  <td>yes</td>
  <td>Optional<br>&lowast;If campaignType is set to "APP": Required.</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 </table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

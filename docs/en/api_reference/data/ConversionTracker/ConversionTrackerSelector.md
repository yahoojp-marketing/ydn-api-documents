# ConversionTrackerSelector
ConversionTrackerSelector object contains a set of criteria (parameters) for get method.
### Service
+ [ConversionTrackerService](../../services/ConversionTrackerService.md)

### Namespace
[ConversionTrackerService#Namespace](../../services/ConversionTrackerService.md#namespace)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>get</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>Account ID.</td>
  <td>Required</td>
 </tr>
 <tr>
  <td>conversionTrackerIds[0..1000]</td>
  <td>xsd:long[]</td>
  <td>Conversion Tracker ID.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>conversionTrackerTypes[0..2]</td>
  <td>enum <a href="./ConversionTrackerType.md">ConversionTrackerType</a></td>
  <td>Conversion Type.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>statuses[0..2]</td>
  <td>enum <a href="./ConversionTrackerStatus.md">ConversionTrackerStatus</a></td>
  <td>Conversion Tracker Status.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>categories[0..7]</td>
  <td>enum <a href="./ConversionTrackerCategory.md">ConversionTrackerCategory</a></td>
  <td>Conversion Category subjected to Tracking.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>appIds[0..1000]</td>
  <td>xsd:string</td>
  <td>App ID.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>countingType</td>
  <td>enum <a href="./ConversionCountingType.md">ConversionCountingType</a></td>
  <td>Method of measurement conversion.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>excludeFromBidding</td>
  <td>enum <a href="./ExcludeFromBidding.md">ExcludeFromBidding</a></td>
  <td>Setting for exclude from Bidding.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>appPlatform</td>
  <td>enum <a href="./AppConversionPlatform.md">AppConversionPlatform</a></td>
  <td>Platform subjected to App Conversion.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>statsPeriod</td>
  <td>enum <a href="./StatsPeriod.md">StatsPeriod</a></td>
  <td>Summarized period of statistics.<br>&lowast;None : REALTIME_TODAY.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>statsPeriodCustomDate</td>
  <td><a href="./StatsPeriodCustomDate.md">StatsPeriodCustomDate</a></td>
  <td>Summarized period of statistics. Can be specified by year, month and day.<br>&lowast;Specification is required if StatsPeriod is "CUSTOM_DATE".</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>paging</td>
  <td><a href="../Common/Paging.md">Paging</a></td>
  <td>Page returned as response.</td>
  <td>Optional</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

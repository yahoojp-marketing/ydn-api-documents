# ConversionTracker
ConversionTracker object shows ConversionTracker information such as ConversionTag and performance data by tag.


### Service
+ [ConversionTrackerService](../../services/ConversionTrackerService.md)

### Namespace
[ConversionTrackerService#Namespace](../../services/ConversionTrackerService.md#namespace)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>add</th>
  <th>set</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td> Account ID</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>conversionTrackerId</td>
  <td>xsd:long</td>
  <td> Conversion Tracker ID</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Required</td>
 </tr>
 <tr>
  <td>conversionTrackerName</td>
  <td>xsd:string</td>
  <td> Conversion Tracker Name</td>
  <td>yes</td>
  <td>Required</td>
  <td>Optional<br>Updatable	</td>
 </tr>
 <tr>
  <td>status</td>
  <td>enum <a href="./ConversionTrackerStatus.md">ConversionTrackerStatus</a></td>
  <td> Conversion Tracker Status</td>
  <td>yes</td>
  <td>Required</td>
  <td>Optional<br>Updatable	</td>
 </tr>
 <tr>
  <td>category</td>
  <td>enum <a href="./ConversionTrackerCategory.md">ConversionTrackerCategory</a></td>
  <td> Conversion category for tracking</td>
  <td>yes</td>
  <td>Required</td>
  <td>Optional<br>Updatable	</td>
 </tr>
 <tr>
  <td>conversions</td>
  <td>xsd:long</td>
  <td> Number of Conversions<br>&lowast;Contains conversions that were made across devices</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>conversionValue</td>
  <td>xsd:long</td>
  <td> Values of Conversions<br>&lowast;Contains conversions that were made across devices</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
<tr>
  <td>userRevenueValue</td>
  <td>xsd:long</td>
  <td> Revenue value for Conversions</td>
  <td>yes</td>
  <td>Optional<br>&lowast;Default value: 0</td>
  <td>Optional<br>Updatable	</td>
 </tr>
 <tr>
  <td>conversionTrackerType</td>
  <td>enum <a href="./ConversionTrackerType.md">ConversionTrackerType</a></td>
  <td> Conversion Type</td>
  <td>yes</td>
  <td>Required</td>
  <td>Required</td>
 </tr>
   <tr>
  <td>countingType</td>
  <td>enum <a href="./ConversionCountingType.md">ConversionCountingType</a></td>
  <td> The selected option for counting type for Conversion tracking.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>measurementPeriod</td>
  <td>xsd:int</td>
  <td>Counting period (Unit: Day) <br>&lowast;within the range of 7 to 90 days</td>
  <td>yes</td>
  <td>Optional<br>&lowast;Default value: 30</td>
  <td>Optional</td>
 </tr>
  <tr>
  <td>excludeFromBidding</td>
  <td>enum <a href="./ExcludeFromBidding.md">ExcludeFromBidding</a></td>
  <td>Describes whether using the item for auto bidding setting or not.<br>*'Conversion Counting' setting</td>
  <td>yes</td>
  <td>Opitonal<br>Default：FALSE(include)</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>allConversions</td>
  <td>xsd:long</td>
  <td> Conversion count of Auto bidding + Negative conversion count.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>allConversionValue</td>
  <td>xsd:string</td>
  <td> Conversion value of Auto bidding + Negative conversion value.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>mostRecentConversionDate</td>
  <td>xsd:string</td>
  <td>The date of the most recent conversion<br>(YYYYMMDD)</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

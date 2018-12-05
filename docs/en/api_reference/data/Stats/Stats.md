# Stats
Stats object contains the stats information.

### Service
+ [StatsService](../../services/StatsService.md)

### Namespace
[StatsService#Namespace](../../services/StatsService.md#namespace)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
 </tr>
 <tr>
  <td>imps</td>
  <td>xsd:long</td>
  <td>Number of impressions</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>clickRate</td>
  <td>xsd:double</td>
  <td>Click through rate</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>totalClickCost</td>
  <td>xsd:double</td>
  <td>Total value of click cost</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>clickCnt</td>
  <td>xsd:long</td>
  <td>Number of clicks</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>avgClickCost</td>
  <td>xsd:double</td>
  <td>Average of click cost</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>conversions</td>
  <td>xsd:string</td>
  <td>Conversions<br>&lowast;Contains cross-device conversions (including video view)</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>conversionRate</td>
  <td>xsd:double</td>
  <td>Conversion Rate<br>&lowast;Contains cross-device conversions (including video view)</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>cpa</td>
  <td>xsd:string</td>
  <td>Conversion cost per acquisition<br>&lowast;Contains cross-device conversions (including video view)</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>conversionValue</td>
  <td>xsd:string</td>
  <td>Conversion value<br>&lowast;Contains cross-device conversions (including video view)</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>valuePerConversions</td>
  <td>xsd:string</td>
  <td>Value per Conversions<br>&lowast;Contains cross-device conversions (including video view)</td>
  <td>yes</td>
 </tr>

 <tr>
  <td>conversionsViaAdClick</td>
  <td>xsd:long</td>
  <td>Conversions(after click)</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>conversionRateViaAdClick</td>
  <td>xsd:double</td>
  <td>Conversion rate(after click)</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>cpaViaAdClick</td>
  <td>xsd:string</td>
  <td>Conversion cost per acquisition(after click)</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>conversionValueViaAdClick</td>
  <td>xsd:string</td>
  <td>Conversion value(after click)</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>valuePerConversionsViaAdClick</td>
  <td>xsd:string</td>
  <td>Value per Conversions(after click)</td>
  <td>yes</td>
 </tr>

 <tr>
  <td>allConversions</td>
  <td>xsd:long</td>
  <td>All Conversions<br>&lowast;Contains cross-device conversions (including video view)</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>allConversionRate</td>
  <td>xsd:double</td>
  <td>All Conversions rate<br>&lowast;Contains cross-device conversions (including video view)</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>allCpa</td>
  <td>xsd:string</td>
  <td>Cost per All Conversions<br>&lowast;Contains cross-device conversions (including video view)</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>allConversionValue</td>
  <td>xsd:string</td>
  <td>All Conversions value<br>&lowast;Contains cross-device conversions (including video view)</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>valuePerAllConversions</td>
  <td>xsd:string</td>
  <td>Value per All Conversions</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>crossDeviceConversions</td>
  <td>xsd:long</td>
  <td>Conversion count that were made across devices</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>avgDeliverRank</td>
  <td>xsd:double</td>
  <td>Average display position of the ads (the average of eCPM rank on ads delivery)</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>totalVimps</td>
  <td>xsd:long</td>
  <td>Impressions for the measurement object</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>vimps</td>
  <td>xsd:long</td>
  <td>Viewable impressions</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>inViewClickCnt</td>
  <td>xsd:long</td>
  <td>Viewable clicks</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>inViewRate</td>
  <td>xsd:double</td>
  <td>Viewable impression rate</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>inViewClickRate</td>
  <td>xsd:double</td>
  <td>Viewable click through rate</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>paidVideoViews</td>
  <td>xsd:long</td>
  <td>Number of paid video views<br>&lowast;For Video Ads only</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>paidVideoViewRate</td>
  <td>xsd:double</td>
  <td>Number of paid video rate<br>&lowast;For Video Ads only</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>averageCpv</td>
  <td>xsd:double</td>
  <td>Average CPV<br>&lowast;For Video Ads only</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>videoViews</td>
  <td>xsd:long</td>
  <td>Number of the video views<br>&lowast;For Video Ads only</td>
  <td>yes</td>
 </tr>
 <tr>
  <td>videoViewsTo25</td>
  <td>xsd:long</td>
  <td>The number of times of video viewed over 25%<br>&lowast;For Video Ads only</td>
  <td>yes</td>
 </tr>
<tr>
  <td>videoViewsTo50</td>
  <td>xsd:long</td>
  <td>The number of times of video viewed over 50%<br>&lowast;For Video Ads only</td>
  <td>yes</td>
 </tr>
<tr>
  <td>videoViewsTo75</td>
  <td>xsd:long</td>
  <td>The number of times of video viewed over 75%<br>&lowast;For Video Ads only</td>
  <td>yes</td>
 </tr>
<tr>
  <td>videoViewsTo95</td>
  <td>xsd:long</td>
  <td>The number of times of video viewed over 95%<br>&lowast;For Video Ads only</td>
  <td>yes</td>
 </tr>
<tr>
  <td>videoViewsTo100</td>
  <td>xsd:long</td>
  <td>The number of times of video viewed 100%<br>&lowast;For Video Ads only</td>
  <td>yes</td>
 </tr>
<tr>
  <td>videoViewsTo3Sec</td>
  <td>xsd:long</td>
  <td>The number of times video viewed over 3 seconds<br>&lowast;For Video Ads only</td>
  <td>yes</td>
 </tr> 
<tr>
  <td>averageRateVideoViewed</td>
  <td>xsd:double</td>
  <td>Average % of Video Viewed (Average value of the video viewed rate)<br>&lowast;For Video Ads only</td>
  <td>yes</td>
 </tr>
<tr>
  <td>averageDurationVideoViewed</td>
  <td>xsd:double</td>
  <td>Average Duration of Video Viewed<br>&lowast;For Video Ads only</td>
  <td>yes</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

# Stats
Stats object serves the stats information.

### Service
+ [StatsService](../services/StatsService.md)
 
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
  <td>imps</td>
  <td>xsd:long</td>
  <td>Number of impressions</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>clickRate</td>
  <td>xsd:double</td>
  <td>Number of click through rate.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>totalClickCost</td>
  <td>xsd:long</td>
  <td>Total value of click cost.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>clickCnt</td>
  <td>xsd:long</td>
  <td>Number of clicks</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>avgClickCost</td>
  <td>xsd:double</td>
  <td>Average of click cost.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
  <tr>
  <td>convCnt</td>
  <td>xsd:long</td>
  <td>Number of conversions occurs via your ads.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>convRate</td>
  <td>xsd:double</td>
  <td>Number of conversion rate.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>cpa</td>
  <td>xsd:double</td>
  <td>Conversion cost per acquisition.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
  <tr>
  <td>avgDeliverRank</td>
  <td>xsd:double</td>
  <td>Average display position of your ads, i.e. the average of eCPM rank on ad delivery.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>totalVimps</td>
  <td>xsd:long</td>
  <td>Total number of impressions on the measurement object.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>vimps</td>
  <td>xsd:long</td>
  <td>Number of impressions on the measurement object.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>inViewClickCnt</td>
  <td>xsd:long</td>
  <td>Number of viewable clicks.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>inViewRate</td>
  <td>xsd:double</td>
  <td>Number of viewable impression rate.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>inViewClickRate</td>
  <td>xsd:double</td>
  <td>Number of viewable click through rate.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>autoVideoPlays</td>
  <td>xsd:long</td>
  <td>Number of times the video played automatically. <br>※For Video Ads only.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>clickVideoPlays</td>
  <td>xsd:long</td>
  <td>Number of times the video played by user's click. <br>※For Video Ads only.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>videoViewedRate</td>
  <td>xsd:double</td>
  <td>The rate of video plays (Number of video plays/Impressions). <br>※For Video Ads only.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>averageCpv</td>
  <td>xsd:double</td>
  <td>Average CPV. <br>※For Video Ads only.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>videoPlays</td>
  <td>xsd:long</td>
  <td>Number of the video viewed. <br>※For Video Ads only.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>videoViewsTo25</td>
  <td>xsd:long</td>
  <td>The number of times of video viewed over 25%. <br>※For Video Ads only.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>videoViewsTo50</td>
  <td>xsd:long</td>
  <td>The number of times of video viewed over 50%. <br>※For Video Ads only.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>videoViewsTo75</td>
  <td>xsd:long</td>
  <td>The number of times of video viewed over 75%. <br>※For Video Ads only.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>videoViewsTo95</td>
  <td>xsd:long</td>
  <td>The number of times of video viewed over 95%. <br>※For Video Ads only.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>videoViewsTo100</td>
  <td>xsd:long</td>
  <td>The number of times of video viewed 100%. <br>※For Video Ads only.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>averageRateVideoViewed</td>
  <td>xsd:double</td>
  <td>Average % of Video Viewed (Average value of the video viewed rate). <br>※For Video Ads only.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>averageDurationVideoViewed</td>
  <td>xsd:double</td>
  <td>Average Duration of Video Viewed. <br>※For Video Ads only.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

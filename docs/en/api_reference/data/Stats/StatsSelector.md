# StatsSelector
StatsSelector object is a container that includes the search conditions (execution parameters) of get methods.

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
  <th>get</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>Account ID.</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>campaignIds[0...500]</td>
  <td>xsd:long</td>
  <td>Campaign ID.<br>Available only when "CAMPAIGN" or "ADGROUP" or "AD" or "TARGET" is specified for statsType.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adGroupIds[0..500]</td>
  <td>xsd:long</td>
  <td>Ad group ID. <br>Available only when "ADGROUP" or "AD" or "TARGET" is specified for statsType.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adIds[0..500]</td>
  <td>xsd:long</td>
  <td>Ad ID.<br>Available only when "AD" is specified for statsType.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>medialds[0..500]</td>
  <td>xsd:long</td>
  <td>Media ID.<br>Available only when "MEDIA" is specified for statsType.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>targetTypes[0..1]</td>
  <td>enum<br><a href="./TargetType.md">TargetType</a></td>
  <td>Target Type.<br>Specification is required when statsType is "TARGET".</td>
  <td>yes</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>statsPeriod</td>
  <td>enum<br><a href="./StatsPeriod.md">StatsPeriod</a></td>
  <td>Aggregation period of statistics.<br>Default is "REALTIME_MONTH".</td>
  <td>yes</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>statsPeriodCustomDate</td>
  <td>enum<br><a href="./StatsPeriodCustomDate.md">StatsPeriodCustomDate</a></td>
  <td>Aggregation period of statistics. Can be specified by year, month and day.<br>&lowast; Specification is required when StatsPeriod is "CUSTOM_DATE".</td>
  <td>yes</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>statsType</td>
  <td>enum<br><a href="./StatsType.md">StatsType</a></td>
  <td>Type of statistics.<br>Default is "CAMPAIGN".</td>
  <td>yes</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>paging</td>
  <td><a href="../Common/Paging.md">Paging</a></td>
  <td>Paging for the response.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">
<img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" />
</a><br />
この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">
クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>


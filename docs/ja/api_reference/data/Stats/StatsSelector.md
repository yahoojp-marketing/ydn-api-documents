# StatsSelector
StatsSelectorオブジェクトは、getメソッドの検索条件（実行パラメータ）を保持します。

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
  <td>アカウントIDです。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>campaignIds[0...500]</td>
  <td>xsd:long</td>
  <td>キャンペーンIDです。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adGroupIds[0..500]</td>
  <td>xsd:long</td>
  <td>広告グループIDです。<br>statsTypeで「ADGROUP」または「AD」を指定した場合のみ有効です。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adIds[0..500]</td>
  <td>xsd:long</td>
  <td>広告IDです。<br>statsTypeで「AD」を指定した場合のみ有効です。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>medialds[0..500]</td>
  <td>xsd:long</td>
  <td>画像IDです。<br>statsTypeで「MEDIA」を指定した場合のみ有効です。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>statsPeriod</td>
  <td>enum<br>
  <a href="./StatsPeriod.md">StatsPeriod</a></td>
  <td>統計情報の集計期間です。<br>デフォルトでは「REALTIME_MONTH」に設定されています。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>statsType</td>
  <td>enum<br>
  <a href="./StatsType.md">StatsType</a></td>
  <td>統計情報の種別です。<br>デフォルトでは「CAMPAIGN」に設定されています。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>paging</td>
  <td><a href="../Common/Paging.md">Paging</a></td>
  <td>ページ設定情報です。</td>
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

# ConversionTrackerSelector
ConversionTrackerSelectorオブジェクトは、getメソッドの検索条件（実行パラメータ）を保持します。

### Service
+ [ConversionTrackerService](../services/ConversionTrackerService.md)

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
  <td>アカウントIDです。</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>conversionTrackerIds[0..1000]</td>
  <td>xsd:long[]</td>
  <td>コンバージョントラッカーのIDです。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>conversionTrackerTypes[0..2]</td>
  <td>enum <a href="./ConversionTrackerType.md">ConversionTrackerType</a></td>
  <td>コンバージョン種別です。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>statuses[0..2]</td>
  <td>enum <a href="./ConversionTrackerStatus.md">ConversionTrackerStatus</a></td>
  <td>コンバージョントラッカーのステータスです。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>categories[0..7]</td>
  <td>enum <a href="./ConversionTrackerCategory.md">ConversionTrackerCategory</a></td>
  <td>トラッキング対象となるコンバージョンのカテゴリーです。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>appIds[0..1000]</td>
  <td>xsd:string</td>
  <td>アプリIDです。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>appPlatform</td>
  <td>enum <a href="./AppConversionPlatform.md">AppConversionPlatform</a></td>
  <td>アプリコンバージョンの対象プラットフォームです。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>statsPeriod</td>
  <td>enum <a href="./StatsPeriod.md">StatsPeriod</a></td>
  <td>統計情報の集計期間です。<br>
  ※指定なし：REALTIME_TODAY
  </td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>paging</td>
  <td><a href="./Paging.md">Paging</a></td>
  <td>データの取得範囲です。</td>
  <td>Optional</td>
</table> 

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

# ConversionTracker
ConversionTrackerオブジェクトは、コンバージョン測定タグやタグごとのパフォーマンスデータなどのコンバージョントラッカー情報を表します。

### Service
+ [ConversionTrackerService](../services/ConversionTrackerService.md)

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
  <td>アカウントIDです。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>conversionTrackerId</td>
  <td>xsd:long</td>
  <td>コンバージョントラッカーIDです。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Required</td>
 </tr>
 <tr>
  <td>conversionTrackerName</td>
  <td>xsd:string</td>
  <td>コンバージョントラッカー名です。</td>
  <td>yes</td>
  <td>Required</td>
  <td>Optional<br>Updatable	</td>
 </tr>
 <tr>
  <td>status</td>
  <td>enum <a href="./ConversionTrackerStatus.md">ConversionTrackerStatus</a></td>
  <td>コンバージョントラッカーのステータスです。</td>
  <td>yes</td>
  <td>Required</td>
  <td>Optional<br>Updatable	</td>
 </tr>
 <tr>
  <td>category</td>
  <td>enum <a href="./ConversionTrackerCategory.md">ConversionTrackerCategory</a></td>
  <td>トラッキングするコンバージョンのカテゴリーです。</td>
  <td>yes</td>
  <td>Required</td>
  <td>Optional<br>Updatable	</td>
 </tr>
 <tr>
  <td>conversions</td>
  <td>xsd:long</td>
  <td>コンバージョン数です。<br>※デバイスをまたいだコンバージョンの値を加味します。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>conversionValue</td>
  <td>xsd:long</td>
  <td>コンバージョン値です。<br>※デバイスをまたいだコンバージョンの値を加味します。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
<tr>
  <td>userRevenueValue</td>
  <td>xsd:long</td>
  <td>コンバージョンの収益値です。</td>
  <td>yes</td>
  <td>Optional<br>※Default値：0</td>
  <td>Optional<br>Updatable	</td>
 </tr>
 <tr>
  <td>conversionTrackerType</td>
  <td>enum <a href="./ConversionTrackerType.md">ConversionTrackerType</a></td>
  <td>コンバージョン種別です。</td>
  <td>yes</td>
  <td>Required</td>
  <td>Required</td>
 </tr>
 <tr>
  <td>measurementPeriod</td>
  <td>xsd:int</td>
  <td>計測期間（単位：日）です。<br>※7～90の範囲内で指定可能</td>
  <td>yes</td>
  <td>Optional<br>※Default値：30</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>mostRecentConversionDate</td>
  <td>xsd:string</td>
  <td>コンバージョンが発生した直近の日付です。<br>（YYYYMMDD）</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

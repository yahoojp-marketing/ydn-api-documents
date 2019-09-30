# ReportRecord
ReportRecordオブジェクトは、レポートの情報を表します。

### Service
+ [ReportService](../../services/ReportService.md)

### Namespace
[ReportService#Namespace](../../services/ReportService.md#namespace)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>add</th>
  <th>remove</th>
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
  <td>reportJobId</td>
  <td>xsd:long</td>
  <td>レポートジョブIDです。</td>
  <td>yes<br>※remove時のみ返却されます。</td>
  <td>Ignore</td>
  <td>Requirement<br>NonUpdatable</td>
 </tr>
 <tr>
  <td>reportId</td>
  <td>xsd:long</td>
  <td>レポートIDです。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>reportName</td>
  <td>xsd:string</td>
  <td>レポート名です。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>requestTime</td>
  <td>xsd:string</td>
  <td>ジョブ依頼日時です。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>completeTime</td>
  <td>xsd:string</td>
  <td>ジョブ完了日時です。</td>
  <td>yes<br>※ジョブ登録の完了後に返却されます。</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>dateRangeType</td>
  <td>enum <a href="./ReportDateRangeType.md">ReportDateRangeType</a></td>
  <td>集計期間タイプです。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>dateRange</td>
  <td><a href="./ReportDateRange.md">ReportDateRange</a></td>
  <td>集計期間です。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>status</td>
  <td>enum <a href="./ReportJobStatus.md">ReportJobStatus</a></td>
  <td>ジョブステータスです。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>jobErrorDetail</td>
  <td>xsd:string</td>
  <td>ジョブエラー詳細です。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>reportDownloadUrl</td>
  <td>xsd:string</td>
  <td>レポートのダウンロードURLです。<br>statusがCOMPLETEDの場合に値が設定されます。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
</table> 

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

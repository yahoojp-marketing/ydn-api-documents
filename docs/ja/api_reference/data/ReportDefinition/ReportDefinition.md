# ReportDefinition
ReportDefinitionオブジェクトは、レポート定義を表します。
### Service
+ [ReportDefinitionService](../../services/ReportDefinitionService.md)

### Namespace
[ReportDefinitionService#Namespace](../../services/ReportDefinitionService.md#namespace)

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
  <td>reportJobStatus</td>
  <td>enum <a href="./ReportJobStatus.md">ReportJobStatus</a></td>
  <td>ジョブステータスです。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>reportJobErrorDetail</td>
  <td>xsd:string</td>
  <td>ジョブエラー詳細です。</td>
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
  <td>reportDownloadURL</td>
  <td>xsd:string</td>
  <td>レポートのダウンロードURLです。<br>statusがCOMPLETEDの場合に値が設定されます。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr> 
 <tr>
  <td>reportName</td>
  <td>xsd:string</td>
  <td>レポート名です。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>dateRangeType</td>
  <td>enum<br><a href="./ReportDateRangeType.md">ReportDateRangeType</a></td>
  <td>集計期間種別です。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>dateRange</td>
  <td>enum<br><a href="./ReportDateRange.md">ReportDateRange</a></td>
  <td>集計期間です。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>frequencyRange</td>
  <td>enum<br><a href="./ReportFrequencyRange.md">ReportFrequencyRange</a></td>
  <td>フリークエンシーの集計期間です。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>filters[0..6]</td>
  <td><a href="./ReportFilter.md">ReportFilter</a></td>
  <td>レポートのフィルターです。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>sortFields[]</td>
  <td>xsd:string</td>
  <td>ソートです。ソートしたいフィールドを選択してください。<br>
  ・最大で5つまで指定可能です。<br>
  ・指定フィールドの前に"+"を追加すると昇順、"-"を追加すると降順で表示されます。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>fields[]</td>
  <td>xsd:string</td>
  <td>表示項目です。<br>入力可能な値は、<a href="../../appendix/reports.md">レポートフィールドページ</a>でご確認ください。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>format</td>
  <td>enum<br><a href="./ReportDownloadFormat.md">ReportDownloadFormat</a></td>
  <td>ファイル出力形式です。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>encode</td>
  <td>enum<br><a href="./ReportDownloadEncode.md">ReportDownloadEncode</a></td>
  <td>出力文字コードです。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>compress</td>
  <td>enum<br><a href="./ReportZip.md">ReportZip</a></td>
  <td>zip化の有無です。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>language</td>
  <td>enum<br><a href="./ReportLang.md">ReportLang</a></td>
  <td>出力言語です。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

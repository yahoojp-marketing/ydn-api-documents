# AuditLogDateRange
AuditLogDateRangeは getDownloadメソッド実行時にダウンロード対象とする更新期間を保持するオブジェクトです。
 
### Service
+ [AuditLogService](../../services/AuditLogService.md)

### Namespace
[AuditLogService#Namespace](../../services/AuditLogService.md#namespace)
 
<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>getDownload</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>startDate</td>
  <td>xsd:string</td>
  <td>開始日付です。<br />
・入力形式：Ymd形式<br />
・デフォルト値：現在の日付<br />
・指定可能範囲：前月の月初<br />
例：4/30時点で、開始日付に 指定できるもっとも古い日付は3/1
</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
<tr>
  <td>endDate</td>
  <td>xsd:string</td>
  <td>終了日付です。<br />
・入力形式：Ymd形式<br />
・デフォルト値：現在の日付<br />
・指定可能範囲：現在の日付<br />
※終了日付は開始日付以降の 日付を指定する<br />
※開始日付から終了日付の 期間は最大1カ月</td>
  <td>-</td>
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

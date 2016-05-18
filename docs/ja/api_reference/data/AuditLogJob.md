# AuditLogJob
AuditLogJobは操作履歴のダウンロードジョブの情報を保持するオブジェクトです。
 
### Service
+ [AuditLogService](../services/AuditLogService.md)
 
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
  <td>accountId</td>
  <td>xsd:long</td>
  <td>アカウントIDです。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>auditLogJobId</td>
  <td>xsd:long</td>
  <td>操作履歴のダウンロードジョブIDです。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>auditLogJobName</td>
  <td>xsd:string</td>
  <td>操作履歴のダウンロードジョブ名です。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>auditLogJobUserName</td>
  <td>xsd:string</td>
  <td>操作履歴ダウンロードジョブの実行ユーザー名です。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>auditLogJobStartDate</td>
  <td>xsd:string</td>
  <td>操作履歴ダウンロードジョブの開始日時です。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>auditLogJobEndDate</td>
  <td>xsd:string</td>
  <td>操作履歴ダウンロードジョブの終了日時です。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>auditLogJobStatus</td>
  <td>enum <br><a href="./AuditLogDownloadJobStatus.md">AuditLogDownloadJobStatus</a></td>
  <td>操作履歴ダウンロードジョブのステータスです。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>progress</td>
  <td>xsd:int</td>
  <td>処理進捗です。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
  <tr>
  <td>downloadAuditLogDownloadUrl</td>
  <td>xsd:string</td>
  <td>操作履歴ダウンロードジョブの結果取得URLです。</td>
  <td>yes</td>
  <td>Ignore</td>
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

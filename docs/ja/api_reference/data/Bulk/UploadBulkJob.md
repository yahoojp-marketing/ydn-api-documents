# UploadBulkJob
UploadBulkJobオブジェクトは、一括アップロードジョブの内容を表します。
### Service
+ [BulkService](../../services/BulkService.md)

### Namespace
[BulkService#Namespace](../../services/BulkService.md#namespace)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>add（upload）</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>アカウントIDです。</td>
  <td>yes</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>uploadBulkJobId</td>
  <td>xsd:long</td>
  <td>バルクジョブIDです。</td>
  <td>yes</td>
  <td>Ignore</td>
 </tr>
  <tr>
  <td>uploadBulkJobName</td>
  <td>xsd:string</td>
  <td>バルクジョブ名です。</td>
  <td>yes</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>uploadBulkUserName</td>
  <td>xsd:string</td>
  <td>バルクジョブ実行ユーザー名です。</td>
  <td>yes</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>uploadBulkStartDate</td>
  <td>xsd:string</td>
  <td>ジョブ開始日時です。</td>
  <td>yes</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>uploadBulkEndDate</td>
  <td>xsd:string</td>
  <td>ジョブ終了日時です。</td>
  <td>yes</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>uploadBulkJobStatus</td>
  <td>enum <a href="UploadBulkJobStatus.md">UploadBulkJobStatus</a></td>
  <td>ジョブステータスです。</td>
  <td>yes</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>processingItemsCount</td>
  <td><a href="ProcessingItemsCount.md">ProcessingItemsCount</a></td>
  <td>処理件数です。</td>
  <td>yes</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>progress</td>
  <td>xsd: int</td>
  <td>処理の進捗です。</td>
  <td>yes</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>downloadBulkUploadFileUrl</td>
  <td>xsd:string</td>
  <td>アップロードしたファイルを取得するURLです。</td>
  <td>yes</td>
  <td>Ignore</td>
 </tr>
 </table> 

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

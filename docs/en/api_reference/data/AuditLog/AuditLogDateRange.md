# AuditLogDateRange
AuditLogDateRange object is container storing the downloading date range of getDownload method.
 
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
  <td>Start date.<br />
- Entry format : Ymd format<br />
- Default value : Current date<br />
- Available range : Beginning of the last month<br />
e.g.: The oldest date selectable as of April 30 is March 1.
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
  <td>End date.<br />
- Entry format : Ymd format<br />
- Default value : Current date<br />
- Available range : Current date<br />
* Enter the date after Start date.<br />
* Maximum length of date range between Start and End is 1 month.</td>
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


# VideoSelector
The VideoSelector object is a container for storing added video information and filtering condition.<br>

### Service
+ [VideoService](../../services/VideoService.md)

### Namespace
[VideoService#Namespace](../../services/VideoService.md#namespace)

<table>
 <tr>
  <th>Field</th>
  <th>Data Type</th>
  <th>Description</th>
  </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>Account ID.</td>
 </tr>
 <tr>
  <td>mediaIds[0..500]</td>
  <td>xsd:long</td>
  <td>Media ID.</td>
 </tr>
 <tr>
  <td>userStatuses[0..2]</td>
  <td>enum<br>
  <a href="./UserStatus.md">UserStatus</a></td>
  <td>Display Status of the video.</td>
 </tr>
 <tr>
  <td>approvalStatuses[0..4]</td>
  <td>enum<br>
  <a href="./ApprovalStatus.md">ApprovalStatus</a></td>
  <td>Approval status of the video on Editorial Review.</td>
 </tr>
 <tr>
  <td>paging</td>
  <td>enum<br>
  <a href="../Common/Paging.md">Paging</a></td>
  <td>Paging.</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>


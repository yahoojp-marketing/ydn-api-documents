# VideoSelector
VideoSelectorオブジェクトは、入稿済みの動画の情報を取得します。<br>

### Service
+ [VideoService](../../services/VideoService.md)

### Namespace
[VideoService#Namespace](../../services/VideoService.md#namespace)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>アカウントIDです。</td>
 </tr>
 <tr>
  <td>mediaIds[0..500]</td>
  <td>xsd:long</td>
  <td>メディアIDです。</td>
 </tr>
 <tr>
  <td>userStatuses[0..2]</td>
  <td>enum<br>
  <a href="./UserStatus.md">UserStatus</a></td>
  <td>動画の配信状況です。</td>
 </tr>
 <tr>
  <td>approvalStatuses[0..4]</td>
  <td>enum<br>
  <a href="ApprovalStatus.md">ApprovalStatus</a></td>
  <td>動画の審査状況です。</td>
 </tr>
 <tr>
  <td>paging</td>
  <td>enum<br>
  <a href="../Common/Paging.md">Paging</a></td>
  <td>取得範囲です。</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

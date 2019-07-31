# Video
Videoオブジェクトは、動画情報を保持します。

### Service
+ [VideoService](../../services/VideoService.md)

### Namespace
[VideoService#Namespace](../../services/VideoService.md#namespace)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>get</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>アカウントIDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement<br>NotUpdatable</td>
  <td>Requirement<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>mediaIds[0..500]</td>
  <td>xsd:long</td>
  <td>メディアIDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement<br>NotUpdatable</td>
  <td>Requirement<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>videoName</td>
  <td>xsd:string</td>
  <td>動画のファイル名です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>videoTitle</td>
  <td>xsd:string</td>
  <td>動画名です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>userStatuses</td>
  <td>enum<br>
  <a href="./UserStatus.md">UserStatus</a></td>
  <td>動画の配信状況です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>creationTime</td>
  <td>xsd:string</td>
  <td>動画の入稿日時です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>approvalStatuses</td>
  <td>enum<br><a href="ApprovalStatus.md">ApprovalStatus</a></td>
  <td>動画の審査状況です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>disapprovalReasonCodes</td>
  <td>xsd:string</td>
  <td>動画の掲載拒否理由です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>processStatus</td>
  <td>enum<br><a href="./VideoProcessStatus.md">VideoProcessStatus</a></td>
  <td>動画の処理状況です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>videoSetting</td>
  <td><a href="./VideoSetting.md">VideoSetting</a></td>
  <td>動画の設定内容です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

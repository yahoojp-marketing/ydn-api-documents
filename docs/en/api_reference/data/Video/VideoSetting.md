# VideoSetting
VideoSetting object stroes the setting information of videos.

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
  <td>videoFileType</td>
  <td>enum<br>
  <a href="./VideoFileType.md">VideoFileType</a></td>
  <td>File type of the video.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>videoAdFormat</td>
  <td>xsd:string</td>
  <td>Ad format type of the video ad.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>fileSize</td>
  <td>xsd:long</td>
  <td>File size of the video.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>width</td>
  <td>xsd:long</td>
  <td>Width of the video.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>height</td>
  <td>xsd:long</td>
  <td>Height (vertical length) of the video.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>playbackTime</td>
  <td>xsd:long</td>
  <td>Play time (sec) of the video.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>downloadOriginalUrl</td>
  <td>xsd:string</td>
  <td>URL for downloading video (original). <br>※This value is not provided for SET and REMOVE request.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>downloadHighBitrateUrl</td>
  <td>xsd:string</td> 
  <td>URL for downloading video (high quality). <br>※This value is not provided for SET and REMOVE request.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>downloadMiddleBitrateUrl</td>
  <td>xsd:string</td>
  <td>URL for downloading video (middle quality).<br>※This value is not provided for SET and REMOVE request.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>downloadLowBitrateUrl</td>
  <td>xsd:string</td>
  <td>URL for downloading video (low quality).<br>※This value is not provided for SET and REMOVE request.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>



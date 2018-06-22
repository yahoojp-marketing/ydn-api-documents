# ImageMedia
The ImageMedia object is a container for storing image.
### Service
+ [MediaService](../../services/MediaService.md)

### Namespace
[MediaService#Namespace](../../services/MediaService.md#namespace)

### Inheritance
+ [Media](./Media.md)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>mediaFileType</td>
  <td>enum <a href="./MediaFileType.md">MediaFileType</a></td>
  <td>The file type of image.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>mediaAdFormat</td>
  <td>xsd:string</td>
  <td>The type of image format.<br>
  *Available format is referable on <a href="../../services/DictionaryService.md">DictionaryService</a>(getMediaAdFormat).
  </td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>fileSize</td>
  <td>xsd:long</td>
  <td>The file size of image. </td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>width</td>
  <td>xsd:long</td>
  <td>The width of image. </td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>height</td>
  <td>xsd:long</td>
  <td>The height of image.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>downloadUrl</td>
  <td>xsd:string</td>
  <td>The URL for downloading image.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>data</td>
  <td>base64Binary</td>
  <td>The image file in base64 encode.</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

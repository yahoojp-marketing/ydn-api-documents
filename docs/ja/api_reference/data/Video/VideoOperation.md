# VideoOperation
VideoOperationオブジェクトは、mutateメソッドの操作対象を保持します。<br>

### Service
+ [VideoService](../../services/VideoService.md)

### Namespace
[VideoService#Namespace](../../services/VideoService.md#namespace)

### Inheritance
+ Operation

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
  <td>xsd:long</a>
</td>
  <td>アカウントIDです。</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>operand[0..200]</td>
  <td><a href="./Video.md">Video</a>
</td>
  <td>操作対象の動画のリストです。</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

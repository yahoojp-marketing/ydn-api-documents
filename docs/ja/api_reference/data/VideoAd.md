# VideoAd
VideoAdオブジェクトは、動画広告の情報を表します。<br>
 
### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

### Inheritance
+ [Ad](./Ad.md)
 
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
  <td>thumbnailMediaId</td>
  <td>xsd:long</td>
  <td>サムネイルIDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>headline</td>
  <td>xsd:string</td>
  <td>広告のタイトルです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>description</td>
  <td>xsd:string</td>
  <td>広告の説明文です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>url</td>
  <td>xsd:string</td>
  <td>リンク先URLです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>displayUrl</td>
  <td>xsd:string</td>
  <td>表示URLです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>buttonText</td>
  <td>enum<br><a href="./ButtonText.md">ButtonText</a></td>
  <td>広告のボタンに表示されるテキストです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>principal</td>
  <td>xsd:string</td>
  <td>広告の主体者表記です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>logoMediaId</td>
  <td>xsd:long</td>
  <td>ロゴの画像IDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
</table>

 
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>


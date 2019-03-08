# DynamicAd
DynamicAd object describes dynamic ad informationinfomation of dynamic ads for display.

### Service
+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace
[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

### Inheritance
+ [Ad](./Ad.md)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description.</th>
  <th>response</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>url</td>
  <td>xsd:string</td>
  <td>Destination URL.</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>displayUrl</td>
  <td>xsd:string</td>
  <td>Display URL.</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>buttonText</td>
  <td>enum <a href="./ButtonText.md">ButtonText</a></td>
  <td>Text for display ad button.</td>
  <td>yes</td>
  <td>Optional<br>&lowast;Default: BUTTON_MORE</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>principal</td>
  <td>xsd:string</td>
  <td>Advertiser Indication.</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>logoMediaId</td>
  <td>xsd:long</td>
  <td>Media ID of logo image.</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>logoMediaId2</td>
  <td>xsd:long</td>
  <td>Media ID of logo image 2.</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>logoMediaId3</td>
  <td>xsd:long</td>
  <td>Media ID of logo image 3.</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>prefix</td>
  <td>xsd:string</td>
  <td>Prefix.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>suffix</td>
  <td>xsd:string</td>
  <td>Suffix.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>brandColor</td>
  <td>xsd:string</td>
  <td>Brand color<br/>Format :RGB or HEX<br/>e.g.：#FFFFFF</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
</table>


<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>


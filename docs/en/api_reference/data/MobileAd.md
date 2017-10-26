# MobileAd
MobileAd object describes mobile ad information.

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
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>url</td>
  <td>xsd:string</td>
  <td>Destination URL</td>
  <td>yes</td>
  <td>Required</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <tr>
  <td>displayUrl</td>
  <td>xsd:string</td>
  <td>Display URL</td>
  <td>yes</td>
  <td>Optional<br>
  <br>
  &lowast;Default value<br>
  -Standard campaign:<br>required<br>
  -Mobile app campaign (iOS) :<br>"itunes.apple.com"<br>
  -Mobile app campaign (Android) :<br>"play.google.com"
</td>
  <td>Optional<br>Updatable<br>
  <br>
  &lowast;Input allowed<br>
  -Mobile app campaign (iOS) :<br>Available only for "itunes.apple.com"<br>
  -Mobile app campaign (Android) :<br>Available only for "play.google.com"
  </td>
  <td>Ignore</td>
 </tr>
 <tr>
  <tr>
  <td>headline</td>
  <td>xsd:string</td>
  <td>Title</td>
  <td>yes</td>
  <td>Required</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <tr>
  <td>description</td>
  <td>xsd:string</td>
  <td>Description text (line 1)</td>
  <td>yes</td>
  <td>Required</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <tr>
  <td>description2</td>
  <td>xsd:string</td>
  <td>Description text (line 2)</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <tr>
  <td>mobileCarriers[0..4]</td>
  <td><a href="./CarrierName.md">CarrierName</a></td>
  <td>Mobile carrier.</td>
  <td>yes</td>
  <td>Required</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 </table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

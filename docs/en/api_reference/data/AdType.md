# AdType (enum)
AdType describes the type of ad.<br>
In addition, the number of available characters of ad creatives vary with selected devices.

### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

<table>
 <tr>
  <th>Enumeration </th>
  <th>Type</th>
  <th>Description</th>
 <tr>
  <td>TEXT_LONG_AD1</td>
  <td>xsd:string</td>
  <td>Text ad is "title is 15 characters" and "description is 19 characters / 19 characters".<br>
  It is available for PC, Smartphone and Tablet. (Recommended)</td>
 </tr>
 <tr>
  <td>TEXT_LONG_AD2</td>
  <td>xsd:string</td>
  <td>Text ad is "title is 15 characters" and "description is 33 characters". <br>
  It is available for PC, Smartphone and Tablet.</td>
 </tr>
 <tr>
  <td>TEXT_SHORT_AD1</td>
  <td>xsd:string</td>
  <td>Short text ad is "title is 12 characters" and "description is 12 characters". <br>
  It is available for Mobile.<br>
  &lowast;Currently this ad type is not available for ad creation.</td>
 </tr>
 <tr>
  <td>TEXT_SHORT_AD2</td>
  <td>xsd:string</td>
  <td>Short text ad is "title is 14 characters" and "description is 19 characters". <br>
  It is available for Mobile.<br>
  &lowast;Currently this ad type is not available for ad creation.</td>
 </tr>
 <tr>
  <td>POS_AD</td>
  <td>xsd:string</td>
  <td>Positioning text is "description is 33 characters".</td>
 </tr>
 <tr>
  <td>APP_AD1</td>
  <td>xsd:string</td>
  <td>Ad for Mobile App Install.<br>
  &lowast;Currently this ad type is not available for ad creation.</td>
 </tr>
 <tr>
  <td>RESPONSIVE_AD</td>
  <td>xsd:string</td>
  <td>Responsive Ad which flexibly adjusts its image size and trimmed to the size of ad place.</td>
 </tr>
 <tr>
  <td>STATIC_FRAME_AD</td>
  <td>xsd:string</td>
  <td>Static frame ad which flexibly adjusts to 3 layout types to the size of ad place. <br>
  &lowast;More information about the layout is referable on <a href="./AdLayout.md">AdLayout</a>.</td>
 </tr>
 <tr>
  <td>VIDEO_AD</td>
  <td>xsd:string</td>
  <td>Video ad which displays a specified video on the ad place.</td>
 </tr>
 <tr>
  <td>NONE</td>
  <td>xsd:string</td>
  <td>Image ad which is displayed on the specified ad place and does not require any text within the ad.</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

# VideoAd
VideoAd object displays Video Ads information.

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
  <th>Description</th>
  <th>response</th>

  <th>add</th>
  <th>set</th>
  <th>remove</th>
 <tr>
  <td>thumbnailMediaId</td>
  <td>xsd:long</td>
  <td>Thumbnail ID</td>
  <td>yes</td>

  <td>Required</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>headline</td>
  <td>xsd:string</td>
  <td>Ad title</td>
  <td>yes</td>

  <td>Required</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>description</td>
  <td>xsd:string</td>
  <td>Ad description</td>
  <td>yes</td>

  <td>Required</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>url</td>
  <td>xsd:string</td>
  <td>Destination URL</td>
  <td>yes</td>

  <td>Required</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>displayUrl</td>
  <td>xsd:string</td>
  <td>Display URL</td>
  <td>yes</td>
  <td>Optional<br>
  <br>
  &lowast;Default value<br>
  - Standard campaign：<br>required<br>
  - Mobile app campaign (iOS) : <br>"itunes.apple.com"<br>
  - Mobile app campaign (Android) : <br>"play.google.com"
  </td>
  <td>Optional<br>
  <br>
  &lowast;Input allowed<br>
  - Mobile app campaign (iOS) : <br>Available only for "itunes.apple.com"<br>
  - Mobile app campaign (Android) : <br>Available only for "play.google.com"
  </td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>buttonText</td>
  <td>enum<br><a href="./ButtonText.md">ButtonText</a></td>
  <td>Text for the button displayed on the ad</td>
  <td>yes</td>

  <td>Optional</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>principal</td>
  <td>xsd:string</td>
  <td>Advertiser Indication of the ad</td>
  <td>yes</td>

  <td>Required</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>logoMediaId</td>
  <td>xsd:long</td>
  <td>Logo image ID</td>
  <td>yes</td>

  <td>Optional</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>videoStartBeaconUrls[0..2]</td>
  <td>xsd:string</td>
  <td>Viewing beacon URL (start)<br>&lowast;SET:Replace all urls.<br>&lowast;Available url only for "https".</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>isRemoveVideoStartBeaconUrls</td>
  <td>enum <a href="./IsRemoveFlg.md">isRemoveFlg</td>
  <td>Remove Viewing beacon URL (start)<br>&lowast;Even if "videoStartBeaconUrl" is set, given priority to setting of "isRemoveVideoStartBeaconUrls".</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
<tr>
  <td>video3SecBeaconUrls[0..2]</td>
  <td>xsd:string</td>
  <td>Viewing beacon URL (3 seconds)<br>&lowast;SET:Replace all urls.<br>&lowast;Available url only for "https".</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>isRemoveVideo3SecBeaconUrls</td>
  <td>enum <a href="./IsRemoveFlg.md">isRemoveFlg</td>
  <td>Remove Viewing beacon URL (3 seconds)<br>&lowast;Even if "video3SecBeaconUrl" is set, given priority to setting of "isRemoveVideo3SecBeaconUrls".</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>videoPaidBeaconUrls[0..2]</td>
  <td>xsd:string</td>
  <td>Viewing Beacon URL (paid)	<br>&lowast;SET:Replace all urls.<br>&lowast;Available url only for "https".</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>isRemoveVideoPaidBeaconUrls</td>
  <td>enum <a href="./IsRemoveFlg.md">isRemoveFlg</td>
  <td>Remove Viewing Beacon URL (paid)<br>&lowast;Even if "videoPaidBeaconUrl" is set, given priority to setting of "isRemoveVideoPaidBeaconUrls".</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
  <tr>
  <td>videoCompleteBeaconUrls[0..2]</td>
  <td>xsd:string</td>
  <td>Viewing beacon URL (complete)	<br>&lowast;SET:Overwrite all urls.<br>&lowast;Available url only for "https".</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>isRemoveVideoCompleteBeaconUrls</td>
  <td>enum <a href="./IsRemoveFlg.md">isRemoveFlg</td>
  <td>Remove Viewing beacon URL (complete)<br>&lowast;Even if "videoCompleteBeaconUrl" is set, given priority to setting of "isRemoveVideoCompleteBeaconUrls".</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

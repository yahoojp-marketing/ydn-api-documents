

# ResponsiveVideoAd

ResponsiveVideoAd object displays Video Ads information.

### Service

+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace

[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

### Inheritance

+ [Ad](./Ad.md)

| Field | Type | Description | response | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| thumbnailMediaId | xsd:long | Thumbnail ID | yes | Requirement | Optional | Ignore | |
| headline | xsd:string | Ad title | yes | Requirement | Optional | Ignore | |
| description | xsd:string | Ad description | yes | Requirement | Optional | Ignore | |
| url | xsd:string | Destination URL | yes | Requirement | Optional | Ignore | |
| displayUrl | xsd:string | Display URL | yes | Optional<br><br>  ∗Default value<br>  -Standard campaign:<br>  required<br>  -Mobile app campaign (iOS) :<br>  "itunes.apple.com"<br>  -Mobile app campaign (Android) :<br>  "play.google.com"<br> | Optional<br/>Updatable<br><br>  ∗Input allowed<br>  -Mobile app campaign (iOS) :<br>  "itunes.apple.com"<br>  -Mobile app campaign (Android) :<br>  "play.google.com"<br> | Ignore | |
| buttonText | enum [ButtonText](./ButtonText.md) | Text for the button displayed on the ad | yes | Optional | Optional | Ignore | |
| principal | xsd:string | Advertiser Indication of the ad | yes | Requirement | Optional | Ignore | |
| logoMediaId | xsd:long | Logo image ID | yes | Optional | Optional | Ignore | |
| videoStartBeaconUrls[0..2] | xsd:string | Viewing beacon URL (start)<br/>∗SET:Replace all urls.<br/>∗Available url only for &#34;https&#34;. | yes | Optional | Optional<br/>Updatable | Ignore | |
| isRemoveVideoStartBeaconUrls | enum [isRemoveFlg](./isRemoveFlg.md) | Remove Viewing beacon URL (start)<br/>∗Even if &#34;videoStartBeaconUrl&#34; is set, given priority to setting of &#34;isRemoveVideoStartBeaconUrls&#34;. | yes | Ignore | Optional<br/>Updatable | Ignore | |
| video3SecBeaconUrls[0..2] | xsd:string | Viewing beacon URL (3 seconds)<br/>∗SET:Replace all urls.<br/>∗Available url only for &#34;https&#34;. | yes | Optional | Optional<br/>Updatable | Ignore | |
| isRemoveVideo3SecBeaconUrls | enum [isRemoveFlg](./isRemoveFlg.md) | Remove Viewing beacon URL (3 seconds)<br/>∗Even if &#34;video3SecBeaconUrl&#34; is set, given priority to setting of &#34;isRemoveVideo3SecBeaconUrls&#34;. | yes | Ignore | Optional<br/>Updatable | Ignore | |
| videoPaidBeaconUrls[0..2] | xsd:string | Viewing Beacon URL (paid)<br/>∗SET:Replace all urls.<br/>∗Available url only for &#34;https&#34;. | yes | Optional | Optional<br/>Updatable | Ignore | |
| isRemoveVideoPaidBeaconUrls | enum [isRemoveFlg](./isRemoveFlg.md) | Remove Viewing Beacon URL (paid)<br/>∗Even if &#34;videoPaidBeaconUrl&#34; is set, given priority to setting of &#34;isRemoveVideoPaidBeaconUrls&#34;. | yes | Ignore | Optional<br/>Updatable | Ignore | |
| videoCompleteBeaconUrls[0..2] | xsd:string | Viewing beacon URL (complete)<br/>∗SET:Overwrite all urls.<br/>∗Available url only for &#34;https&#34;. | yes | Optional | Optional<br/>Updatable | Ignore | |
| isRemoveVideoCompleteBeaconUrls | enum [isRemoveFlg](./isRemoveFlg.md) | Remove Viewing beacon URL (complete)<br/>∗Even if &#34;videoCompleteBeaconUrl&#34; is set, given priority to setting of &#34;isRemoveVideoCompleteBeaconUrls&#34;. | yes | Ignore | Optional<br/>Updatable | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

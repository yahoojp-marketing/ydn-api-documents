

# StaticFrameAd

The StaticFrameAd object describes the Static Frame Ad information.

### Service

+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace

[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

### Inheritance

+ [Ad](./Ad.md)

| Field | Type | Description | response | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| size | xsd:string | Ad Size | yes | Requirement | Requirement<br/>NotUpdatable | Ignore | |
| headline | xsd:string | Title | yes | Requirement(size=300X250) | Optional(size=300X250) | Ignore | |
| description | xsd:string | Description | yes | Requirement(size=300X250) | Optional(size=300X250) | Ignore | |
| url | xsd:string | Destination URL | yes | Requirement(size=300X250) | Optional(size=300X250) | Ignore | |
| displayUrl | xsd:string | Display URL | yes | Optional(size=300X250)<br><br>  ∗Default value<br>  -Standard campaign:<br>  required<br>  -Mobile app campaign (iOS) :<br>  "itunes.apple.com"<br>  -Mobile app campaign (Android) :<br>  "play.google.com"<br> | Optional(size=300X250)<br><br>  ∗Input allowed<br>  -Mobile app campaign (iOS) :<br>  "itunes.apple.com"<br>  -Mobile app campaign (Android) :<br>  "play.google.com"<br> | Ignore | |
| layout | xsd:string | Ad Layout | yes | Requirement(size=300X250) | Requirement(size=300X250)<br/>NotUpdatable | Ignore | |
| buttonText | enum [ButtonText](./ButtonText.md) | The text of the button to display in the ads<br/>∗Default value:FOR_MORE_INFO | yes | Optional(size=300X250) | Optional(size=300X250) | Ignore | |
| principal | xsd:string | Advertiser Indication | yes | Requirement(size=300X250) | Optional(size=300X250) | Ignore | |
| logoMediaId | xsd:long | Media ID of logo image | yes | Optional(size=300X250) | Optional(size=300X250) | Ignore | |
| colorSetId | xsd:long | Color set ID | yes | Optional(size=300X250) | Optional(size=300X250) | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

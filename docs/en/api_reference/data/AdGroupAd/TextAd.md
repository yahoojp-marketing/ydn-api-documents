

# TextAd

TextAd object describes the Text Ad information.

### Service

+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace

[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

### Inheritance

+ [Ad](./Ad.md)

| Field | Type | Description | response | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| url | xsd:string | Destination URL | yes | Requirement | Optional<br/>Updatable | Ignore | |
| displayUrl | xsd:string | Display URL | yes | Optional<br><br>  ∗Default value<br>  -Standard campaign:<br>  required<br>  -Mobile app campaign (iOS) :<br>  "itunes.apple.com"<br>  -Mobile app campaign (Android) :<br>  "play.google.com"<br> | Optional<br/>Updatable<br><br>  ∗Input allowed<br>  -Mobile app campaign (iOS) :<br>  "itunes.apple.com"<br>  -Mobile app campaign (Android) :<br>  "play.google.com"<br> | Ignore | |
| headline | xsd:string | Title | yes | Requirement | Optional<br/>Updatable | Ignore | |
| description | xsd:string | Description text (line 1) | yes | Requirement | Optional<br/>Updatable | Ignore | |
| description2 | xsd:string | Description text (line 2) | yes | Optional | Optional<br/>Updatable | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

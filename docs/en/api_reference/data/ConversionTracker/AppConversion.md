

# AppConversion

AppConversion object contains the information for AppConversionTracker.

### Service

+ [ConversionTrackerService](../../services/ConversionTrackerService.md)

### Namespace

[ConversionTrackerService#Namespace](../../services/ConversionTrackerService.md#namespace)

### Inheritance

+ [ConversionTracker](./ConversionTracker.md)

| Field | Type | Description | response | add | set |
| ----- | ---- | ----------- | -------- | --------- | --------- |
| appId | xsd:string | App ID of the object to be tracked. | yes | Required | Ignore | |
| appPlatform | enum [AppConversionPlatform](./AppConversionPlatform.md) | App Platform of the object to be tracked. | yes | Required | Ignore | |
| appConversionType | enum [AppConversionType](./AppConversionType.md) | Type of conversion tracking for app | yes | Optional<br>*Default : FIRST_OPEN | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

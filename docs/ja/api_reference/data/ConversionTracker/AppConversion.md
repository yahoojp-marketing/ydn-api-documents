

# AppConversion

AppConversionオブジェクトは、アプリコンバージョントラッカーの情報を保持します。

### Service

+ [ConversionTrackerService](../../services/ConversionTrackerService.md)

### Namespace

[ConversionTrackerService#Namespace](../../services/ConversionTrackerService.md#namespace)

### Inheritance

+ [ConversionTracker](./ConversionTracker.md)

| Field | Type | Description | response | add | set |
| ----- | ---- | ----------- | -------- | --------- | --------- |
| appId | xsd:string | 計測対象のアプリIDです。 | yes | Required | Ignore | |
| appPlatform | enum [AppConversionPlatform](./AppConversionPlatform.md) | 計測対象アプリのプラットフォームです。 | yes | Required | Ignore | |
| appConversionType | enum [AppConversionType](./AppConversionType.md) | アプリコンバージョンの計測タイプです。 | yes | Optional<br>*Default : FIRST_OPEN | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

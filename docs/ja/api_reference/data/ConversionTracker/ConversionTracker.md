

# ConversionTracker

ConversionTrackerオブジェクトは、コンバージョン測定タグやタグごとのパフォーマンスデータなどのコンバージョントラッカー情報を表します。

### Service

+ [ConversionTrackerService](../../services/ConversionTrackerService.md)

### Namespace

[ConversionTrackerService#Namespace](../../services/ConversionTrackerService.md#namespace)

| Field | Type | Description | response | add | set |
| ----- | ---- | ----------- | -------- | --------- | --------- |
| accountId | xsd:long | アカウントIDです。 | yes | Ignore | Ignore | |
| conversionTrackerId | xsd:long | コンバージョントラッカーIDです。 | yes | Ignore | Required | |
| conversionTrackerName | xsd:string | コンバージョントラッカー名です。 | yes | Required | Optional<br>Updatable | |
| status | enum [ConversionTrackerStatus](./ConversionTrackerStatus.md) | コンバージョントラッカーのステータスです。 | yes | Required | Optional<br>Updatable | |
| category | enum [ConversionTrackerCategory](./ConversionTrackerCategory.md) | トラッキングするコンバージョンのカテゴリーです。 | yes | Required | Optional<br>Updatable | |
| userRevenueValue | xsd:long | コンバージョンの収益値です。 | yes | Optional<br>*Default : 0 | Optional<br>Updatable | |
| conversionTrackerType | enum [ConversionTrackerType](./ConversionTrackerType.md) | コンバージョン種別です。 | yes | Required | Required | |
| countingType | enum [ConversionCountingType](./ConversionCountingType.md) | コンバージョンの計測方法です。 | yes | Optional | Optional | |
| measurementPeriod | xsd:int | 計測期間（単位：日）です。<br>※7～90の範囲内で指定可能 | yes | Optional<br>*Default : 30 | Optional | |
| measurementPeriodView | xsd:int | 測定期間（動画視聴）<br>※1-30の範囲で指定可能 | yes | Optional<br>*Default : 1 | Optional | |
| excludeFromBidding | enum [ExcludeFromBidding](./ExcludeFromBidding.md) | 自動入札設定で使用するかを表します。<br>※「コンバージョン列に含める/含めない」の設定です。 | yes | Opitonal<br>*Default : FALSE（使用する） | Optional | |
| conversions | xsd:long | コンバージョン数 | yes | Ignore | Ignore | |
| conversionValue | xsd:string | コンバージョンの価値/コンバージョン数 | yes | Ignore | Ignore | |
| conversionsViaAdClick | xsd:long | コンバージョン数（クリック経由） | yes | Ignore | Ignore | |
| conversionValueViaAdClick | xsd:string | コンバージョンの価値（クリック経由） | yes | Ignore | Ignore | |
| allConversions | xsd:long | コンバージョン数（全て） | yes | Ignore | Ignore | |
| allConversionValue | xsd:string | コンバージョンの価値（全て） | yes | - | - | |
| crossDeviceConversions | xsd:long | クロスデバイスコンバージョン数 | yes | Ignore | Ignore | |
| mostRecentConversionDate | xsd:string | コンバージョンが発生した直近の日付です。<br>（YYYYMMDD） | yes | Ignore | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

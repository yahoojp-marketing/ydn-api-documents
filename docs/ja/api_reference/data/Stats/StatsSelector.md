

# StatsSelector

StatsSelectorオブジェクトは、getメソッドの検索条件（実行パラメータ）を保持します。

### Service

+ [StatsService](../../services/StatsService.md)

### Namespace

[StatsService#Namespace](../../services/StatsService.md#namespace)

| Field | Type | Description | response | get |
| ----- | ---- | ----------- | -------- | --------- |
| accountId | xsd:long | アカウントID | yes | Requirement | |
| campaignIds[0...500] | xsd:long | キャンペーンID<br/>statsTypeで「CAMPAIGN」または「ADGROUP」または「AD」または「TARGET」を指定した場合のみ有効です。 | yes | Optional | |
| adGroupIds[0..500] | xsd:long | 広告グループID<br/>statsTypeで「ADGROUP」または「AD」または「TARGET」を指定した場合のみ有効です。 | yes | Optional | |
| adIds[0..500] | xsd:long | 広告ID<br/>statsTypeで「AD」を指定した場合のみ有効です。 | yes | Optional | |
| mediaIds[0..500] | xsd:long | 画像ID<br/>statsTypeで「MEDIA」を指定した場合のみ有効です。 | yes | Optional | |
| targetTypes[0..1] | enum [TargetType](./TargetType.md) | ターゲットタイプ<br/>statsTypeで「TARGET」を指定した場合のみ必須です。 | yes | Optional | |
| statsPeriod | enum [StatsPeriod](./StatsPeriod.md) | 統計情報の集計期間<br/>デフォルトでは「REALTIME_MONTH」に設定されています。 | yes | Optional | |
| statsPeriodCustomDate | [StatsPeriodCustomDate](./StatsPeriodCustomDate.md) | 統計情報の集計期間<br/>年月日で指定可能です。<br/>StatsPeriodが「CUSTOM_DATE」の時は入力が必須です。 | yes | Optional | |
| statsType | enum [StatsType](./StatsType.md) | 統計情報の種別<br/>デフォルトでは「CAMPAIGN」に設定されています。 | yes | Optional | |
| paging | [Paging](../Common/Paging.md) | ページ設定情報 | yes | Optional | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

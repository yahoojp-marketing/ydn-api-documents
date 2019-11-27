

# AdScheduleTarget

AdScheduleTargetオブジェクトは、時間帯ターゲティングの設定情報を保持します。

### Service

+ [AdGroupTargetService](../../services/AdGroupTargetService.md)

### Namespace

[AdGroupTargetService#Namespace](../../services/AdGroupTargetService.md#namespace)

### Inheritance

+ [Target](./Target.md)

| Field | Type | Description | response | add | set | remove | replace |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| dayOfWeek | enum [DayOfWeek](./DayOfWeek.md) | 曜日です。 | yes | Requirement | Ignore | Ignore | Optional | |
| startHour | xsd:int | 開始時間（時のみ）です。 | yes | Requirement | Ignore | Ignore | Optional | |
| endHour | xsd:int | 終了時間（時のみ）です。 | yes | Requirement | Ignore | Ignore | Optional | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

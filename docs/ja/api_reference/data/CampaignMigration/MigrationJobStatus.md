

# MigrationJobStatus (enum)

MigrationStatusはマイグレーションジョブの状態を示します。

#### Service

+ [CampaignMigrationService](../../services/CampaignMigrationService.md)

#### Namespace

[CampaignMigrationService#Namespace](../../services/CampaignMigrationService.md#namespace)

| Enumeration  |       Type       |          Description          |
| ------------ | ---------------- | ----------------------------- |
| NOT_STARTED | xsd:string | 未処理 |
| IN_PROGRESS | xsd:string | 処理中 |
| COMPLETED | xsd:string | 正常終了 |
| FILE_FORMAT_ERROR | xsd:string | ファイルフォーマットエラー |
| INVALID_CSV_VALUE_ERROR | xsd:string | 異常なCSVの値 |
| UNKNOWN_CSV_FIELD_ERROR | xsd:string | 未知のCSVフィールドエラー |
| SYSTEM_ERROR | xsd:string | システムエラー |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

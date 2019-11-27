

# MigrationJob

MigrationJobオブジェクトは、マイグレーションジョブの処理状況を示すオブジェクトです。

### Service

+ [CampaignMigrationService](../../services/CampaignMigrationService.md)

### Namespace

[CampaignMigrationService#Namespace](../../services/CampaignMigrationService.md#namespace)

| Field | Type | Description | response |
| ----- | ---- | ----------- | -------- |
| migrationJobId | xsd:long | マイグレーションジョブID | yes | |
| accountId | xsd:long | アカウントID | yes | |
| migrationScope | enum [MigrationScope](./MigrationScope.md) | マイグレーションスコープ | yes | |
| migrationJobStatus | enum [MigrationJobStatus](./MigrationJobStatus.md) | マイグレーションジョブステータス | yes | |
| migrationJobSubmitDate | xsd:string | マイグレーションジョブ登録日時 | yes | |
| migrationJobEndDate | xsd:string | マイグレーションジョブ終了日時 | yes | |
| totalCount | xsd:long | 全キャンペーン数 | yes | |
| inProgressCount | xsd:long | 進行中キャンペーン数 | yes | |
| succeededCount | xsd:long | 正常終了キャンペーン数 | yes | |
| failedCount | xsd:long | 失敗キャンペーン数 | yes | |
| downloadOriginalFileUrl | xsd:string | アップロードしたオリジナルcsvファイルのDownloadURL | yes | |
| downloadErrorFileUrl | xsd:string | エラーが発生したキャンペーン一覧のcsvファイルのDownloadURL | yes | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

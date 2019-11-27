

# MigrationJob

MigrationJob object indicates processing status of migration job.

### Service

+ [CampaignMigrationService](../../services/CampaignMigrationService.md)

### Namespace

[CampaignMigrationService#Namespace](../../services/CampaignMigrationService.md#namespace)

| Field | Type | Description | response |
| ----- | ---- | ----------- | -------- |
| migrationJobId | xsd:long | Migration job ID | yes | |
| accountId | xsd:long | Account ID | yes | |
| migrationScope | enum [MigrationScope](./MigrationScope.md) | Migration scope | yes | |
| migrationJobStatus | enum [MigrationJobStatus](./MigrationJobStatus.md) | Migration job status | yes | |
| migrationJobSubmitDate | xsd:string | Migration job submit date | yes | |
| migrationJobEndDate | xsd:string | Migration job end date | yes | |
| totalCount | xsd:long | Number of total campaigns | yes | |
| inProgressCount | xsd:long | Number of progressing campaigns | yes | |
| succeededCount | xsd:long | Number of completed campaigns | yes | |
| failedCount | xsd:long | Number of failed campaigns | yes | |
| downloadOriginalFileUrl | xsd:string | Download URL of the uploaded original csv file | yes | |
| downloadErrorFileUrl | xsd:string | Download URL of the campaign list with error | yes | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

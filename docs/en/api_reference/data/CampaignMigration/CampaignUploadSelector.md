

# CampaignUploadSelector

CampaignUploadSelector object defines conditions to get campaign's bulk upload URL.

### Service

+ [CampaignMigrationService](../../services/CampaignMigrationService.md)

### Namespace

[CampaignMigrationService#Namespace](../../services/CampaignMigrationService.md#namespace)

| Field | Type | Description | response | getCampaignDownloadUrl |
| ----- | ---- | ----------- | -------- | --------- |
| accountId | xsd:long | Account ID | yes | Optional<br>If not specified, URL that can upload the campaign associated with multiple account ID can be obtained.<br>In the migration campaigns under the single account, migration jobs can be filtered  by specified account ID.<br>* On-Behalf-Of authentication: Specifying account ID is required. | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

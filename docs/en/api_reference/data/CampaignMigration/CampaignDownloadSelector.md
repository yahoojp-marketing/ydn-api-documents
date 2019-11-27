

# CampaignDownloadSelector

CampaignDownloadSelector object defines the target of a campaign's bulk download.<br>* The character code is UTF-8 only.

### Service

+ [CampaignMigrationService](../../services/CampaignMigrationService.md)

### Namespace

[CampaignMigrationService#Namespace](../../services/CampaignMigrationService.md#namespace)

| Field | Type | Description | response | getCampaignDownloadUrl |
| ----- | ---- | ----------- | -------- | --------- |
| accountId | xsd:long | Account ID | yes | Optional<br>If not specified, the campaign associated with all account IDs will be downloaded.<br>* Proxy authentication: Specifying account ID is required. | |
| lang | enum [MigrationLang](./MigrationLang.md) | Language. | yes | Optional<br>Default:JA | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

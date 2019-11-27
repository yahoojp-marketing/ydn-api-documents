

# MigrationStatusSelector

MigrationStatusSelectorオブジェクトは、getMigrationStatusメソッドの検索条件（実行パラメータ）を保持します。

### Service

+ [CampaignMigrationService](../../services/CampaignMigrationService.md)

### Namespace

[CampaignMigrationService#Namespace](../../services/CampaignMigrationService.md#namespace)

| Field | Type | Description | response | getMigrationStatus |
| ----- | ---- | ----------- | -------- | --------- |
| migrationJobIds[0..500] | xsd:long | マイグレーションジョブIDです。 | yes | Requirement | |
| accountId | xsd:long | アカウントID | yes | Optional<br>※代行認証の場合は指定必須です。 | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

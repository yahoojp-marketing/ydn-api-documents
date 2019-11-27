

# CampaignDownloadSelector

CampaignDownloadSelectorオブジェクトは、キャンペーンの一括ダウンロードの対象を定義します。<br>※文字コードはUTF-8固定

### Service

+ [CampaignMigrationService](../../services/CampaignMigrationService.md)

### Namespace

[CampaignMigrationService#Namespace](../../services/CampaignMigrationService.md#namespace)

| Field | Type | Description | response | getCampaignDownloadUrl |
| ----- | ---- | ----------- | -------- | --------- |
| accountId | xsd:long | アカウントID | yes | Optional<br>指定しない場合は全アカウントIDに紐づくキャンペーンがダウンロードされます。<br>※代行認証の場合は、アカウントIDの指定が必須です。 | |
| lang | enum [MigrationLang](./MigrationLang.md) | 言語 | yes | Optional<br>Default:JA | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

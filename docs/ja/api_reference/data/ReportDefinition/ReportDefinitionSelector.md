# ReportDefinitionSelector
ReportDefinitionSelectorオブジェクトは、操作の対象とするレポートを表します。
### Service
+ [ReportDefinitionService](../../services/ReportDefinitionService.md)

### Namespace
[ReportDefinitionService#Namespace](../../services/ReportDefinitionService.md#namespace)

| フィールド | データ型 | 説明 | 制限 |
|---|---|---|---|
| accountId| xsd: long| アカウントIDです。| Req |
| reportJobIds[]| xsd: long| レポートIDです。| Opt |
| reportJobStatuses[]| xsd: [ReportJobStatus](./ReportJobStatus.md)| レポートジョブのステータスです。| Opt |
| paging| <a href="../Common/Paging.md">Paging</a>| レスポンスとして戻されるページです。| Opt |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

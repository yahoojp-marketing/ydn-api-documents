

# ReportDefinition

ReportDefinitionオブジェクトは、レポート定義を表します。<br>
TC-CI-00000073は「その他」の地域コードです。DictionaryServiceのgetGeographicLocationでは取得できず、地域ターゲティグでは指定できません。

### Service

+ [ReportDefinitionService](../../services/ReportDefinitionService.md)

### Namespace

[ReportDefinitionService#Namespace](../../services/ReportDefinitionService.md#namespace)

| Field | Type | Description | response | get | add | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| accountId | xsd:long | アカウントIDです。 | yes | - | Ignore | Ignore | |
| reportJobId | xsd:long | レポートジョブIDです。 | yes | - | Ignore | Requirement<br>NonUpdatable | |
| reportJobStatus | enum [ReportJobStatus](./ReportJobStatus.md) | ジョブステータスです。 | yes | - | Ignore | Ignore | |
| reportJobErrorDetail | xsd:string | ジョブエラー詳細です。 | yes | - | Ignore | Ignore | |
| requestTime | xsd:string | ジョブ依頼日時です。 | yes | - | Ignore | Ignore | |
| completeTime | xsd:string | ジョブ完了日時です。 | yes | <br>※ジョブ登録の完了後に返却されます。 | Ignore | Ignore | |
| reportDownloadUrl | xsd:string | レポートダウンロードURLです。 | yes | - | Ignore | Ignore | |
| reportName | xsd:string | レポート名です。 | yes | - | Optional | Ignore | |
| dateRangeType | enum [ReportDateRangeType](./ReportDateRangeType.md) | 集計期間種別です。 | yes | - | Requirement | Ignore | |
| dateRange | [ReportDateRange](./ReportDateRange.md) | 集計期間です。 | yes | - | Optional | Ignore | |
| frequencyRange | enum [ReportFrequencyRange](./ReportFrequencyRange.md) | フリークエンシーの集計期間です。 | yes | - | Optional | Ignore | |
| filters[0..6] | [ReportFilter](./ReportFilter.md) | レポートのフィルターです。 | yes | - | Optional | Ignore | |
| sortFields[] | xsd:string | ソートです。ソートしたいフィールドを選択してください。<br>・最大で5つまで指定可能です。<br>・指定フィールドの前に&#34;+&#34;を追加すると昇順、&#34;-&#34;を追加すると降順で表示されます。 | yes | - | Optional | Ignore | |
| fields[] | xsd:string | 表示項目です。<br>入力可能な値は、[レポートフィールドページ](../../appendix/reports.md)でご確認ください。 | yes | - | Requirement | Ignore | |
| format | enum [ReportDownloadFormat](./ReportDownloadFormat.md) | ファイル出力形式です。 | yes | - | Optional | Ignore | |
| encode | enum [ReportDownloadEncode](./ReportDownloadEncode.md) | 出力文字コードです。 | yes | - | Optional | Ignore | |
| compress | enum [ReportZip](./ReportZip.md) | zip化の有無です。 | yes | - | Optional | Ignore | |
| language | enum [ReportLang](./ReportLang.md) | 出力言語です。 | yes | - | Optional | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

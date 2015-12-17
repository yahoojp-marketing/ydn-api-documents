# ReportRecord
ReportRecordオブジェクトは、レポートの情報を表します。

### Service
+ [ReportService](../services/ReportService.md)

| フィールド | データ型 | maxOccurs | minOccurs | response | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| accountId| long| 1| 0| ○| -| -| -| アカウントIDです。 |
| reportJobId| long| 1| 0| ○ ※remove時のみ 返却されます。| -| -| Req| レポートジョブIDです。 |
| reportId| long| 1| 0| ○| Req| -| -| レポートIDです。 |
| reportName| string| 1| 0| ○| -| -| -| レポート名です。 |
| requestTime| string| 1| 0| ○| -| -| -| ジョブ依頼日時です。 |
| completeTime| string| 1| 0| ○ ※ジョブの登録 完了後に返却されます。| -| -| -| ジョブ完了日時です。 |
| dateRangeType| enum <a href="./ReportDateRangeType.md">ReportDateRangeType</a>| 1| 0| ○| -| -| -| 集計期間タイプです。 |
| dateRange| <a href="./ReportDateRange.md">ReportDateRange</a>| 1| 0| ○| -| -| -| 集計期間です。 |
| status| enum <a href="./ReportJobStatus.md">ReportJobStatus</a>| 1| 0| ○| -| -| -| ジョブステータスです。 |
| jobErrorDetail| string| 1| 0| ○ ※get時のみ返却 されます。| -| -| -| ジョブエラー詳細です。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

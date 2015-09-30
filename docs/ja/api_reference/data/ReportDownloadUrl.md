# ReportDownloadUrl
ReportDownloadUrlオブジェクトは、レポートの情報を含むレポートのダウンロードURLを表します。
### Service
+ [ReportService](../services/ReportService.md)

| フィールド | データ型 | 説明 | ADD | REMOVE | 
|---|---|---|---|---|
| ReportRecord(inherited)|||||
| accountId| xsd: long| アカウントIDです。| ─| ─ |
| reportJobId| xsd: long| ジョブIDです。| ─| Req<br>                            notupdatable |
| reportId| xsd: long| レポートIDです。| Req| ─ |
| reportName| xsd: string| レポート名です。| ─| ─ |
| requestTime| xsd: string| リクエストタイムスタンプです。| ─| ─ |
| completeTime| xsd: string| ジョブの完了日時です。| ─| ─ |
| dateRangeType| <span>enum</span><span> </span><a href="./ReportDateRangeType.md"><span>ReportDateRangeType</span></a>| レポートの対象期間です。| ─| ─ |
| dateRange| <a href="./ReportDateRange.md"><span>ReportDateRange</span></a>| レポートの対象期間です。| ─| ─ |
| status| <span>enum</span><span> </span><a href="./ReportJobStatus.md"><span>ReportJobStatus</span></a>| レポートの処理ステータスです。| ─| ─ |
| ReportDownloadUrl|||||
| downloadUrl| xsd: string| レポートのダウンロードURLです。| ─| ─ |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

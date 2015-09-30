# ReportDefinition
ReportDefinitionオブジェクトは、レポート定義を表します。
### Service
+ [ReportDefinitionService](../services/ReportDefinitionService.md)

| フィールド | データ型 | maxOccurs | minOccurs | response | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| reportId| long| 1| 0| ○| Ignore| -| Requirement<br>(Not updatable)| レポートIDです。 |
| accountId| long| 1| 0| ○| Ignore| -| Ignore| アカウントIDです。 |
| reportName| string| 1| 0| ○| Optional| -| Ignore| レポート名です。 |
| dateRangeType| enum <a href="./ReportDateRangeType.md">ReportDateRangeType</a>| 1| 0| ○| Requirement| -| Ignore| 集計期間種別です。 |
| dateRange| <a href="./ReportDateRange.md">ReportDateRange</a>| 1| 0| ○| Optional| -| Ignore| 集計期間です。 |
| frequencyRange|  enum <a href="./ReportDateRangeType.md">ReportDateRangeType</a>| 1| 0| ○| Optional| -|Ignore|フリークエンシーの計測期間です。 |
| sortFields[]| string| unbounded| 0| ○| Optional| -| Ignore| ソートです。ソートしたいフィールドを選択してください。<br>・最大で5つまで指定可能です。<br>・指定フィールドの前に"+"を追加すると昇順、"-"を追加すると降順で表示されます。 |
| fields[]| string| unbounded| 0| ○| Requirement| -| Ignore| 表示項目です。<br>入力可能な値は、<a href="../appendix/reports.md">レポートフィールドページ</a>よりご確認ください。 |
| format| enum <a href="./ReportDownloadFormat.md">ReportDownloadFormat</a>| 1| 0| ○| Optional| -| Ignore| ファイル出力形式です。 |
| encode| enum <a href="./ReportDownloadEncode.md">ReportDownloadEncode</a>| 1| 0| ○| Optional| -| Ignore| 出力文字コードです。 |
| zip| enum <a href="./ReportZip.md">ReportZip</a>| 1| 0| ○| Optional| -| Ignore| zip化の有無です。 |
| lang| enum <a href="./ReportLang.md">ReportLang</a>| 1| 0| ○| Optional| -| Ignore| 出力言語です。 |
| intervalType| enum <a href="./ReportIntervalType.md">ReportIntervalType</a>| 1| 0| ○| Optional| -| Ignore| 定期レポート作成タイミングです。 |
| specifyDay| int| 1| 0| ○| Optional| -| Ignore| 定期レポート作成日です。 |
| addTemplate| enum <a href="./ReportAddTemplate.md">ReportAddTemplate</a>| 1| 0| ○| Optional| -| Ignore| テンプレートフラグです。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

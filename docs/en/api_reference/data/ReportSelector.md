# ReportSelector
The ReportSelector object serves the operation target report.
### Service
+ [ReportService](../services/ReportService.md)

| Field | Data Type | Description | Restriction | 
|---|---|---|---|
| accountId| xsd: long| The account ID.| Req |
| reportJobIds[]| xsd: long| The report job ID.| Opt |
| reportJobStatuses| enum <a href="../data/ReportJobStatus.md">ReportJobStatus[]</a>| Checks the report job process status.| Opt |
| paging| <a href="../data/Paging.md">Paging</a>| This page comes back as a response.| Opt |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

# ConversionTrackerSelector
ConversionTrackerSelector object specifies ConversionTracker and operation.
### Service
+ [ConversionTrackerService](../services/ConversionTrackerService.md)

| Field | Data Type | Description | ADD | SET | 
|---|---|---|---|---|
| accountId| xsd:long| Account ID| Req| Req |
| conversionTrackerIds[]| xsd:long| Conversion Tracker ID| -| Req |
| statuses[]| enum <a href="./ConversionTrackerStatus.md">ConversionTrackerStatus</a>| Conversion Tracker Status| Req| Opt(Updatable) |
| categories[]| enum <a href="./ConversionTrackerCategory.md">ConversionTrackerCategory</a>| Conversion Category| Req| Opt(Updatable) |
| statsPeriod| enum <a href="./StatsPeriod.md">StatsPeriod</a>| Summarized period of statistics| -| - |
| paging| <a href="./Paging.md">Paging</a>| Page returned as response| -| - |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

# ConversionTracker
ConversionTracker object shows ConversionTracker information such as ConversionTag and performance data by tag.
### Service
+ [ConversionTrackerService](../services/ConversionTrackerService.md)

| Field | Data Type | Description | ADD | SET | 
|---|---|---|---|---|
| accountId| xsd:long| Account ID| Req| Req |
| conversionTrackerId| xsd:long| Conversion Tracker ID| -| Req |
| conversionTrackerName| xsd:string| Conversion Tracker Name| Req| Opt(Updatable) |
| status| enum <a href="./ConversionTrackerStatus.md">ConversionTrackerStatus</a>| Conversion Tracker Status| Req| Opt(Updatable) |
| category| enum <a href="./ConversionTrackerCategory.md">ConversionTrackerCategory</a>| Conversion category for tracking.| Req| Opt(Updatable) |
| numConversionEvents| xsd:int| Number of conversion events.| -| - |
| conversionValue| xsd:long| Total sales by conversion.| -| - |
| mostRecentConversionDate| xsd:string| Most recent date of Conversion| -| - |
| userRevenueValue| xsd:long| Revenue value for Conversions.| Opt(Default: 0)| Opt(Updatable) |
| conversionTrackerType| enum <a href="./ConversionTrackerType.md">ConversionTrackerType</a>| Conversion Type| Req| Req |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

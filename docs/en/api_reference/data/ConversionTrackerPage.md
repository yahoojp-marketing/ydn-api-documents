# ConversionTrackerPage
ConversionTrackerPage object shows entry of ConversionTracker.
### Service
+ [ConversionTrackerService](../services/ConversionTrackerService.md)

| Field | Data Type | Description | ADD | SET | 
|---|---|---|---|---|
| Page(inherited)|||||
| totalNumEntries| xsd:int| Total number of entries |
| Page.Type| xsd:string| Page subtypefor the instance |
| ConversionTrackerPage|||||
| totalNumConversionEvents| xsd:long| Total number of click-through Conversions| -| - |
| totalConversionValue| xsd:long| Total number of Conversions |
| values[]| <a href="./ConversionTrackerValues.md">ConversionTrackerValues</a>| Results of Conversion Tracker values| -| - |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

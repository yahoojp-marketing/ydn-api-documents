# ConversionTrackerValues
ConversionTrackerValuesオブジェクトは、操作結果を含むコンバージョントラッカー情報を表します。
### Service
+ [ConversionTrackerService](../services/ConversionTrackerService.md)

| フィールド | データ型 | 説明 | ADD | SET | 
|---|---|---|---|---|
| ReturnValue(inherited)|||||
| operationSucceeded| xsd:boolean| 処理結果です。| Req| Req |
| error[]| <a href="./Error.md">Error</a>| エラーの内容です。| Opt| Opt |
| ConversionTrackerValues|||||
| conversionTracker| <a href="./ConversionTracker.md">ConversionTracker</a>| コンバージョントラッカー1件あたりの結果情報です。| —| — |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

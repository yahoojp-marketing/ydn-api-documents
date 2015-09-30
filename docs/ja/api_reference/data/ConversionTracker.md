# ConversionTracker
ConversionTrackerオブジェクトは、コンバージョン測定タグやタグごとのパフォーマンスデータなどのコンバージョントラッカー情報を表します。
### Service
+ [ConversionTrackerService](../services/ConversionTrackerService.md)

| フィールド | データ型 | 説明 | ADD | SET | 
|---|---|---|---|---|
| accountId| xsd:long| アカウントIDです。| Req| Req |
| conversionTrackerId| xsd:long| コンバージョントラッカーのIDです。| ─| Req |
| conversionTrackerName| xsd:string| コンバージョントラッカーの名称です。| Req| Opt(Updatable) |
| status| enum <a href="./ConversionTrackerStatus.md">ConversionTrackerStatus</a>| コンバージョントラッカーのステータスです。| Req| Opt(Updatable) |
| category| enum <a href="./ConversionTrackerCategory.md">ConversionTrackerCategory</a>| トラッキング対象のコンバージョンのカテゴリです。| Req| Opt(Updatable) |
| numConversionEvents| xsd:int| コンバージョンのイベント回数です。| ─| ─ |
| conversionValue| xsd:long| コンバージョンの値です。| ─| ─ |
| mostRecentConversionDate| xsd:string| コンバージョンされた直近日です。| ─| ─ |
| userRevenueValue| xsd:long| このコンバージョンの収益値です。| Opt(Default: 0)| Opt(Updatable) |
| conversionTrackerType| enum <a href="./ConversionTrackerType.md">ConversionTrackerType</a>| コンバージョンタイプです。| Req| Req |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

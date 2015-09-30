# ConversionTrackerSelector
ConversionTrackerSelectorオブジェクトは、操作の対象となるコンバージョントラッカーおよび操作を指定します。
### Service
+ [ConversionTrackerService](../services/ConversionTrackerService.md)

| フィールド | データ型 | 説明 | ADD | SET | 
|---|---|---|---|---|
| accountId| xsd:long| アカウントIDです。| Req| Req |
| conversionTrackerIds[]| xsd:long| コンバージョントラッカーのIDです。| ─| Req |
| statuses[](updatable)| enum <a href="./ConversionTrackerStatus.md">ConversionTrackerStatus</a>| コンバージョントラッカーのステータスです。| Req| Opt(Updatable) |
| categories[]| enum <a href="./ConversionTrackerCategory.md">ConversionTrackerCategory</a>| トラッキング対象のコンバージョンのカテゴリです。| Req| Opt(Updatable) |
| statsPeriod| enum <a href="./StatsPeriod.md">StatsPeriod</a>| 統計情報の集計期間です。| ─| ─ |
| paging| <a href="./Paging.md">Paging</a>| 取得範囲です。| ─| ─ |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

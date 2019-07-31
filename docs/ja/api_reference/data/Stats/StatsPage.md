

# StatsPage

StatsPageオブジェクトは、getメソッドの実行結果（全Entityのリスト）を保持します。

### Service

+ [StatsService](../../services/StatsService.md)

### Namespace

[StatsService#Namespace](../../services/StatsService.md#namespace)

### Inheritance

+ [Page](../Common/Page.md)

| Field | Type | Description | response | get |
| ----- | ---- | ----------- | -------- | --------- |
| period | [Period](./Period.md) | 統計情報更新日 | yes | - | |
| values | [StatsValues](./StatsValues.md)<br>inherited [CampaignStatsValues](./CampaignStatsValues.md)<br>inherited [AdGroupStatsValues](./AdGroupStatsValues.md)<br>inherited [AdStatsValues](./AdStatsValues.md)<br>inherited [ImageStatsValues](./ImageStatsValues.md)<br>inherited [VideoStatsValues](./VideoStatsValues.md)<br>inherited [TargetStatsValues](./TargetStatsValues.md) | getメソッドの実行結果です。 | yes | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

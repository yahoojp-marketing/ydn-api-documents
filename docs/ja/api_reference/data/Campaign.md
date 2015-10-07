# Campaign
Campaignオブジェクトは、キャンペーン情報を表します。
### Service
+ [CampaignService](../services/CampaignService.md)

| フィールド | データ型 | maxOccurs | minOccurs | response | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| accountId| long| 1| 1| ○| Req| Req| Req| アカウントIDです。 |
| campaignId| long| 1| 0| ○| -| Req| Req| キャンペーンIDです。 |
| campaignName| string| 1| 0| ○| Req| Opt| -| キャンペーン名です。 |
| userStatus| enum <a href="./UserStatus.md">UserStatus</a>| 1| 0| ○| Req| Opt| -| ユーザーにより広告配信の有無を調整できる設定です。<br>指定しない場合は、フィルタ条件にすべての掲載状況が含まれます。 |
| servingStatus| enum <a href="./CampaignServingStatus.md">CampaignServingStatus</a>| 1| 0| ○| -| -| -| キャンペーンレベルの配信状況です。<br>ユーザーによる広告配信の調整に関わらず、キャンペーンとしての状態を表します。 |
| startDate| string| 1| 0| ○| Opt| Opt| -| 開始日です。 |
| endDate| string| 1| 0| ○| Opt| Opt| -| 終了日です。 |
| budget| <a href="./Budget.md">Budget</a>| 1| 0| ○| Req| Opt| -| キャンペーン予算です。 |
| biddingStrategy| <a href="./BiddingStrategy.md">BiddingStrategy</a>| 1| 0| ○| Req| Opt| -| 入札最適化方法です。 |
| adProductType| string| 1| 0| ○| Req| NotUpdatable| -| 配信方法です。 |
| frequencyCap| <a href="./FrequencyCap.md">FrequencyCap</a>| 1| 0| ○| Opt| Opt| -| フリクエンシー制御です。 |
| conversionOptimize| <a href="./ConversionOptimizer.md">ConversionOptimizer</a>| 1| 0| ○| -| Opt(Updatable)| -| コンバージョン最適化設定です。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

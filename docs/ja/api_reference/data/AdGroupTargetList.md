# AdGroupTargetList
AdGroupTargetListオブジェクトは、特定の広告グループのターゲティング設定を表します。
### Service
+ [AdGroupTargetService](../services/AdGroupTargetService.md)

| フィールド | データ型 | maxOccurs | minOccurs | response | add | set | remove | 説明です。 | 
|---|---|---|---|---|---|---|---|---|
| accountId| long| 1| 1| ○| -| Req| -| アカウントIDです。 |
| campaignId| long| 1| 1| ○| -| Req| -| キャンペーンIDです。 |
| adGroupId| long| 1| 1| ○| -| Req| -| 広告グループIDです。 |
| targets[0..200]| <a href="./TargetList.md">TargetList</a><br><br>			inherited <a href="./AdScheduleTargetList.md">AdScheduleTargetList</a><br><br>			inherited <a href="./GeoTargetList.md">GeoTargetList</a><br><br>			inherited <a href="./AgeTargetList.md">AgeTargetList</a><br><br>			inherited <a href="./GenderTargetList.md">GenderTargetList</a><br><br>			inherited <a href="./InterestCategoryTargetList.md">InterestCategoryTargetList</a><br><br>			inherited <a href="./SiteCategoryTargetList.md">SiteCategoryTargetList</a><br><br>			inherited <a href="./SiteRetargetingTargetList.md">SiteRetargetingTargetList</a><br><br>			inherited <a href="./SearchTargetList.md">SearchTargetList</a><br><br>			inherited <a href="./PlacementTargetList.md">PlacementTargetList</a>| unbounded| 0| ○| -| Req| -| ターゲット設定情報です。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

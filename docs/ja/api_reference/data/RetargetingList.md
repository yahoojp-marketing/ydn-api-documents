# RetargetingList
RetargetingListオブジェクトは、サイトリターゲティング のターゲットリストの情報を表します。
### Service
+ [RetargetingListService](../services/RetargetingListService.md)

| フィールド | データ型 | maxOccurs | minOccurs | response | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| accountId| long| 1| 1| ○| Req| Req| Req| アカウントIDです。 |
| targetListId| long| 1| 0| ○| -| Req| Req| ターゲットリストIDです。 |
| targetListName| string| 1| 0| ○| Req| Opt| -| ターゲットリスト名です。 |
| description| string| 1| 0| ○| Opt| Opt| -| ターゲットリストの説明です。 |
| deliveryStatus| enum <a href="./DeliveryStatus.md">DeliveryStatus</a>| 1| 0| ○| -| -| -| 配信ステータスです。 |
| reach| long| 1| 0| ○| -| -| -| リーチ数です。 |
| targetList| <a href="./TargetList_RetargetingList.md">TargetList</a><br><br>			inherited <a href="./RuleTargetList.md">RuleTargetList</a><br><br>			inherited <a href="./CombinationTargetList.md">CombinationTargetList</a><br><br>			inherited <a href="./SimilarityTargetList.md">SimilarityTargetList</a>| 1| 0| ○| Req| Opt| -| ターゲットリスト設定内容です。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

# RetargetingList
RetargetingList object diplays the target list for site retargeting.
### Service
+ [RetargetingListService](../services/RetargetingListService.md)

| name | type | maxOccurs | minOccurs | response | add | set | remove | description | 
|---|---|---|---|---|---|---|---|---|
| accountId| long| 1| 1| ○| Requirement| Requirement <br>NonUpdatable| Requirement <br>NonUpdatable| Account ID |
| targetListId| long| 1| 0| ○| Ignore| Requirement <br>NonUpdatable| Requirement <br>NonUpdatable| Target List ID |
| targetListName| string| 1| 0| ○| Requirement| Optional<br>Updatable| Ignore| Target List Name |
| description| string| 1| 0| ○| Optional| Optional<br>Updatable| Ignore| Target List Description |
| deliveryStatus| enum <a href="./DeliveryStatus.md">DeliveryStatus</a>| 1| 0| ○| Ignore| Ignore| Ignore| Delivery Status |
| reach| long| 1| 0| ○| Ignore| Ignore| Ignore| Number of Reach |
| targetList| <a href="./TargetList_RetargetingList.md">TargetList</a><br><br> inherited <a href="./RuleTargetList.md">RuleTargetList</a><br><br> inherited <a href="./CombinationTargetList.md">CombinationTargetList</a><br><br> inherited <a href="./SimilarityTargetList.md">SimilarityTargetList</a>| 1| 0| ○| Requirement| Optional<br>Updatable| Ignore| Target List Setting |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

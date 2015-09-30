# RetargetingListSelector
RetargetingListSelectorオブジェクトは、サイトリターゲティングのターゲットリストを指定します。
### Service
+ [RetargetingListService](../services/RetargetingListService.md)

| フィールド | データ型 | maxOccurs | minOccurs | response | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| accountId| long| 1| 1| -| -| -| -| 検索条件：アカウントIDです。 |
| targetListIds[0...100]| long| unbounded| 0| -| -| -| -| 検索条件：ターゲットリストIDです。 |
| targetListTypes[0...4]| enum <a href="./TargetListType.md">TargetListType</a>| unbounded| 0| -| -| -| -| 検索条件：ターゲットリスト種別です。 |
| paging| <a href="./Paging.md">Paging</a>| 1| 0| -| -| -| -| 検索条件：取得範囲です。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

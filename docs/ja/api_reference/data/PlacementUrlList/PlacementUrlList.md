# PlacementUrlList
PlacementUrlListオブジェクトは、プレイスメントUrl情報を保持するオブジェクトです。
### Service
+ [PlacementUrlListService](../../services/PlacementUrlListService.md)

### Namespace
[PlacementUrlListService#Namespace](../../services/PlacementUrlListService.md#namespace)

| フィールド | データ型 | maxOccurs | minOccurs | response | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| accountId| long| 1| 1| ○| Req| Req| Req| アカウントIDです。 |
| urlListId| long| 1| 0| ○| -| Req| Req| urlリストIDです。 |
| urlListName| string| 1| 0| ○| Req| Opt| -| urlリスト名です。 |
| description| string| 1| 0| ○| Opt| Opt| -| urlリストの説明です。 |
| isUnknownDomain| enum <a href="./UnknownDomainFlg.md">UnknownDomainFlg</a>| 1| 0| ○| Opt| Opt| -| 不明ドメインフラグです。<br>						　・デフォルト：FALSE |
| urls[0...1000]| <a href="./UrlList.md">UrlList</a>| unbounded| 0| ○| Req| Optional| -| urlリストです。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

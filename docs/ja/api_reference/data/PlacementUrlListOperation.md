# PlacementUrlListOperation
PlacementUrlListOperationオブジェクトは、mutateメソッドで操作対象のプレイスメントUrl情報を保持するオブジェクトです。
### Service
+ [PlacementUrlListService](../services/PlacementUrlListService.md)

| フィールド | データ型 | maxOccurs | minOccurs | response | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| <a href="./Operation.md">Operation</a>(inherited)|||||||||
| PlacementUrlListOperation|||||||||
| accountId| long| 1| 1| -| Req| Req| Req| アカウントID |
| operand[0...100]| <a href="./PlacementUrlList.md">PlacementUrlList</a>| unbounded| 1| -| Req| Req| Req| プレイスメントURLリスト |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

# PlacementUrlIdea
PlacementUrlIdeaオブジェクトは、プレイスメントUrl情報を保持するオブジェクトです。
### Service
+ [PlacementUrlIdeaService](../../services/PlacementUrlIdeaService.md)

### Namespace
[PlacementUrlIdeaService#Namespace](../../services/PlacementUrlIdeaService.md#namespace)

| フィールド | データ型 | maxOccurs | minOccurs | response | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| operationKey| long| 1| 0| ○| -| -| -| Number(0から始まる連番)です。 |
| operationSucceeded| long| 1| 0| ○| -| -| -| white list から検索できたかどうかの判定（成功：true 固定）です。 |
| keyword| string| 1| 0| ○| -| -| -| 検索キーワードです。 |
| siteCategory| string| 1| 0| ○| -| -| -| 検索カテゴリです。 |
| searchUrl| string| 1| 0| ○| -| -| -| 取得URLです。<br>			不明なURLの場合　UNKNOWN_URLが入ります。 |
| adFormat| enum <a href="./AdFormat.md">AdFormat[]</a>| unbounded| 0| ○| -| -| -| 広告フォーマットです。 |
| desktopReaches| long| 1| 0| ○| -| -| -| PC でのリーチ数です。<br>			　・100未満の時は0 |
| desktopAdRequests| long| 1| 0| ○| -| -| -| PC でのADリクエスト数です。<br>			　・100未満の時は0 |
| smartPhoneReaches| long| 1| 0| ○| -| -| -| SmartPhone でのリーチ数です。<br>			　・100未満の時は0 |
| smartPhoneAdRequests| long| 1| 0| ○| -| -| -| SmartPhone でのADリクエスト数です。<br>			　・100未満の時は0 |
| tabletReaches| long| 1| 0| ○| -| -| -| Tablet でのリーチ数です。<br>			　・100未満の時は0 |
| tabletAdRequests| long| 1| 0| ○| -| -| -| TabletでのADリクエスト数です。<br>			　・100未満の時は0 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

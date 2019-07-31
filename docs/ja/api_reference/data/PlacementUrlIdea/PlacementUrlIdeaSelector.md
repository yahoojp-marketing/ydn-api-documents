# PlacementUrlIdeaSelector
PlacementUrlIdeaSelectorオブジェクトは、getメソッドの検索条件（実行パラメータ）を保持するオブジェクトです。
### Service
+ [PlacementUrlIdeaService](../../services/PlacementUrlIdeaService.md)

### Namespace
[PlacementUrlIdeaService#Namespace](../../services/PlacementUrlIdeaService.md#namespace)

| フィールド | データ型 | maxOccurs | minOccurs | response | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| keyword| string| 1| 0| -| Ignore| Ignore| Ignore| 検索キーワードの配列です。<br>・URLを検索するためのキーワードです。<br>・部分一致です。<br>・スペース区切りでAND検索です。<br>・最大文字数250です。<br>・スペース区切りでの単語数は最大10個です。 |
| siteCategories[1..50]| string[]| unbounded| 0| -| Ignore| Ignore| Ignore| カテゴリの配列です。<br>・URLのカテゴリです。<br>・完全一致です。<br>・複数指定でOR検索です。<br>・TC-SC-xxxxxx で現される規定値です。<br>・DicitonaryService から返ってくるTC-SC-xxxxxxをそのまま指定です。<br>・最大50件です。 |
| adFormats[1..15]| AdFormatConditions[]| unbounded| 0| -| Ignore| Ignore| Ignore| 広告フォーマットの配列です。<br>・広告掲載フォーマットです。<br>・複数指定でOR検索です。<br>・最大配列数15件です。 |
| paging| Paging[]| 1| 0| -| Ignore| Ignore| Ignore| 返却結果の先頭位置と返却結果の数を指定です。<br>・最大500件です。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

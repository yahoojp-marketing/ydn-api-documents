# SelectConditions
SelectConditionsオブジェクトは、プレイスメントターゲティングで使用する、検索キーワドとカテゴリを保持するオブジェクトです。
### Service
+ [PlacementUrlIdeaService](../services/PlacementUrlIdeaService.md)

| フィールド | データ型 | maxOccurs | minOccurs | response | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| keyword| string| 1| 0| -| -| -| -| URLを検索するためのキーワードです。<br>			　・部分一致です。<br>			　・スペース区切りでAND検索になります。<br>			　・最大文字数250です。 |
| siteCategory| string| 1| 0| -| -| -| -| URLのカテゴリです。<br>			　・完全一致です。<br>			　・カテゴリOR検索をする場合は、conditionsを複数指定してください。<br>			　・TC-SC-xxxxxx で現される規定値(xxxxxx部分はcre_SITE_CATEGORY_M_data.tsv の表1列目の値)です。<br>			　・DicitonaryService から返ってくるTC-SC-xxxxxxをそのまま指定します。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

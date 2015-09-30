# SelectConditions
The objects to keep Search Keyword and Category used in Placement Targeting.
### Service
+ [PlacementUrlIdeaService](../services/PlacementUrlIdeaService.md)

| name | type | maxOccurs | minOccurs | response | add | set | remove | description | 
|---|---|---|---|---|---|---|---|---|
| keyword| string| 1| 0| -| -| -| -| ・Keyword for retrieving the URL<br>・Partial Match Search<br>・AND search separated by spaces<br>・Maximum number of characters 250<br>・Required one of the "keywords" or "categories" |
| category| string| 1| 0| -| -| -| -| ・Category of the URL<br>・Exact Match Search<br>・AND search separated by spaces<br>・Specified value to be expressed in TC-SC-xxxxxx<br>・Specify as a TC-SC-xxxxxx coming back from DicitonaryService |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

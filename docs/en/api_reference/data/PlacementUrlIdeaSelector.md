# PlacementUrlIdeaSelector
The objects to keep get method search conditions (execution parameter).
### Service
+ [PlacementUrlIdeaService](../services/PlacementUrlIdeaService.md)

| name | type | maxOccurs | minOccurs | response | add | set | remove | description | 
|---|---|---|---|---|---|---|---|---|
| keyword| string| 1| 0| -| Ignore| Ignore| Ignore| Array of Search keyword.<br>・Keyword to search the URL<br>・Broad match<br>・Search all keywords (AND), separated by spaces<br>・Maximum of 250 characters<br>・Maximum of 10 spaces to separate the words |
| siteCategories[1..50]| string[]| unbounded| 0| -| Ignore| Ignore| Ignore| Array of categories.<br>・Category of URL<br>・Exact match<br>・Search multiple specific keywords (OR)<br>・From value: TC-SC-xxxxxx<br>・Choose the TC-SC-xxxxxx value from DictionaryService<br>・Maximum of 50 cases |
| adFormats[1..15]| <a href="./AdFormatConditions.md">AdFormatConditions</a>[]| unbounded| 0| -| Ignore| Ignore| Ignore| Array of ad formats.<br>・Ad Distribution format<br>・Search multiple specific keywords (OR)<br>・Maximum of 15 arrays |
| paging| <a href="./Paging.md">Paging</a>[]| 1| 0| 1| Ignore| Ignore| Ignore| Paging. |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

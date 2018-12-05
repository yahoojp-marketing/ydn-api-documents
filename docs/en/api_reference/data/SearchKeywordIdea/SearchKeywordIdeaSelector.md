# SearchKeywordIdeaSelector
SearchKeywordIdeaSelector object displays the list of keyword for search targeting.
### Service
+ [SearchKeywordIdeaService](../../services/SearchKeywordIdeaService.md)

### Namespace
[SearchKeywordIdeaService#Namespace](../../services/SearchKeywordIdeaService.md#namespace)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>get</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>keywords[1..200]</td>
  <td>xsd:string</td>
  <td>Search condition : Keyword.<br>*Keyword for suggesting.<br>*Can not specify Keyword and Keyword ID at the same time.</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>keywordIds[1..500]</td>
  <td>xsd:string</td>
  <td>Search condition : Keyword ID.<br>*Keyword for searching.<br>*Can not specify Keyword and Keyword ID at the same time.</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>searchKeywordRecency</td>
  <td><a href="./KeywordRecency.md">KeywordRecency</a></td>
  <td>Search condition : Effective period. <br>*Keywod for searching.<br>*Default value : WITHIN_30DAYS</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>searchKeywordFrequency</td>
  <td><a href="./KeywordFrequency.md">KeywordFrequency</a></td>
  <td>Search condition : Number of searches.<br>*Keyword for searching.<br>*Default value : ONCE_OR_MORE</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>paging</td>
  <td><a href="../Common/Paging.md">Paging</a></td>
  <td>Range of page to be acquired.</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 </tr>
 <td>sortField</td>
  <td>enum <a href="./SortField.md">SortField</a></td>
  <td>Sort field.<br>Default：DESKTOP_SEARCH_VOLUME (Reach number on PC)</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
  <td>sortType</td>
  <td>enum <a href="./SortType.md">SortType</a></td>
  <td>Sort method.<br>Default：DESC (Descending order)</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
  </tr>
  <td>matchType</td>
  <td>enum <a href="./MatchType.md">MatchType</a></td>
  <td>Search condition :<br>
  search method.<br>Default：<br>For keyword : BROAD (Partial Match
)<br>For keywordIds : EXACT (Perfect matching)</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 </table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

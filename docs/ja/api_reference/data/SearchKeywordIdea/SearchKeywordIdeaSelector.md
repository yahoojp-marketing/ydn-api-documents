# SearchKeywordIdeaSelector
SearchKeywordIdeaSelectorオブジェクトは、サーチターゲティング対象キーワードのリストを表します。
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
  <td>検索条件：キーワード<br>※キーワード提案用<br>※キーワード、キーワードIDの同時指定はできません。</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>keywordIds[1..500]</td>
  <td>xsd:string</td>
  <td>検索条件：キーワードID<br>※キーワード検索用<br>※キーワード、キーワードIDの同時指定はできません。</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>searchKeywordRecency</td>
  <td><a href="./KeywordRecency.md">KeywordRecency</a></td>
  <td>検索条件：有効期間<br>※キーワード検索用<br>※デフォルト値：WITHIN_30DAYS</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>searchKeywordFrequency</td>
  <td><a href="./KeywordFrequency.md">KeywordFrequency</a></td>
  <td>検索条件：検索回数<br>※キーワード検索用<br>※デフォルト値：ONCE_OR_MORE</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>paging</td>
  <td><a href="../Common/Paging.md">Paging</a></td>
  <td>ページの取得範囲</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <td>sortField</td>
  <td>enum <a href="./SortField.md">SortField</a></td>
  <td>ソート項目<br>デフォルト：DESKTOP_SEARCH_VOLUME<br>(PC でのリーチ数)</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
  <td>sortType</td>
  <td>enum <a href="./SortType.md">SortType</a></td>
  <td>ソート方法<br>デフォルト：DESC(降順)</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
  </tr>
  <td>matchType</td>
  <td>enum <a href="./MatchType.md">MatchType</a></td>
  <td>検索条件：検索方法<br>デフォルト：<br>keywordsの場合:<br> BROAD(部分一致)<br>keywordIdsの場合: <br>EXACT(完全一致)</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 </table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

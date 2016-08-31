# SearchKeywordIdeaSelector
SearchKeywordIdeaSelectorオブジェクトは、サーチターゲティング対象キーワードのリストを表します。
### Service
+ [SearchKeywordIdeaService](../services/SearchKeywordIdeaService.md)

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
  <td>keywords[1..100]</td>
  <td>xsd:string</td>
  <td>検索条件：キーワードです。<br>※キーワード提案用</td>
  <td>-</td>
  <td>keywords,keywordIds<br>どちらか一方の<br>指定が必須。<br>両方指定は不可。</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>keywordIds[1..500]</td>
  <td>xsd:string</td>
  <td>検索条件：キーワードIDです。<br>※キーワード検索用</td>
  <td>-</td>
  <td>keywords,keywordIds<br>どちらか一方の<br>指定が必須。<br>両方指定は不可。</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>searchKeywordRecency</td>
  <td><a href="./KeywordRecency.md">KeywordRecency</a></td>
  <td>検索条件：有効期間です。<br>※キーワード検索用<br>※デフォルト値：WITHIN_30DAYS</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>searchKeywordFrequency</td>
  <td><a href="./KeywordFrequency.md">KeywordFrequency</a></td>
  <td>検索条件：検索回数です。<br>※キーワード検索用<br>※デフォルト値：ONCE_OR_MORE</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>paging</td>
  <td><a href="./Paging.md">Paging</a></td>
  <td>ページの取得範囲です。</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 </table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

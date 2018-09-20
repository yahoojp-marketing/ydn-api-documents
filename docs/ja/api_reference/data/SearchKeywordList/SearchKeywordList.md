# SearchKeywordList
SearchKeywordListオブジェクトは、サーチキーワードリストを表します。
### Service
+ [SearchKeywordListService](../../services/SearchKeywordListService.md)

### Namespace
[SearchKeywordListService#Namespace](../../services/SearchKeywordListService.md#namespace)

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
  <td>accountId</td>
  <td>xsd:long</td>
  <td>アカウントIDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement<br>NotUpdatable</td>
  <td>Requirement<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>searchKeywordListId</td>
  <td>xsd:long</td>
  <td>サーチキーワードリストIDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement<br>NotUpdatable</td>
  <td>Requirement<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>searchKeywordListName</td>
  <td>xsd:string</td>
  <td>サーチキーワードリスト名です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>searchKeywordListDescription</td>
  <td>xsd:string</td>
  <td>サーチキーワードリストの説明文です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>searchKeywordRecency</td>
  <td>enum <a href="./KeywordRecency.md">KeywordRecency</a></td>
  <td>サーチキーワードリストの有効期間です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>※デフォルト値：WITHIN_30DAYS</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>searchKeywordFrequency</td>
  <td>enum <a href="./KeywordFrequency.md">KeywordFrequency</a></td>
  <td>サーチキーワードリストの検索回数です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>※デフォルト値：ONCE_OR_MORE</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>deliveryStatus</td>
  <td>enum <a href="./DeliveryStatus.md">DeliveryStatus</a></td>
  <td>配信状況です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>searchKeyword[1..500]</td>
  <td><a href="./SearchKeyword.md">SearchKeyword</a></td>
  <td>サーチキーワードリストです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement<br>Updatable</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

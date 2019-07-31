# SearchKeywordList
SearchKeywordList object displays the search list.
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
  <td>Account ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement<br>NotUpdatable</td>
  <td>Requirement<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>searchKeywordListId</td>
  <td>xsd:long</td>
  <td>Search keyword list ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement<br>NotUpdatable</td>
  <td>Requirement<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>searchKeywordListName</td>
  <td>xsd:string</td>
  <td>Name of Search keyword list.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>searchKeywordListDescription</td>
  <td>xsd:string</td>
  <td>Description of Search keyword list.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>searchKeywordRecency</td>
  <td>enum <a href="./KeywordRecency.md">KeywordRecency</a></td>
  <td>Effective period of the search keyword list.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>*Default value : WITHIN_30DAYS</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>searchKeywordFrequency</td>
  <td>enum <a href="./KeywordFrequency.md">KeywordFrequency</a></td>
  <td>Number of searches of the search keyword list.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>*Default value : ONCE_OR_MORE</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>deliveryStatus</td>
  <td>enum <a href="./DeliveryStatus.md">DeliveryStatus</a></td>
  <td>Ad delivery status.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>searchKeyword[1..500]</td>
  <td><a href="./SearchKeyword.md">SearchKeyword</a></td>
  <td>Search keyword list.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement<br>Updatable</td>
  <td>-</td>
 </tr>
</table>

# Target
The Target object is a container for storing targeting settings.

### Service
+ [AdGroupTargetService](../../services/AdGroupTargetService.md)

### Namespace
[AdGroupTargetService#Namespace](../../services/AdGroupTargetService.md#namespace)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
  <th>replace</th>
 </tr>
 <tr>
  <td>type</td>
  <td>enum <a href="./TargetType.md">TargetType</a></td>
  <td>Targeting type</td>
  <td>yes</td>
  <td>Required</td>
  <td>Required</td>
  <td>Required</td>
  <td>Required</td>
 </tr>
 <tr>
  <td>targetId</td>
  <td>xsd:string</td>
  <td>Target ID<br><br>
  &lowast;1<br>
  TargetId indicates the following items in Ver.6.0 and earlier.<br>
  ‐SiteRetargeting: targetListId<br>
  ‐PlacementTarget: placementUrlListId<br>
  ‐SearchTarget: searchKeywordListId<br>
  ‐GeoTarget: IM area code(geo)<br>
  ‐InterestCategory: category code(category)<br>
  ‐SiteCategory: category code(category)<br>
  ‐OsVersionTarget: osVersion<br>
  </td>
  <td>yes</td>
  <td>Optional<br><br>
  &lowast;2<br>
  Required if type is one of the following<br>
  ‐SITE_RETARGETING<br>
  ‐PLACEMENT_TARGET<br>
  ‐SEARCH_TARGET<br>
  ‐GEO_TARGET<br>
  ‐INTEREST_CATEGORY<br>
  ‐SITE_CATEGORY<br>
  </td>
  <td>Required</td>
  <td>Required</td>
  <td>Optional<br><br>
  &lowast;3<br>
  Not required if isRemove is true.<br>
 </tr>
 <tr>
  <td>isRemove</td>
  <td>xsd:boolean</td>
  <td>If true, delete all targeting types.
  <td>‐</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Optional</td>
 </tr>
 </table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

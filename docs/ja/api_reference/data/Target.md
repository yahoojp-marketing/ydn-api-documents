# Target
Targetオブジェクトは、ターゲティング設定情報を保持します。
 
### Service
+ [AdGroupTargetService](../services/AdGroupTargetService.md)
 
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
  <td>ターゲティング種別です。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>targetId</td>
  <td>xsd:string</td>
  <td>ターゲットIDです。<br><br>
  ※1<br>
  targetIdはVer.6.0以前における以下の項目を示します。<br>
  ‐SiteRetargeting：targetListId<br>
  ‐PlacementTarget：placementUrlListId<br>
  ‐SearchTarget：searchKeywordListId<br>
  ‐GeoTarget：IM地域コード(geo)<br>
  ‐InterestCategory: カテゴリーコード(category)<br>
  ‐SiteCategory: カテゴリーコード(category)<br>
  ‐OsVersionTarget:osVersion<br>
  </td>
  <td>yes</td>
  <td>Optional<br><br>
  ※2<br>
  typeが以下のいずれかの場合、設定必須<br>
  ‐SITE_RETARGETING<br>
  ‐PLACEMENT_TARGET<br>
  ‐SEARCH_TARGET<br>
  ‐GEO_TARGET<br>
  ‐INTEREST_CATEGORY<br>
  ‐SITE_CATEGORY<br>
  </td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Optional<br><br>
  ※3<br>
  isRemoveがtrueの場合、設定不要<br>
 </tr>
 <tr>
  <td>isRemove</td>
  <td>xsd:boolean</td>
  <td>trueの場合、ターゲティング種別をすべて削除します。
  <td>‐</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Optional</td>
 </tr>
 </table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

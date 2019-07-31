# ManualCPVAdGroupBid
ManualCPVAdGroupBidオブジェクトは、広告グループの入札価格（CPV）を保持します。<br>
※広告掲載方式がVIDEO_AD(動画広告)のキャンペーンIDを指定した時のみ利用可能です。

### Service
+ [AdGroupService](../../services/AdGroupService.md)

### Namespace
[AdGroupService#Namespace](../../services/AdGroupService.md#namespace)

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
  <td>video</td>
  <td>enum<br><a href="./BiddingStrategyType.md">BiddingStrategyType</a></td>
  <td>入札方法です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Ignore<br>NotUpdatable</td>
  <td>Ignore<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>maxCpv</td>
  <td>xsd:long</td>
  <td>入札価格です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement<br>Updatable</td>
  <td>Ignore<br>NotUpdatable</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">
<img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" />
</a><br />
この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">
クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

# ConversionTrackerPage
ConversionTrackerPageオブジェクトは、getメソッドの実行結果（全Entityのリスト）を保持します。

### Service
+ [ConversionTrackerService](../services/ConversionTrackerService.md)
 
### Inheritance
+ [Page](./Page.md)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
 </tr>
 <tr>
  <td>totalConversions</td>
  <td>xsd:long</td>
  <td>コンバージョン数の合計です。<br>※デバイスをまたいだコンバージョンの値を加味します。</td>
 </tr>
 <tr>
  <td>totalConversionValue</td>
  <td>xsd:string</td>
  <td>コンバージョン値の合計です。<br>※デバイスをまたいだコンバージョンの値を加味します。</td>
 </tr>
 <tr>
  <td>values[0...1000]</td>
  <td><a href="./ConversionTrackerValues.md">ConversionTrackerValues</a></td>
  <td>getメソッドの実行結果です。</td>
 </tr>
</table> 

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

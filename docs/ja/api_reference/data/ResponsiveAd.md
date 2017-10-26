# ResponsiveAd
ResponsiveAdオブジェクトは、レスポンシブ広告の情報を表します。

### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

### Inheritance
+ [Ad](./Ad.md)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>headline</td>
  <td>xsd:string</td>
  <td>タイトルです。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>description</td>
  <td>xsd:string</td>
  <td>説明文です。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
  <tr>
  <td>url</td>
  <td>xsd:string</td>
  <td>リンク先URLです。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
  <tr>
  <td>displayUrl</td>
  <td>xsd:string</td>
  <td>表示URLです。
  </td>
  <td>yes</td>
  <td>Optional<br>
  <br>
  ※Default値<br>
  -標準キャンペーン：<br>入力必須<br>
  -アプリキャンペーン（iOS）：<br>「itunes.apple.com」<br>
  -アプリキャンペーン（Android）：<br>「play.google.com」
  </td>
  <td>Optional<br>
  <br>
  ※入力許可<br>
  -アプリキャンペーン（iOS）：<br>「itunes.apple.com」のみ可能<br>
  -アプリキャンペーン（Android）：<br>「play.google.com」のみ可能
  </td>
  <td>Ignore</td>
 </tr>
  <tr>
  <td>buttonText</td>
  <td>enum <a href="./ButtonText.md">ButtonText</a></td>
  <td>広告に表示するボタンのテキストです。<br>
  ※Default値：FOR_MORE_INFO</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
  <tr>
  <td>principal</td>
  <td>xsd:string</td>
  <td>主体者表記です。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
  <tr>
  <td>logoMediaId</td>
  <td>xsd:long</td>
  <td>ロゴ画像のメディアIDです。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
</table> 

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

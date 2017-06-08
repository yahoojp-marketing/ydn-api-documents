# コンバージョン改修実施後のレポートフィールドについて
YDN APIでは、2017年6月14日（予定）のコンバージョン改修に伴い、一部レポートフィールド（レポート項目）を変更します。  
詳細は以下の表でご確認ください。

<table>
<tbody>
<tr><th rowspan="2" colspan="3">現在</th><th colspan="6">改修後</th></tr><tr><td colspan="3">旧指標</td><td colspan="3">新指標</td></tr>
<tr><td>表示名</td><td>XML属性</td><td>フィールド名（ENUM）</td><td>表示名</td><td>XML属性</td><td>フィールド名（ENUM）</td><td>表示名</td><td>XML属性</td><td>フィールド名（ENUM）</td></tr>
<tr><td>総コンバージョン数</td><td>total<br>Conversions</td><td>CONVERSION</td><td>コンバージョン数（旧）</td><td>total<br>ConversionsOld</td><td>CONVERSION<br>_OLD</td><td>コンバージョン数</td><td>conversions</td><td>CONVERSIONS</td></tr>
<tr><td>総コンバージョン率</td><td>totalConversionRate</td><td>CONVERSION<br>_RATE</td><td>コンバージョン率（旧）</td><td>totalConversion<br>RateOld</td><td>CONVERSION<br>_RATE_OLD</td><td>コンバージョン率</td><td>convRate</td><td>CONV_RATE</td></tr>
<tr><td>コスト/総コンバージョン数</td><td>costTotal<br>Conversions</td><td>CPA</td><td>コスト/コンバージョン数（旧）</td><td>costTotal<br>ConversionsOld</td><td>CPA_OLD</td><td>コスト/コンバージョン数</td><td>costPerConv</td><td>COST_PER_CONV</td></tr>
<tr><td>合計売上金額</td><td>total<br>Revenue</td><td>REVENUE</td><td>合計売上金額（旧）</td><td>totalRevenue<br>Old</td><td>REVENUE_OLD</td><td>合計売上金額</td><td>revenue</td><td>REVENUE</td></tr>
<tr><td>売上/総コンバージョン数</td><td>revenueTotal<br>Conversion</td><td>REVENUE_<br>CONVERSION</td><td>売上/コンバージョン数（旧）</td><td>revenueTotal<br>ConversionOld</td><td>REVENUE_CONVER<br>SION_OLD</td><td>売上/コンバージョン数</td><td>revenue<br>PerConv</td><td>REVENUE_<br>PER_CONV</td></tr>
</tbody>
</table>

改修後の全レポートフィールドは、以下でご確認ください。<br>
希望のレポートタイプをクリックすると、指定可能なレポートフィールドの詳細が表示されます。<br>

* [アカウントレポート、キャンペーンレポート、広告グループレポート、広告レポート、リンク先URLレポート](./AD.csv)
* [インタレストカテゴリーレポート](./INTEREST_CATEGORY.csv)
* [サイトカテゴリーレポート](./SITE_CATEGORY.csv)
* [配信先URLレポート](./URL.csv)
* [フリークエンシーレポート](./FREQUENCY.csv)

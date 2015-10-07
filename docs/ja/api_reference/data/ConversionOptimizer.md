# ConversionOptimizer
ConversionOptimizerオブジェクトは、コンバージョン最適化設定情報を表します。
### Service
+ [ConversionTrackerService](../services/ConversionTrackerService.md)

| フィールド | データ型 | 説明 | ADD | SET | 
|---|---|---|---|---|
| targetCpa| xsd:long| コンバージョン単価の目標値です。<br>※デフォルト：0<br>※設定範囲：0 - 9,999,999,999<br>※「0」の場合：コンバージョン最適化機能は無効<br>※「1」以上の場合：コンバージョン最適化機能は有効<br>※「コンバージョン最適化使用可否」がDISABLE（使用不可）の場合には、目標値を「0」から「1」以上の値に変更することはできません。<br>※コンバージョン最適化機能が動作している場合には、手動で設定されている入札設定は無効になります。| ─| Opt |
| eligibilityFlg| enum <a href="./ConversionOptimizerEligibilityFlg.md">ConversionOptimizerEligibilityFlg</a>| コンバージョン最適化使用可否です。<br>※デフォルト：DISABLE（使用不可）<br>※過去30日間に15件未満のコンバージョン：DISABLE（使用不可）<br>※過去30日間に15件以上のコンバージョン：ENABLE（使用可能）| ─| ─ |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

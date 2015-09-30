# GenderTarget
GenderTargetオブジェクトは、性別ターゲティング設定を表します。
### Service
+ [AdGroupTargetService](../services/AdGroupTargetService.md)

| フィールド | データ型 | maxOccurs | minOccurs | response | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| type| enum <a href="./TargetType.md">TargetType</a>| 1| 1| ○| -| Req| -| ターゲット種別です。 |
| gender| enum <a href="./Gender.md">Gender</a>| 1| 1| ○| -| Req| -| 性別です。 |
| estimateFlg| enum <a href="./EstimateFlg.md">EstimateFlg</a>| 1| 0| ○| -| Opt| -| 推定配信フラグです。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

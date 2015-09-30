# StaticFrameAd
StaticFrameAdオブジェクトは、広告枠サイズ固定広告の情報を表します。
### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

| フィールド | データ型 | maxOccurs | minOccurs | response | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| size| string| 1| 0| ○| Req| Req<br>Not updatable| Ignore| 広告サイズです。 |
| headline| string| 1| 0| ○| Req(size=300X250)| Opt(size=300X250)| Ignore| タイトルです。 |
| description| string| 1| 0| ○| Req(size=300X250)| Opt(size=300X250)| Ignore| 説明文です。 |
| url| string| 1| 0| ○| Req(size=300X250)| Opt(size=300X250)| Ignore| リンク先URLです。 |
| displayUrl| string| 1| 0| ○| Req(size=300X250)| Opt(size=300X250)| Ignore| 表示URLです。 |
| layout| string| 1| 0| ○| Opt(size=300X250)| Req(size=300X250)<br>Not updatable| Ignore| 広告レイアウトです。<br>記載可能な内容は、<a href="./AdLayout.md">AdLayout</a>を参考ください。|
| buttonText| enum <a href="./ButtonText.md">ButtonText</a>| 1| 0| ○| Opt(size=300X250)| Opt(size=300X250)| Ignore| 広告のボタンに表示されるテキストです。 |
| principal| string| 1| 0| ○| Req(size=300X250)| Opt(size=300X250)| Ignore| 広告の主体者表記です。 |
| logoMediaId| long| 1| 0| ○| Opt(size=300X250)| Opt(size=300X250)| Ignore| ロゴの画像IDです。 |
| colorSetId| long| 1| 0| ○| Opt(size=300X250)| Opt(size=300X250)| Ignore| カラーセットIDです。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

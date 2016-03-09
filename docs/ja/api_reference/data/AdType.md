# AdType (enum)
AdTypeは、AdTypeは、広告の配信先デバイスと配信先に応じたタイトル・説明文の文字数を表します。<br>なお、選択した配信先デバイスにより、指定可能な広告の文字数は異なります。

### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

| 値 | 説明 | 
|---|---|
| TEXT_LONG_AD1| 「タイトル15文字、説明文19文字-19文字」のテキスト広告です。PC、スマートフォン・タブレット端末の場合にご利用いただけます。（推奨） |
| TEXT_LONG_AD2| 「タイトル15文字、説明文33文字」のテキスト広告です。<br>PC、スマートフォン・タブレット端末の場合にご利用頂けます。 |
| TEXT_SHORT_AD1| 「タイトル12文字、説明文12文字」のショートテキスト広告です。<br>モバイルの場合にご利用いただけます。（推奨） |
| TEXT_SHORT_AD2| 「タイトル14文字、説明文19文字」のショートテキスト広告です。<br>モバイルの場合にご利用いただけます。 |
| POS_AD| 「説明文33文字」の掲載位置指定テキストです。 |
| RESPONSIVE_AD| 配信される広告表示枠の形に合わせて画像のサイズ変更およびトリミングが行われるレスポンシブ広告です。<br>・タイトル：25文字<br>・説明文：90文字<br>・表示URL：4～50文字<br>・リンクURL：11～1024文字<br>・主体者表記：20文字<br>・ボタン（任意）<br>・ロゴ：180×180（任意） |
| STATIC_FRAME_AD| 配信される広告表示枠の形に合わせて3種類のレイアウトが利用可能な広告枠サイズ固定広告です。<br>※レイアウトの仕様につきましては「AdLayout」を参照して下さい。 |
| NONE| テキストが不要な掲載位置指定の画像広告です。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

# ImageMedia
ImageMediaオブジェクトは、画像を格納するコンテナです。
### Service
+ [MediaService](../services/MediaService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| <a href="./Media.md">Media</a>(inherited)|||
| ImageMedia|||
| mediaFileType| enum <a href="./MediaFileType.md">MediaFileType</a>| 画像のファイルタイプです。 |
| mediaAdFormat| string| 画像の広告サイズの種類です。<br>入力可能な内容は以下のとおりです：<br>・IAB_UAP_LEADER_BOARD（728x90）<br>・IAB_STANDARD_BANNER（320x50）<br>・IAB_UAP_MEDIUM_RECTANGLE（300x250）<br>・BANNER（468x60）<br>・IAB_UAP_WIDE_SKYSCRAPER（160x600）<br>・YJ_SMART_DOUBLE_BANNER（320x100）<br>・SQUARE_57（57x57）<br>・SQUARE_512（512x512）<br>・SQUARE_180（180x180）<br>・SQUARE_300（300x300） |
| fileSize| xsd:long| 画像のファイルサイズです。 |
| width| xsd:long| 画像の横幅です。 |
| height| xsd:long| 画像の縦の長さです。 |
| downloadUrl| xsd:string| 画像参照用URLです。 |
| data| base64Binary| 画像ファイルのbase64エンコードです。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

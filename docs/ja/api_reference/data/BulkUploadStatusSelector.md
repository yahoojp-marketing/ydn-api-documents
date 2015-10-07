# BulkUploadStatusSelector
BulkUploadStatusSelectorオブジェクトは、一括アップロードの処理状況を指定します。
### Service
+ [BulkService](../services/BulkService.md)

| フィールド | データ型 | 説明 | 制限 | 
|---|---|---|---|
| accountId| xsd: long| アカウントIDです。| Req |
| uploadBulkJobIds| xsd: long[]| 一括アップロードのジョブIDです。| Req |
| uploadBulkJobStatus| <span>enum </span><a href="./UploadBulkJobStatus.md"><span>uploadBulkJobStatus</span></a>[]| バルク処理のステータスです。指定がない場合は全てとなります。| Opt |
| lang| <span>enum</span><span>　</span><a href="./BulkLang.md"><span>BulkLang</span></a>| レスポンスに含まれる、エラー出力用バルクシートの言語を指定します。| Opt |
| output| <span>enum</span><span>　</span><a href="./BulkOutput.md"><span>BulkOutput</span></a>| レスポンスに含まれる、エラー出力用バルクシートの出力フォーマットを指定します。| Req |
| encoding| <span>enum</span><span>　</span><a href="./BulkEncoding.md"><span>BulkEncoding</span></a>| レスポンスに含まれる、エラー出力用バルクシートの文字コードを指定します。| Req |
| paging| <a href="./Paging.md"><span>Paging</span></a>| レスポンスとして戻されるページです。| Opt |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

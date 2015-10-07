# BulkDownloadStatusSelector
BulkDownloadStatusSelectorオブジェクトは、バルクダウンロードの状況を表します。
### Service
+ [BulkService](../services/BulkService.md)

| フィールド | データ型 | 説明 | 制限 | 
|---|---|---|---|
| accountId| xsd: long| アカウントIDです。| Req |
| downloadBulkJobIds| xsd: long[]| getBulkDownloadで取得したダウンロードのバルクIDです。200件を超えて指定している場合はエラーとなります。| Req |
| downloadBulkJobStatus| <span>enum</span><span> </span><a href="./DownloadBulkJobStatus.md">DownloadBulkJobStatus</a>[]| バルク処理のステータスです。指定がない場合は全てとなります。| Opt |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

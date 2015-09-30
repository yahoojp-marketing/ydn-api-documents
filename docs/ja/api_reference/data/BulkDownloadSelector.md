# BulkDownloadSelector
BulkDownloadSelectorオブジェクトは、一括ダウンロードする対象を定義します。
### Service
+ [BulkService](../services/BulkService.md)

| フィールド | データ型 | maxOccurs | minOccurs | response | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| accountId| long| 1| 1| -| Req| -| -| アカウントIDです。 |
| campaignIds[0...200]| long| unbounded| 0| -| Opt| -| -| ダウンロード対象のキャンペーンIDです。 |
| adGroupIds[0...200]| long| unbounded| 0| -| Opt| -| -| ダウンロード対象の広告グループIDです。 |
| adIds[0...200]| long| unbounded| 0| -| Opt| -| -| ダウンロード対象の広告IDです。 |
| mediaIds[0...200]| long| unbounded| 0| -| Opt| -| -| ダウンロード対象のメディアIDです。 |
| campaignUserStatuses[0...2]| enum <a href="./UserStatus.md">UserStatus</a>| unbounded| 0| -| Opt| -| -| ダウンロード対象のキャンペーン配信ステータス（ユーザー設定）です。 |
| adGroupUserStatuses[0...2]| enum <a href="./UserStatus.md">UserStatus</a>| unbounded| 0| -| Opt| -| -| ダウンロード対象の広告グループ配信ステータス（ユーザー設定）です。 |
| adGroupAdUserStatuses[0...2]| enum <a href="./UserStatus.md">UserStatus</a>| unbounded| 0| -| Opt| -| -| ダウンロード対象の広告配信ステータス（ユーザー設定）です。 |
| mediaUserStatuses[0...2]| enum <a href="./UserStatus.md">UserStatus</a>| unbounded| 0| -| Opt| -| -| ダウンロード対象のメディア配信ステータス（ユーザー設定）です。 |
| adGroupAdApprovalStatuses[0...5]| enum <a href="./ApprovalStatus.md">ApprovalStatus</a>| unbounded| 0| -| Opt| -| -| ダウンロード対象の広告審査ステータスです。 |
| mediaApprovalStatuses[0...4]| enum <a href="./MediaApprovalStatus.md">MediaApprovalStatus</a>| unbounded| 0| -| Opt| -| -| ダウンロード対象のメディア（画像）審査ステータスです。 |
| entityTypes| enum <a href="./EntityType.md">EntityType</a>| 1| 0| -| Opt| -| -| ダウンロードするエンティティの単位です。 |
| downloadBulkJob| <a href="./DownloadBulkJob.md">DownloadBulkJob</a>| 1| 0| -| Opt| -| -| ダウンロードするバルクジョブの情報です。 |
| downloadType| enum <a href="./BulkDownloadType.md">BulkDownloadType</a>| 1| 0| -| Opt| -| -| ダウンロードするエンティティの項目です。 |
| lang| enum <a href="./BulkLang.md">BulkLang</a>| 1| 0| -| Opt| -| -| ダウンロードする情報の言語設定です。 |
| output| enum <a href="./BulkOutput.md">BulkOutput</a>| 1| 1| -| Req| -| -| ダウンロードする情報の出力形式設定です。 |
| encoding| enum <a href="./BulkEncoding.md">BulkEncoding</a>| 1| 1| -| Req| -| -| ダウンロードする情報の文字エンコード設定です。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

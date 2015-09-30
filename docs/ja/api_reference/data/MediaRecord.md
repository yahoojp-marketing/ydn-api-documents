# MediaRecord
MediaRecordオブジェクトは、画像の情報を表します。
### Service
+ [MediaService](../services/MediaService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| accountId| xsd: long| アカウントIDです。 |
| mediaId| xsd: long| 画像IDです。 |
| mediaName| xsd: string| 実ファイル名です。 |
| mediaTitle| xsd: string| 画像名です。 |
| userStatus| enum <a href="../data/UserStatus.md">UserStatus</a>| 配信の状況です。 |
| logoFlg| enum <a href="../data/LogoFlg.md">LogoFlg</a>| ロゴフラグです。<br>（デフォルト：FALSE） |
| creationTime| xsd: string| 入稿日時です。 |
| approvalStatus| enum <a href="../data/MediaApprovalStatus.md">MediaApprovalStatus</a>| 審査の状況です。 |
| disapprovalReasonCodes| xsd: string| 掲載拒否の理由です。 |
| media| Media<br>inherited <a href="../data/ImageMedia.md">ImageMedia</a>| 画像を含むコンテナです。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

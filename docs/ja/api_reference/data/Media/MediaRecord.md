

# MediaRecord

MediaRecordオブジェクトは、画像の情報を表します。

### Service

+ [MediaService](../../services/MediaService.md)

### Namespace

[MediaService#Namespace](../../services/MediaService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| accountId | xsd:long | アカウントIDです。 | yes | - | Requirement | Requirement<br>NotUpdatable | Requirement<br>NotUpdatable | |
| mediaId | xsd:long | 画像IDです。 | yes | - | - | Requirement<br>NotUpdatable | Requirement<br>NotUpdatable | |
| mediaName | xsd:string | 実ファイル名です。 | yes | - | Requirement | - | - | |
| mediaTitle | xsd:string | 画像名です。 | yes | - | Requirement | Optional<br>Updatable | - | |
| userStatus | enum [UserStatus](./UserStatus.md) | 配信状況です。 | yes | - | Requirement | Optional<br>Updatable | - | |
| logoFlg | enum [LogoFlg](./LogoFlg.md) | ロゴフラグです。（デフォルト：FALSE） | yes | - | Optional | Optional<br>Updatable | - | |
| thumbnailFlg | enum [ThumbnailFlg](./ThumbnailFlg.md) | サムネイルフラグです。（デフォルト：FALSE） | yes | - | Optional | - | - | |
| creationTime | xsd:string | 入稿日時です。 | yes | - | - | - | - | |
| approvalStatus | enum [MediaApprovalStatus](./MediaApprovalStatus.md) | 審査の状況です。 | yes | - | - | - | - | |
| disapprovalReasonCodes | xsd:string | 掲載拒否の理由です。 | yes | - | - | - | - | |
| media | [Media](./Media.md)<br>inherited [ImageMedia](./ImageMedia.md) | 画像の設定内容です。 | yes | - | Requirement | - | - | |
| campaignBannerFlg | enum [CampaignBannerFlg](./CampaignBannerFlg.md) | キャンペーンバナーフラグです。（デフォルト：FALSE） | yes | - | Optional | - | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

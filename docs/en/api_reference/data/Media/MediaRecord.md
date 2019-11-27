

# MediaRecord

The MediaRecord object is a container for the information of media (image data).

### Service

+ [MediaService](../../services/MediaService.md)

### Namespace

[MediaService#Namespace](../../services/MediaService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| accountId | xsd:long | Account ID. | yes | - | Requirement | Requirement<br>NotUpdatable | Requirement<br>NotUpdatable | |
| mediaId | xsd:long | Media ID (image ID). | yes | - | - | Requirement<br>NotUpdatable | Requirement<br>NotUpdatable | |
| mediaName | xsd:string | File name. | yes | - | Requirement | - | - | |
| mediaTitle | xsd:string | Image name. | yes | - | Requirement | Optional<br>Updatable | - | |
| userStatus | enum [UserStatus](./UserStatus.md) | Display status. | yes | - | Requirement | Optional<br>Updatable | - | |
| logoFlg | enum [LogoFlg](./LogoFlg.md) | A flag for logo. (Default = FALSE) | yes | - | Optional | Optional<br>Updatable | - | |
| thumbnailFlg | enum [ThumbnailFlg](./ThumbnailFlg.md) | A flag of thumbnail. (Default = FALSE) | yes | - | Optional | - | - | |
| creationTime | xsd:string | Date and time of creation. | yes | - | - | - | - | |
| approvalStatus | enum [MediaApprovalStatus](./MediaApprovalStatus.md) | Editorial review status. | yes | - | - | - | - | |
| disapprovalReasonCodes | xsd:string | Reason code why it&#39;s disapproved on the review. | yes | - | - | - | - | |
| media | [Media](./Media.md)<br>inherited [ImageMedia](./ImageMedia.md) | Media (image) settings. | yes | - | Requirement | - | - | |
| campaignBannerFlg | enum [CampaignBannerFlg](./CampaignBannerFlg.md) | Flag of campaign banner. (Default = FALSE) | yes | - | Optional | - | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

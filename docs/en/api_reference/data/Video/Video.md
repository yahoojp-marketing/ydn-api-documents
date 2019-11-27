

# Video

Video object is a container for the information of videos.

### Service

+ [VideoService](../../services/VideoService.md)

### Namespace

[VideoService#Namespace](../../services/VideoService.md#namespace)

| Field | Type | Description | response | get | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| accountId | xsd:long | Account ID. | yes | - | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | |
| mediaId | xsd:long | Media ID. | yes | - | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | |
| videoName | xsd:string | Video file name. | yes | - | - | - | |
| videoTitle | xsd:string | Video name. | yes | - | Optional<br/>Updatable | - | |
| userStatus | enum [UserStatus](./UserStatus.md) | Display Status of video. | yes | - | Optional<br/>Updatable | - | |
| creationTime | xsd:string | Time and date when the video was submitted. | yes | - | - | - | |
| approvalStatus | enum [ApprovalStatus](./ApprovalStatus.md) | Approval status of the video on Editorial Review. | yes | - | - | - | |
| disapprovalReasonCodes | xsd:string | Disapproval reason of the video. | yes | - | - | - | |
| processStatus | enum [VideoProcessStatus](./VideoProcessStatus.md) | Process status of the video. | yes | - | - | - | |
| videoSetting | [VideoSetting](./VideoSetting.md) | Setting details of the video. | yes | - | - | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

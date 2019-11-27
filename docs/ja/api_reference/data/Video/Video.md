

# Video

Videoオブジェクトは、動画情報を保持します。

### Service

+ [VideoService](../../services/VideoService.md)

### Namespace

[VideoService#Namespace](../../services/VideoService.md#namespace)

| Field | Type | Description | response | get | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| accountId | xsd:long | アカウントIDです。 | yes | - | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | |
| mediaId | xsd:long | メディアIDです。 | yes | - | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | |
| videoName | xsd:string | 動画のファイル名です。 | yes | - | - | - | |
| videoTitle | xsd:string | 動画名です。 | yes | - | Optional<br/>Updatable | - | |
| userStatus | enum [UserStatus](./UserStatus.md) | 動画の配信状況です。 | yes | - | Optional<br/>Updatable | - | |
| creationTime | xsd:string | 動画の入稿日時です。 | yes | - | - | - | |
| approvalStatus | enum [ApprovalStatus](./ApprovalStatus.md) | 動画の審査状況です。 | yes | - | - | - | |
| disapprovalReasonCodes | xsd:string | 動画の掲載拒否理由です。 | yes | - | - | - | |
| processStatus | enum [VideoProcessStatus](./VideoProcessStatus.md) | 動画の処理状況です。 | yes | - | - | - | |
| videoSetting | [VideoSetting](./VideoSetting.md) | 動画の設定内容です。 | yes | - | - | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

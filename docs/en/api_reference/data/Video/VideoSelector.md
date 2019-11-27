

# VideoSelector

The VideoSelector object is a container for storing added video information and filtering condition.

### Service

+ [VideoService](../../services/VideoService.md)

### Namespace

[VideoService#Namespace](../../services/VideoService.md#namespace)

| Field | Type | Description | response |
| ----- | ---- | ----------- | -------- |
| accountId | xsd:long | Account ID. | yes | |
| mediaIds[0..500] | xsd:long | Media ID. | yes | |
| userStatuses[0..2] | enum [UserStatus](./UserStatus.md) | Display Status of the video. | yes | |
| approvalStatuses[0..4] | enum [ApprovalStatus](./ApprovalStatus.md) | Approval status of the video on Editorial Review. | yes | |
| processStatuses | enum [VideoProcessStatus](./VideoProcessStatus.md) | Process status of the video. | yes | |
| paging | [Paging](../Common/Paging.md) | Paging. | yes | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

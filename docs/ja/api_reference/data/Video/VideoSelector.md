

# VideoSelector

VideoSelectorオブジェクトは、入稿済みの動画の情報を取得します。

### Service

+ [VideoService](../../services/VideoService.md)

### Namespace

[VideoService#Namespace](../../services/VideoService.md#namespace)

| Field | Type | Description | response |
| ----- | ---- | ----------- | -------- |
| accountId | xsd:long | アカウントIDです。 | yes | |
| mediaIds[0..500] | xsd:long | メディアIDです。 | yes | |
| userStatuses[0..2] | enum [UserStatus](./UserStatus.md) | 動画の配信状況です。 | yes | |
| approvalStatuses[0..4] | enum [ApprovalStatus](./ApprovalStatus.md) | 動画の審査状況です。 | yes | |
| processStatuses | enum [VideoProcessStatus](./VideoProcessStatus.md) | 動画の処理状況です。 | yes | |
| paging | [Paging](../Common/Paging.md) | 取得範囲です。 | yes | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>



# MediaSelector

MediaSelectorオブジェクトは、操作の対象とする画像およびフィルタ条件を表します。

### Service

+ [MediaService](../../services/MediaService.md)

### Namespace

[MediaService#Namespace](../../services/MediaService.md#namespace)

| Field | Type | Description | response |
| ----- | ---- | ----------- | -------- |
| accountId | xsd:long | アカウントIDです。 | yes | |
| mediaIds | xsd:long | 画像IDです。 | yes | |
| userStatuses | enum [UserStatus](./UserStatus.md) | 画像の配信の状況です。 | yes | |
| approvalStatuses | enum [MediaApprovalStatus](./MediaApprovalStatus.md) | 画像の審査の状況です。 | yes | |
| paging | [Paging](../Common/Paging.md) | Paging | yes | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

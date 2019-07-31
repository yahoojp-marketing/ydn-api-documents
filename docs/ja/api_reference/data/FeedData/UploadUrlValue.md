

# UploadUrlValue

UploadUrlValueオブジェクトは、getUploadUrl操作の結果を保持する。

### Service

+ [FeedDataService](../../services/FeedDataService.md)

### Namespace

[FeedDataService#Namespace](../../services/FeedDataService.md#namespace)

| Field | Type | Description | response |
| ----- | ---- | ----------- | -------- |
| accountId | xsd:long | アカウントID | yes | |
| itemListUploadType | enum [ItemListUploadType](./ItemListUploadType.md) | 取り込み種別 | yes | |
| feedHolderId | xsd:long | FeedHolderを識別するId | yes | |
| uploadUrl | xsd:string | ファイルアップロードする一時URL | yes | |
| isDebug | xsd:boolean | trueはデバッグモードでの実行を意味します。 | yes | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

# FeedHolderRecord
FeedHolderRecordオブジェクトは、FeedHolder情報を保持します。

### Service
+ [FeedHolderService](../../services/FeedHolderService.md)

### Namespace
[FeedHolderService#Namespace](../../services/FeedHolderService.md#namespace)

| Field | Type | Description | response | add | set | remove
|---|---|---|---|---|---|---|
| accountId| xsd:long| アカウントID | ○ | Requirement |　Requirement | Requirement 
| feedHolderId| xsd:long| FeedHolderを識別するId | ○ | Ignore | Requirement | Requirement
| feedHolderName| xsd:string| FeedHolderを識別する名称 |  ○ | Requirement | Optional | Ignore
| itemCount| xsd:long| アイテム数 | ○ | Ignore | Ignore | Ignore
| approvedItemCount| xsd:long| 審査済みアイテム数 | ○ | Ignore | Ignore | Ignore
| disApprovedItemCount| xsd:long| 審査否認アイテム数 | ○ | Ignore | Ignore | Ignore

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

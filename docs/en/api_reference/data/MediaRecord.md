# MediaRecord
The MediaRecord object is a container for the information of media.
### Service
+ [MediaService](../services/MediaService.md)

| Field | Data Type | Description | 
|---|---|---|
| accountId| xsd: long| The account ID. |
| mediaId| xsd: long| The image ID. |
| mediaName| xsd: string| The name of file. |
| mediaTitle| xsd: string| The name of media. |
| userStatus| enum <a href="../data/UserStatus.md">UserStatus</a>| The display status. |
| logoFlg| enum <a href="../data/LogoFlg.md">LogoFlg</a>| Logo image flag.<br>(Default: FALSE) |
| creationTime| xsd: string| The submitted date. |
| approvalStatus| enum <a href="../data/MediaApprovalStatus.md">MediaApprovalStatus</a>| The approval status. |
| disapprovalReasonCodes| xsd: string| The disapproval reason. |
| media| Media <br>inherited <a href="../data/ImageMedia.md">ImageMedia</a>| The container with media |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

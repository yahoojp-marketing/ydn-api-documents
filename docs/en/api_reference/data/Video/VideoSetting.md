

# VideoSetting

VideoSetting object stores the setting information of videos.

### Service

+ [VideoService](../../services/VideoService.md)

### Namespace

[VideoService#Namespace](../../services/VideoService.md#namespace)

| Field | Type | Description | response | get | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| videoFileType | enum [VideoFileType](./VideoFileType.md) | File type of the video. | yes | - | - | - | |
| videoAdFormat | xsd:string | Ad format type of the video ad. | yes | - | - | - | |
| fileSize | xsd:long | File size of the video. | yes | - | - | - | |
| width | xsd:long | Width of the video. | yes | - | - | - | |
| height | xsd:long | Height (vertical length) of the video. | yes | - | - | - | |
| playbackTime | xsd:long | Play time (sec) of the video. | yes | - | - | - | |
| downloadOriginalUrl | xsd:string | URL for downloading video (original).<br/>※This value is not provided for SET and REMOVE request. | yes | - | - | - | |
| downloadHighBitrateUrl | xsd:string | URL for downloading video (high quality).<br/>※This value is not provided for SET and REMOVE request. | yes | - | - | - | |
| downloadMiddleBitrateUrl | xsd:string | URL for downloading video (middle quality).<br/>※This value is not provided for SET and REMOVE request. | yes | - | - | - | |
| downloadLowBitrateUrl | xsd:string | URL for downloading video (low quality).<br/>※This value is not provided for SET and REMOVE request. | yes | - | - | - | |
| videoAspectRatio | xsd:string | Type of aspect ratio.<br>* Refer to [getMediaAdFormat](../../services/DictionaryService.md#getmediaadformat) for available aspect ratio. | yes | - | - | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>



# ImageMedia

The ImageMedia object is a container for storing image.

### Service

+ [MediaService](../../services/MediaService.md)

### Namespace

[MediaService#Namespace](../../services/MediaService.md#namespace)

### Inheritance

+ [Media](./Media.md)

| Field | Type | Description | response | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| mediaFileType | enum [MediaFileType](./MediaFileType.md) | The file type of image. | yes | Ignore | Ignore | Ignore | |
| mediaAdFormat | xsd:string | The type of image format.<br>*Available format is referable on [getMediaAdFormat](../../services/DictionaryService.md#getmediaadformat). | yes | Ignore | Ignore | Ignore | |
| fileSize | xsd:long | The file size of image. | yes | Ignore | Ignore | Ignore | |
| width | xsd:long | The width of image. | yes | Ignore | Ignore | Ignore | |
| height | xsd:long | The height of image. | yes | Ignore | Ignore | Ignore | |
| downloadUrl | xsd:string | The URL for downloading image. | yes | Ignore | Ignore | Ignore | |
| data | xsd:base64Binary | The image file in base64 encode. | - | Requirement | Ignore | Ignore | |
| aspectRatio | xsd:string | Type of aspect ratio.<br>* Refer to [getMediaAdFormat](../../services/DictionaryService.md#getmediaadformat) for available aspect ratio. | yes | Ignore | Ignore | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

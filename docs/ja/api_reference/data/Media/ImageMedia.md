

# ImageMedia

ImageMediaオブジェクトは、画像を格納するコンテナです。

### Service

+ [MediaService](../../services/MediaService.md)

### Namespace

[MediaService#Namespace](../../services/MediaService.md#namespace)

### Inheritance

+ [Media](./Media.md)

| Field | Type | Description | response | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| mediaFileType | enum [MediaFileType](./MediaFileType.md) | 画像のファイルタイプです。 | yes | Ignore | Ignore | Ignore | |
| mediaAdFormat | xsd:string | 画像フォーマットの種類です。<br>※利用可能なフォーマットは[getMediaAdFormat](../../services/DictionaryService.md#getmediaadformat)よりご確認ください。 | yes | Ignore | Ignore | Ignore | |
| fileSize | xsd:long | ファイルサイズです。 | yes | Ignore | Ignore | Ignore | |
| width | xsd:long | 横幅です。 | yes | Ignore | Ignore | Ignore | |
| height | xsd:long | 縦の長さです。 | yes | Ignore | Ignore | Ignore | |
| downloadUrl | xsd:string | ダウンロードURLです。 | yes | Ignore | Ignore | Ignore | |
| data | xsd:base64Binary | 画像ファイルのbase64エンコードです。 | - | Requirement | Ignore | Ignore | |
| aspectRatio | xsd:string | 画像アスペクト比の種類です。<br>※利用可能なアスペクト比は[getMediaAdFormat](../../services/DictionaryService.md#getmediaadformat)よりご確認ください。 | yes | Ignore | Ignore | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

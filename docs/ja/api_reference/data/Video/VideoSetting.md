

# VideoSetting

VideoSettingオブジェクトは、動画の設定内容を保持します。

### Service

+ [VideoService](../../services/VideoService.md)

### Namespace

[VideoService#Namespace](../../services/VideoService.md#namespace)

| Field | Type | Description | response | get | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| videoFileType | enum [VideoFileType](./VideoFileType.md) | 動画のファイルタイプです。 | yes | - | - | - | |
| videoAdFormat | xsd:string | 動画広告の種類です。 | yes | - | - | - | |
| fileSize | xsd:long | 動画のファイルサイズです。 | yes | - | - | - | |
| width | xsd:long | 動画の横幅です。 | yes | - | - | - | |
| height | xsd:long | 動画の高さ（縦の長さ）です。 | yes | - | - | - | |
| playbackTime | xsd:long | 動画再生時間（秒）です。 | yes | - | - | - | |
| downloadOriginalUrl | xsd:string | 動画のダウンロードURL（オリジナル）です。<br/>※SETとREMOVEの場合は返却されません。 | yes | - | - | - | |
| downloadHighBitrateUrl | xsd:string | 動画のダウンロードURL（高画質）です。<br/>※SETとREMOVEの場合は返却されません。 | yes | - | - | - | |
| downloadMiddleBitrateUrl | xsd:string | 動画のダウンロードURL（中画質）です。<br/>※SETとREMOVEの場合は返却されません。 | yes | - | - | - | |
| downloadLowBitrateUrl | xsd:string | 動画のダウンロードURL（低画質）です。<br/>※SETとREMOVEの場合は返却されません。 | yes | - | - | - | |
| videoAspectRatio | xsd:string | 動画アスペクト比の種類です。<br>※利用可能なアスペクト比は[getMediaAdFormat](../../services/DictionaryService.md#getmediaadformat)よりご確認ください。 | yes | - | - | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

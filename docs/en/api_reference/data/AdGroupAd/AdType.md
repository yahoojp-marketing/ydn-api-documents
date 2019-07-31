

# AdType (enum)

AdType describes the type of ad.
In addition, the number of available characters of ad creatives vary with selected devices.

#### Service

+ [AdGroupAdService](../../services/AdGroupAdService.md)

#### Namespace

[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

| Enumeration  |       Type       |          Description          |
| ------------ | ---------------- | ----------------------------- |
| TEXT_LONG_AD1 | xsd:string | Text ad is &#34;title is 15 characters&#34; and &#34;description is 19 characters / 19 characters&#34;.<br/>It is available for PC, Smartphone and Tablet. (Recommended) |
| TEXT_LONG_AD2 | xsd:string | Text ad is &#34;title is 15 characters&#34; and &#34;description is 33 characters&#34;.<br/>It is available for PC, Smartphone and Tablet. |
| TEXT_SHORT_AD1 | xsd:string | Short text ad is &#34;title is 12 characters&#34; and &#34;description is 12 characters&#34;.<br/>It is available for Mobile.<br/>∗Currently this ad type is not available for ad creation. |
| TEXT_SHORT_AD2 | xsd:string | Short text ad is &#34;title is 14 characters&#34; and &#34;description is 19 characters&#34;.<br/>It is available for Mobile.<br/>∗Currently this ad type is not available for ad creation. |
| POS_AD | xsd:string | Positioning text is &#34;description is 33 characters&#34;. |
| RESPONSIVE_IMAGE_AD | xsd:string | Responsive Ad which flexibly adjusts its image size and trimmed to the size of ad place. |
| STATIC_FRAME_AD | xsd:string | Static frame ad which flexibly adjusts to 3 layout types to the size of ad place.<br/>∗More information about the layout is referable on <a href="/yahoojp-marketing/ydn-api-documents/blob/master/docs/en/api_reference/data/AdGroupAd/AdLayout.md">AdLayout</a>. |
| RESPONSIVE_VIDEO_AD | xsd:string | Video ad which displays a specified video on the ad place. |
| DYNAMIC_AD | xsd:string | Dynamic ad which displays products in various formats, such as image size or product combination according to website and device to be displayed. |
| BANNER_IMAGE_AD | xsd:string | Ad composed of image. |
| BANNER_VIDEO_AD | xsd:string | Ad composed of video. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

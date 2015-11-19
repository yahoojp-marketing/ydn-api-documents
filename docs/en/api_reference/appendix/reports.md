# Report Fields
The table below describes available report fields.

### Report Fields List
Field Name           | Display Name (Japanese)  | Display Name (English) | XML Attribute    | Unit Type | Response List
-------------------- | ------------------------ | ---------------------- | ---------------- | --------- | ------------
ACCOUNT_ID            | アカウントID         | Account ID                         | accountID            | long  | -
ACCOUNT_NAME          | アカウント名          | Account Name                       | accountName          | string | -
CAMPAIGN_ID           | キャンペーンID        | Campaign ID                        | campaignID           | long  | -
CAMPAIGN_NAME         | キャンペーン名         | Campaign Name                      | campaignName         | string | -
ADGROUP_ID            | 広告グループID        | Ad Group ID                   | adgroupID            | long  | -
ADGROUP_NAME          | 広告グループ名         | Ad Group Name                 | adgroupName          | string | -
AD_ID                 | 広告ID            | Ad ID                     | adID                 | long | -  
AD_NAME               | 広告名             | Ad Name                   | adName               | string | -
AD_TYPE               | 広告タイプ           | Ad Type                  | adType               | string | [AD_TYPE Response](#ad_type)
URL_ID     | リンク先URL ID             | Destination URL ID            | destinationURLID         | long | -
URL_NAME       | リンク先URL         | Destination URL          | destinationURL       | stirng | -
PREF_ID         | 都道府県ID          | Prefecture ID                           | prefectureID         | long | -
PREF_NAME       | 都道府県            | Prefecture                             | prefecture           | string | -
CITY_ID               | 市区郡ID           | City ID                                 | cityID               | long | -
CITY_NAME             | 市区郡             | City                                    | city                 | string | -
WARD_ID               | 行政区ID           | Ward ID                                 | wardID               | long | -
WARD_NAME             | 行政区             | Ward                                    | ward                 | string | -
GENDER               | 性別              | Gender                                  | gender               | string | [GENDER Response](#gender)
AGE                  | 年齢              | Age                                     | age                  | int | [AGE Response](#age)
DAY                  | 日               | Daily                                   | day                  | string | -
DELIVER              | 広告掲載方式          | Ad Distribution                    | adDistribution       | string | [DELIVER Response](#deliver)
DEVICE               | デバイス            | Device                              | device               | string | [DEVICE Response](#device)
SITE_CATEGORY         | サイトカテゴリー名       | Site Category                  | siteCategory         | string | -
INTEREST_CATEGORY     | インタレストカテゴリー名    | Interest Category           | interestCategory     | string | -
DELIVER_URL       | 配信先URL         | Ad Delivery URL          | adDeliveryURL       | string | -
AD_STYLE              | 掲載フォーマット（画像タイプ） | Ad Format Media Type | adStyle   | string | [AD_STYLE Response](#ad_style)
MEDIA_ID              | 画像ID            | Media ID                           | mediaID              | long | -  
MEDIA_NAME            | 画像名             | Media Name                        | mediaName            | string | -
MEDIA_FILE_NAME       | ファイル名             | File Name                      | fileName            | string | -
MEDIA_AD_FORMAT      | ピクセルサイズ           | Pixel Size                    | pixelSize           | string   | [MEDIA_AD_FORMAT Response](#media_ad_format)
AD_TITLE                | タイトル            | Title                    | title                | string | -
DESCRIPTION1         | 説明文1            | Description 1            | description1         | string | -
DESCRIPTION2         | 説明文2            | Description 2            | description2         | string | -
DISPLAY_URL           | 表示URL           | Display URL            | displayURL           | string | -
SEARCHKEYWORD_ID      | サーチキーワードID      | Search Keyword ID                       | searchKeywordID      | long  | -
SEARCHKEYWORD        | サーチキーワード        | Search Keyword                          | searchKeyword        | string | -
FREQUENCY       | フリークエンシー数    | Frequency          | frequency     | int    | -
CONVERSION_LABEL       | コンバージョンラベル名    | Conversion Name          | conversionName     | string    | -
OBJECTIVE_OF<br>_CONVERSION_TRACKING | コンバージョン測定の目的 | Objective of Conversion Tracking |objectiveOfConversionTracking | string  | -
CARRIER       | キャリア    | Carrier          | carrier     | string    | [CARRIER Response](#carrier)
AD_LAYOUT       | 広告レイアウト    | Ad Layout          | adLayout     | string    | [AD_LAYOUT Response](#ad_layout)
IMAGE_OPTION       | 画像自動付与    | Dynamic Image Extensions          | dynamicImageExtensions     | string    | [IMAGE_OPTION Response](#image_option)
IMPS          | インプレッション数       | Impressions                   | impressions          | int   | - 
CLICK_RATE                  | クリック率           | CTR         |           ctr                  | double | -
COST                 | コスト             | Cost                                    | cost                 | int  | -  
CLICK               | クリック数           | Click                                  | click               | int  | -  
AVG_CPC           | 平均CPC           | Avg. CPC                                 | averageCpc           | double | -
CONVERSION     | 総コンバージョン数       | Total Conversions                  | totalConversions     | int  | -  
CONVERSIONRATE  | 総コンバージョン率       | Total Conversion Rate         | totalConversionRate  | double | -
CPA | コスト/総コンバージョン数   | Cost / Total Conversions | costTotalConversions | double | -
AVG_DELIVER_RANK | 平均掲載順位 | Avg. Position | averagePosition | double | -
UNIQUE_USERS           | ユニークユーザ数      | Unique Users             | uniqueUsers          | int | -
REVENUE           | 合計売上金額     | Total Revenue             | Total Revenue          | int | -
REVENUE_CONVERSIONS           | 売上 / 総コンバージョン数      | Revenue / Total Conversions   | revenueTotalConversions          | int | -
TOTAL_VIEWABLE_IMPS           | ビュー計測対象インプレッション数  | measurableImpressions         | measurableImpressions          | int | -
VIEWABLE_IMPS           | ビューインプレッション数      | Viewable Impressions           | Viewable Impressions          | int | -
INVIEW_RATE           | ビューインプレッション率      | Viewable Impression Rate            | Viewable Impression Rate          | int | -
INVIEW_CLICK           | ビュークリック数      | Viewable Clicks            | Viewable Clicks          | int | -
INVIEW_CLICK_RATE           | ビュークリック率      | Viewable CTR            | viewableCtr          | int | -




### Response Details
<a name="ad_type">
##### AD_TYPE Response
Value           | Display Name (Japanese)  | Display Name (English) 
-------------------- | ------------------------ | ---------------------- 
TEXT_AD1 | テキスト（15・19-19） | Text Ad(15-19-19)
TEXT_AD2 | テキスト（15・33） | Text Ad(15-33)
SHORT_AD1 | ショートテキスト（14・19） | Short Ad(14-19)
SHORT_AD2 | ショートテキスト（12・12） | Short Ad(12-12)
PLACEMENT_TEXT | 掲載位置指定テキスト | Placement Text Ad
TEXT_AD3 | テキスト（15・90） | Text Ad(15-90)
RESPONSIVE | レスポンシブ | Responsive
STATIC_FRAME_300X250 | 広告枠サイズ固定（300×250） | Static Frame(300×250)
NOT_REQUIRED | テキスト不要 | Text not required

<a name="gender">
##### GENDER Response
Value           | Display Name (Japanese)  | Display Name (English) 
-------------------- | ------------------------ | ---------------------- 
MALE | 男性 | Male
FEMALE | 女性 | Female
UNKNOWN | 不明 | Unknown
MALE_ADV | 男性（拡張） | Male (adv.)
FEMALE_ADV | 女性（拡張） | Female (adv.)

<a name="age">
##### AGE Response
 Display Name (Japanese)  | Display Name (English) 
 ------------------------ | ---------------------- 
～5歳 | Age / Under 6
6歳～11歳 | Age / 6-11
12歳～14歳 | Age / 12-14
15歳～17歳 | Age / 15-17
18歳～19歳 | Age / 18-19
20歳～21歳 | Age / 20-21
22歳～29歳 | Age / 22-29
30歳～39歳 | Age / 30s
40歳～49歳 | Age / 40s
50歳～59歳 | Age / 50s
60歳～69歳 | Age / 60s
70歳～ | Age / Over 70
不明 | Unknown
～5歳（拡張） | Age / Under 6 (adv.)
6歳～11歳（拡張） | Age / 6-11 (adv.)
12歳～14歳（拡張） | Age / 12-14 (adv.)
15歳～17歳（拡張） | Age / 15-17 (adv.)
18歳～19歳（拡張） | Age / 18-19 (adv.)
20歳～21歳（拡張） | Age / 20-21 (adv.)
22歳～29歳（拡張） | Age / 22-29 (adv.)
30歳～39歳（拡張） | Age / 30s (adv.)
40歳～49歳（拡張） | Age / 40s (adv.)
50歳～59歳（拡張） | Age / 50s (adv.)
60歳～69歳（拡張） | Age / 60s (adv.)
70歳～（拡張） | Age / Over 70 (adv.)


<a name="deliver">
##### DELIVER Response
To confirm the available fields for each account, please use <a href="../services/ReportDefinitionService.md">getReportFields from ReportDefinitionService</a>.


<a name="device">
##### DEVICE  Response
 Display Name (Japanese)  | Display Name (English) 
 ------------------------ | ---------------------- 
PC | PC
モバイル | Mobile
スマートフォン | SmartPhone
タブレット端末 | Tablet
そのほか | Other

<a name="ad_style">
##### AD_STYLE Response
 Display Name (Japanese)  | Display Name (English) 
 ------------------------ | ---------------------- 
テキスト | Text Ad
ディスプレイ（静止画） | Display Ad (Static Image)
ディスプレイ（アニメーション） | Display Ad (Animated)
テンプレート（静止画） | Template Ad (Static Image)
動画 | Video Ad


<a name="media_ad_format">
##### MEDIA_AD_FORMAT Response
 Display Name (Japanese)  | Display Name (English) 
 ------------------------ | ---------------------- 
728x90 | 728x90
320x50 | 320x50
300x250 | 300x250
468x60 | 468x60
320x75 | 320x75
250x250 | 250x250
200x200 | 200x200
16x16 | 16x16
336x280 | 336x280
180x150 | 180x150
160x600 | 160x600
120x600 | 120x600
970x90 | 970x90
970x250 | 970x250
88x31 | 88x31
550x480 | 550x480
300x600 | 300x600
300x500 | 300x500
300x1050 | 300x1050
120x60 | 120x60
320x100 |　320x100
57x57 | 57x57
512x512 | 512x512
480x320 | 480x320
320x480 | 320x480
1200x628 | 1200x628
180x180 | 180x180
300x300 | 300x300

<a name="carrier">
##### CARRIER Response
 Display Name (Japanese)  | Display Name (English) 
 ------------------------ | ---------------------- 
docomo | docomo
KDDI | KDDI
SoftBank | SoftBank
その他 | Other

<a name="ad_layout">
##### AD_LAYOUT Response
Value           | Display Name (Japanese)  | Display Name (English) 
-------------------- | ------------------------ | ---------------------- 
SQUARE_BANNER_TOP | スクエアバナー（トップ） | Square Banner (Top)
WIDE_BANNER_TOP | ワイドバナー（トップ） | Wide Banner (Top)
WIDE_BANNER_MIDDLE | ワイドバナー（ミドル） | Wide Banner (Middle)

<a name="image_option">
##### IMAGE_OPTION Response
Value           | Display Name (Japanese)  | Display Name (English) 
-------------------- | ------------------------ | ---------------------- 
PAUSED | オフ | Off
ACTIVE | オン | On
IGNORE | - | -

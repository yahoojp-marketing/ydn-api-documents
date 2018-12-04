# Report Fields
The table below describes available report fields of YDN API.<br>
Click any report type to see more details of available report fields.<br>
Ad reporting feature will create a report for each entity unit such as account, campaign, etc., or for each destination URL, by combination of selected report fields.<br>

* [Ad reports (Account report, Campaign report, Ad group report, Destination URL report)](./reports/AD.csv)
* [Interest category report](./reports/INTEREST_CATEGORY.csv)
* [Site category report](./reports/SITE_CATEGORY.csv)
* [Ad Delivery URL report](./reports/URL.csv)
* [Frequency report](./reports/FREQUENCY.csv)


### Behavior Types
Value           | Description
-------------------- | ------------------------ 
Attribute | Setting item of ad
Segment | Segment of actual distribution performance
Metric | Actual distribution performance of ad


### Response Details
<a name="ad_type"></a>
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

<a name="gender"></a>
##### GENDER Response
Value           | Display Name (Japanese)  | Display Name (English) 
-------------------- | ------------------------ | ---------------------- 
MALE | 男性 | Male
FEMALE | 女性 | Female
UNKNOWN | 不明 | Unknown
MALE_ADV | 男性（拡張） | Male (adv.)
FEMALE_ADV | 女性（拡張） | Female (adv.)

<a name="age"></a>
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


<a name="deliver"></a>
##### DELIVER Response
To confirm the available fields for each account, please use <a href="../services/ReportDefinitionService.md">getReportFields from ReportDefinitionService</a>.


<a name="device"></a>
##### DEVICE  Response
 Display Name (Japanese)  | Display Name (English) 
 ------------------------ | ---------------------- 
PC | PC
モバイル | Mobile
スマートフォン | SmartPhone
タブレット端末 | Tablet
そのほか | Other

<a name="ad_style"></a>
##### AD_STYLE Response
 Display Name (Japanese)  | Display Name (English) 
 ------------------------ | ---------------------- 
テキスト | Text Ad
ディスプレイ（静止画） | Display Ad (Static Image)
ディスプレイ（アニメーション） | Display Ad (Animated)
テンプレート（静止画） | Template Ad (Static Image)
動画 | Video Ad


<a name="media_ad_format"></a>
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
320x100 | 320x100
57x57 | 57x57
512x512 | 512x512
480x320 | 480x320
320x480 | 320x480
1200x628 | 1200x628
180x180 | 180x180
300x300 | 300x300
400x200 | 400x200
640x360 | 640x360
600x600 | 600x600

<a name="carrier"></a>
##### CARRIER Response
 Display Name (Japanese)  | Display Name (English) 
 ------------------------ | ---------------------- 
docomo | docomo
KDDI | KDDI
SoftBank | SoftBank
その他 | Other

<a name="ad_layout"></a>
##### AD_LAYOUT Response
Value           | Display Name (Japanese)  | Display Name (English) 
-------------------- | ------------------------ | ---------------------- 
SQUARE_BANNER_TOP | スクエアバナー（トップ） | Square Banner (Top)
WIDE_BANNER_TOP | ワイドバナー（トップ） | Wide Banner (Top)
WIDE_BANNER_MIDDLE | ワイドバナー（ミドル） | Wide Banner (Middle)

<a name="image_option"></a>
##### IMAGE_OPTION Response
Value           | Display Name (Japanese)  | Display Name (English) 
-------------------- | ------------------------ | ---------------------- 
PAUSED | オフ | Off
ACTIVE | オン | On
IGNORE | - | -

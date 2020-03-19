# AdGroupAdService

AdGroupAdServiceは広告の操作を提供します。

#### WSDL

| environment |                                      url                                      |
| ----------- | ----------------------------------------------------------------------------- |
| production  | https://location.im.yahooapis.jp/services/V201911/AdGroupAdService?wsdl |
| sandbox     | https://sandbox.im.yahooapis.jp/services/V201911/AdGroupAdService?wsdl  |

#### Namespace

http://im.yahooapis.jp/V201911/AdGroupAd

#### Service Overview

広告の取得と更新を行います。

##### ■ヒント
ディスプレイ広告（運用型）における広告の作成は、以下のベストプラクティスを参照してください。  
[ディスプレイ広告（運用型）で目的別キャンペーンを入稿する（V201911のみ）](../../bestpractice/display_ads_campaign.md)

#### Operation

AdGroupAdServiceで提供される操作を説明します。

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)

## get

### リクエスト

広告の情報を取得します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| selector | Yes | [AdGroupAdSelector](../data/AdGroupAd/AdGroupAdSelector.md) |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/AdGroupAd" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201911/AdGroupAd" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <selector>
        <accountId>1234567890</accountId>
        <campaignIds>10001</campaignIds>
        <campaignIds>10002</campaignIds>
        <campaignIds>10003</campaignIds>
        <campaignIds>10004</campaignIds>
        <campaignIds>10005</campaignIds>
        <campaignIds>10006</campaignIds>
        <campaignIds>10007</campaignIds>
        <adGroupIds>20001</adGroupIds>
        <adGroupIds>20002</adGroupIds>
        <adGroupIds>20003</adGroupIds>
        <adGroupIds>20004</adGroupIds>
        <adGroupIds>20005</adGroupIds>
        <adGroupIds>20006</adGroupIds>
        <adGroupIds>20007</adGroupIds>
        <adIds>30001</adIds>
        <adIds>30002</adIds>
        <adIds>30003</adIds>
        <adIds>30004</adIds>
        <adIds>30005</adIds>
        <adIds>30006</adIds>
        <adIds>30007</adIds>
        <mediaIds>100000</mediaIds>
        <mediaIds>100001</mediaIds>
        <labelIds>3000</labelIds>
        <labelIds>3001</labelIds>
        <containsLabelIdFlg>true</containsLabelIdFlg>
        <userStatuses>ACTIVE</userStatuses>
        <userStatuses>PAUSED</userStatuses>
        <approvalStatuses>APPROVED</approvalStatuses>
        <approvalStatuses>APPROVED_WITH_REVIEW</approvalStatuses>
        <approvalStatuses>POST_DISAPPROVED</approvalStatuses>
        <approvalStatuses>PRE_DISAPPROVED</approvalStatuses>
        <approvalStatuses>REVIEW</approvalStatuses>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>1000</ns2:numberResults>
        </paging>
        <campaignGoalFilterType>ALL</campaignGoalFilterType>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス

| パラメータ | データ型 |
| -------- | ------- |
| rval | [AdGroupAdPage](../data/AdGroupAd/AdGroupAdPage.md) |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/AdGroupAd" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>AdGroupAd</ns2:service>
      <ns2:requestTime>1574393592269</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/AdGroupAd">
      <ns2:rval>
        <totalNumEntries>7</totalNumEntries>
        <Page.Type>AdGroupAdPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>test campaign1</ns2:campaignName>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:adGroupName>test adGroup1</ns2:adGroupName>
            <ns2:adId>2000001</ns2:adId>
            <ns2:adName>test ad1</ns2:adName>
            <ns2:mediaId>100000</ns2:mediaId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupAdBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TextAd">
              <ns2:type>TEXT_LONG_AD1</ns2:type>
              <ns2:url>http://testtest.co.jp</ns2:url>
              <ns2:displayUrl>testtest.co.jp</ns2:displayUrl>
              <ns2:headline>headline</ns2:headline>
              <ns2:description>description</ns2:description>
              <ns2:description2>description2</ns2:description2>
            </ns2:ad>
            <ns2:impressionBeaconUrls>https://test.com/</ns2:impressionBeaconUrls>
            <ns2:labels>
              <ns2:labelId>3000</ns2:labelId>
              <ns2:labelName>test label</ns2:labelName>
              <ns2:description>test description</ns2:description>
              <ns2:color>#FFFFFF</ns2:color>
            </ns2:labels>
            <ns2:labels>
              <ns2:labelId>3001</ns2:labelId>
              <ns2:labelName>test label2</ns2:labelName>
              <ns2:description>test description2</ns2:description>
              <ns2:color>#FFFFFF</ns2:color>
            </ns2:labels>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10002</ns2:campaignId>
            <ns2:campaignName>test campaign2</ns2:campaignName>
            <ns2:adGroupId>20002</ns2:adGroupId>
            <ns2:adGroupName>test adGroup2</ns2:adGroupName>
            <ns2:adId>3000001</ns2:adId>
            <ns2:adName>test ad2</ns2:adName>
            <ns2:mediaId>100000</ns2:mediaId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupAdBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:PosAd">
              <ns2:type>POS_AD</ns2:type>
              <ns2:url>http://testtest.co.jp</ns2:url>
              <ns2:description>description</ns2:description>
            </ns2:ad>
            <ns2:labels>
              <ns2:labelId>3000</ns2:labelId>
              <ns2:labelName>test label</ns2:labelName>
              <ns2:description>test description</ns2:description>
              <ns2:color>#FFFFFF</ns2:color>
            </ns2:labels>
            <ns2:labels>
              <ns2:labelId>3001</ns2:labelId>
              <ns2:labelName>test label2</ns2:labelName>
              <ns2:description>test description2</ns2:description>
              <ns2:color>#FFFFFF</ns2:color>
            </ns2:labels>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10003</ns2:campaignId>
            <ns2:campaignName>test campaign3</ns2:campaignName>
            <ns2:adGroupId>20003</ns2:adGroupId>
            <ns2:adGroupName>test adGroup3</ns2:adGroupName>
            <ns2:adId>3000001</ns2:adId>
            <ns2:adName>test ad3</ns2:adName>
            <ns2:mediaId>100000</ns2:mediaId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupAdBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ResponsiveImageAd">
              <ns2:type>RESPONSIVE_IMAGE_AD</ns2:type>
              <ns2:headline>headline</ns2:headline>
              <ns2:description>description</ns2:description>
              <ns2:url>http://testtest.co.jp</ns2:url>
              <ns2:displayUrl>testtest.co.jp</ns2:displayUrl>
              <ns2:buttonText>APPLY_NOW</ns2:buttonText>
              <ns2:principal>principal</ns2:principal>
              <ns2:logoMediaId>2222</ns2:logoMediaId>
            </ns2:ad>
            <ns2:labels>
              <ns2:labelId>3000</ns2:labelId>
              <ns2:labelName>test label</ns2:labelName>
              <ns2:description>test description</ns2:description>
              <ns2:color>#FFFFFF</ns2:color>
            </ns2:labels>
            <ns2:labels>
              <ns2:labelId>3001</ns2:labelId>
              <ns2:labelName>test label2</ns2:labelName>
              <ns2:description>test description2</ns2:description>
              <ns2:color>#FFFFFF</ns2:color>
            </ns2:labels>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10004</ns2:campaignId>
            <ns2:campaignName>test campaign4</ns2:campaignName>
            <ns2:adGroupId>20004</ns2:adGroupId>
            <ns2:adGroupName>test adGroup4</ns2:adGroupName>
            <ns2:adId>3000001</ns2:adId>
            <ns2:adName>test ad4</ns2:adName>
            <ns2:mediaId>100000</ns2:mediaId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupAdBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:StaticFrameAd">
              <ns2:type>STATIC_FRAME_AD</ns2:type>
              <ns2:size>300X250</ns2:size>
              <ns2:headline>headline</ns2:headline>
              <ns2:description>description</ns2:description>
              <ns2:url>http://testtest.co.jp</ns2:url>
              <ns2:displayUrl>testtest.co.jp</ns2:displayUrl>
              <ns2:layout>SQUARE_BANNER_TOP</ns2:layout>
              <ns2:buttonText>APPLY_NOW</ns2:buttonText>
              <ns2:principal>principal</ns2:principal>
              <ns2:colorSetId>1000000005</ns2:colorSetId>
            </ns2:ad>
            <ns2:labels>
              <ns2:labelId>3000</ns2:labelId>
              <ns2:labelName>test label</ns2:labelName>
              <ns2:description>test description</ns2:description>
              <ns2:color>#FFFFFF</ns2:color>
            </ns2:labels>
            <ns2:labels>
              <ns2:labelId>3001</ns2:labelId>
              <ns2:labelName>test label2</ns2:labelName>
              <ns2:description>test description2</ns2:description>
              <ns2:color>#FFFFFF</ns2:color>
            </ns2:labels>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10005</ns2:campaignId>
            <ns2:campaignName>test campaign5</ns2:campaignName>
            <ns2:adGroupId>20005</ns2:adGroupId>
            <ns2:adGroupName>test adGroup5</ns2:adGroupName>
            <ns2:adId>3000001</ns2:adId>
            <ns2:adName>test ad5</ns2:adName>
            <ns2:mediaId>100001</ns2:mediaId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupAdBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:BannerImageAd">
              <ns2:type>BANNER_IMAGE_AD</ns2:type>
              <ns2:url>http://testtest.co.jp</ns2:url>
              <ns2:displayUrl>testtest.co.jp</ns2:displayUrl>
            </ns2:ad>
            <ns2:labels>
              <ns2:labelId>3000</ns2:labelId>
              <ns2:labelName>test label</ns2:labelName>
              <ns2:description>test description</ns2:description>
              <ns2:color>#FFFFFF</ns2:color>
            </ns2:labels>
            <ns2:labels>
              <ns2:labelId>3001</ns2:labelId>
              <ns2:labelName>test label2</ns2:labelName>
              <ns2:description>test description2</ns2:description>
              <ns2:color>#FFFFFF</ns2:color>
            </ns2:labels>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10006</ns2:campaignId>
            <ns2:campaignName>test campaign6</ns2:campaignName>
            <ns2:adGroupId>20006</ns2:adGroupId>
            <ns2:adGroupName>test adGroup6</ns2:adGroupName>
            <ns2:adId>3000001</ns2:adId>
            <ns2:adName>test ad6</ns2:adName>
            <ns2:mediaId>100001</ns2:mediaId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPVAdGroupAdBid">
              <ns2:type>MANUAL_CPV</ns2:type>
              <ns2:maxCpv>100000</ns2:maxCpv>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ResponsiveVideoAd">
              <ns2:type>RESPONSIVE_VIDEO_AD</ns2:type>
              <ns2:thumbnailMediaId>555555</ns2:thumbnailMediaId>
              <ns2:headline>headline</ns2:headline>
              <ns2:description>description</ns2:description>
              <ns2:url>http://testtest.co.jp</ns2:url>
              <ns2:displayUrl>testtest.co.jp</ns2:displayUrl>
              <ns2:buttonText>APPLY_NOW</ns2:buttonText>
              <ns2:principal>principal</ns2:principal>
              <ns2:logoMediaId>99999</ns2:logoMediaId>
              <ns2:videoStartBeaconUrls>http://testtest.videoStartBeaconUrls.co.jp</ns2:videoStartBeaconUrls>
              <ns2:videoStartBeaconUrls>http://testtest.videoStartBeaconUrls2.co.jp</ns2:videoStartBeaconUrls>
              <ns2:video3SecBeaconUrls>http://testtest.video3SecBeaconUrls.co.jp</ns2:video3SecBeaconUrls>
              <ns2:video3SecBeaconUrls>http://testtest.video3SecBeaconUrls2.co.jp</ns2:video3SecBeaconUrls>
              <ns2:videoPaidBeaconUrls>http://testtest.videoPaidBeaconUrls.co.jp</ns2:videoPaidBeaconUrls>
              <ns2:videoPaidBeaconUrls>http://testtest.videoPaidBeaconUrls2.co.jp</ns2:videoPaidBeaconUrls>
              <ns2:videoCompleteBeaconUrls>http://testtest.videoCompleteBeaconUrls.co.jp</ns2:videoCompleteBeaconUrls>
              <ns2:videoCompleteBeaconUrls>http://testtest.videoCompleteBeaconUrls2.co.jp</ns2:videoCompleteBeaconUrls>
            </ns2:ad>
            <ns2:labels>
              <ns2:labelId>3000</ns2:labelId>
              <ns2:labelName>test label</ns2:labelName>
              <ns2:description>test description</ns2:description>
              <ns2:color>#FFFFFF</ns2:color>
            </ns2:labels>
            <ns2:labels>
              <ns2:labelId>3001</ns2:labelId>
              <ns2:labelName>test label2</ns2:labelName>
              <ns2:description>test description2</ns2:description>
              <ns2:color>#FFFFFF</ns2:color>
            </ns2:labels>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10007</ns2:campaignId>
            <ns2:campaignName>test campaign7</ns2:campaignName>
            <ns2:adGroupId>20007</ns2:adGroupId>
            <ns2:adGroupName>test adGroup7</ns2:adGroupName>
            <ns2:adId>3000001</ns2:adId>
            <ns2:adName>test ad7</ns2:adName>
            <ns2:mediaId>100001</ns2:mediaId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupAdBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:DynamicAd">
              <ns2:type>DYNAMIC_AD</ns2:type>
              <ns2:url>http://hogehoge.co.jp</ns2:url>
              <ns2:displayUrl>hogehoge.co.jp</ns2:displayUrl>
              <ns2:buttonText>APPLY_NOW</ns2:buttonText>
              <ns2:principal>principal</ns2:principal>
              <ns2:logoMediaId>99991</ns2:logoMediaId>
              <ns2:logoMediaId2>99992</ns2:logoMediaId2>
              <ns2:logoMediaId3>99993</ns2:logoMediaId3>
              <ns2:prefix>pr</ns2:prefix>
              <ns2:suffix>suf</ns2:suffix>
              <ns2:brandColor>#FFFFFF</ns2:brandColor>
            </ns2:ad>
            <ns2:labels>
              <ns2:labelId>3000</ns2:labelId>
              <ns2:labelName>test label</ns2:labelName>
              <ns2:description>test description</ns2:description>
              <ns2:color>#FFFFFF</ns2:color>
            </ns2:labels>
            <ns2:labels>
              <ns2:labelId>3001</ns2:labelId>
              <ns2:labelName>test label2</ns2:labelName>
              <ns2:description>test description2</ns2:description>
              <ns2:color>#FFFFFF</ns2:color>
            </ns2:labels>
            <ns2:thirdPartyTrackingVendor>TEST</ns2:thirdPartyTrackingVendor>
            <ns2:thirdPartyTrackingScriptUrl>https://test.com</ns2:thirdPartyTrackingScriptUrl>
          </ns2:adGroupAd>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)

### リクエスト

広告を追加します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| operations | Yes | [AdGroupAdOperation](../data/AdGroupAd/AdGroupAdOperation.md) |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/AdGroupAd" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201911/AdGroupAd">
      <operations>
        <operator>ADD</operator>
        <accountId>1234567890</accountId>
        <operand>
          <accountId>0</accountId>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <adName>TextAd</adName>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPCAdGroupAdBid">
            <type>MANUAL_CPC</type>
            <maxCpc>100</maxCpc>
          </bid>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="TextAd">
            <type>TEXT_LONG_AD1</type>
            <url>http://test.co.jp</url>
            <displayUrl>test.co.jp</displayUrl>
            <headline>headline</headline>
            <description>description</description>
            <description2>description2</description2>
          </ad>
          <impressionBeaconUrls>https://test.com</impressionBeaconUrls>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignId>10002</campaignId>
          <adGroupId>20002</adGroupId>
          <adName>PosAd</adName>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPCAdGroupAdBid">
            <type>MANUAL_CPC</type>
            <maxCpc>100</maxCpc>
          </bid>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="PosAd">
            <type>POS_AD</type>
            <url>http://test.co.jp</url>
            <description>description</description>
          </ad>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignId>10003</campaignId>
          <adGroupId>20003</adGroupId>
          <adName>ResponsiveImageAd</adName>
          <mediaId>1111</mediaId>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPCAdGroupAdBid">
            <type>MANUAL_CPC</type>
            <maxCpc>100</maxCpc>
          </bid>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ResponsiveImageAd">
            <type>RESPONSIVE_IMAGE_AD</type>
            <headline>headline</headline>
            <description>description</description>
            <url>http://test.co.jp</url>
            <displayUrl>test.co.jp</displayUrl>
            <buttonText>APPLY_NOW</buttonText>
            <principal>principal</principal>
            <logoMediaId>66666</logoMediaId>
          </ad>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignId>10004</campaignId>
          <adGroupId>20004</adGroupId>
          <adName>StaticFrameAd</adName>
          <mediaId>1111</mediaId>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPCAdGroupAdBid">
            <type>MANUAL_CPC</type>
            <maxCpc>100</maxCpc>
          </bid>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="StaticFrameAd">
            <type>STATIC_FRAME_AD</type>
            <size>300X250</size>
            <headline>headline</headline>
            <description>description</description>
            <url>http://test.co.jp</url>
            <displayUrl>test.co.jp</displayUrl>
            <layout>SQUARE_BANNER_TOP</layout>
            <buttonText>APPLY_NOW</buttonText>
            <principal>principal</principal>
            <colorSetId>1000000005</colorSetId>
          </ad>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignId>10005</campaignId>
          <adGroupId>20005</adGroupId>
          <adName>BannerImageAd</adName>
          <mediaId>1111</mediaId>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPCAdGroupAdBid">
            <type>MANUAL_CPC</type>
            <maxCpc>100</maxCpc>
          </bid>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="BannerImageAd">
            <type>BANNER_IMAGE_AD</type>
            <url>http://test.co.jp</url>
            <displayUrl>test.co.jp</displayUrl>
          </ad>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignId>10006</campaignId>
          <adGroupId>20006</adGroupId>
          <adName>ResponsiveVideoAd</adName>
          <mediaId>1111</mediaId>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPVAdGroupAdBid">
            <type>MANUAL_CPV</type>
            <maxCpv>10000</maxCpv>
          </bid>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ResponsiveVideoAd">
            <type>RESPONSIVE_VIDEO_AD</type>
            <thumbnailMediaId>44444</thumbnailMediaId>
            <headline>headline</headline>
            <description>description</description>
            <url>http://test.co.jp</url>
            <displayUrl>test.co.jp</displayUrl>
            <buttonText>APPLY_NOW</buttonText>
            <principal>principal</principal>
            <logoMediaId>894651</logoMediaId>
            <videoStartBeaconUrls>http://testtest.videoStartBeaconUrls.co.jp</videoStartBeaconUrls>
            <videoStartBeaconUrls>http://testtest.videoStartBeaconUrls2.co.jp</videoStartBeaconUrls>
            <video3SecBeaconUrls>http://testtest.video3SecBeaconUrls.co.jp</video3SecBeaconUrls>
            <video3SecBeaconUrls>http://testtest.video3SecBeaconUrls2.co.jp</video3SecBeaconUrls>
            <videoPaidBeaconUrls>http://testtest.videoPaidBeaconUrls.co.jp</videoPaidBeaconUrls>
            <videoPaidBeaconUrls>http://testtest.videoPaidBeaconUrls2.co.jp</videoPaidBeaconUrls>
            <videoCompleteBeaconUrls>http://testtest.videoCompleteBeaconUrls.co.jp</videoCompleteBeaconUrls>
            <videoCompleteBeaconUrls>http://testtest.videoCompleteBeaconUrls2.co.jp</videoCompleteBeaconUrls>
            <video25PercentBeaconUrls>http://testtest.video25PercentBeaconUrls.co.jp</video25PercentBeaconUrls>
            <video25PercentBeaconUrls>http://testtest.video25PercentBeaconUrls2.co.jp</video25PercentBeaconUrls>
            <video50PercentBeaconUrls>http://testtest.video50PercentBeaconUrls.co.jp</video50PercentBeaconUrls>
            <video50PercentBeaconUrls>http://testtest.video50PercentBeaconUrls2.co.jp</video50PercentBeaconUrls>
            <video75PercentBeaconUrls>http://testtest.video75PercentBeaconUrls.co.jp</video75PercentBeaconUrls>
            <video75PercentBeaconUrls>http://testtest.video75PercentBeaconUrls2.co.jp</video75PercentBeaconUrls>
          </ad>
          <thirdPartyTrackingScriptUrl>https://testtest.com/</thirdPartyTrackingScriptUrl>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignId>10007</campaignId>
          <adGroupId>20007</adGroupId>
          <adName>DynamicAd</adName>
          <mediaId>1111</mediaId>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPCAdGroupAdBid">
            <type>MANUAL_CPC</type>
            <maxCpc>100</maxCpc>
          </bid>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="DynamicAd">
            <type>DYNAMIC_AD</type>
            <url>http://hogehoge.co.jp</url>
            <displayUrl>hogehoge.co.jp</displayUrl>
            <buttonText>APPLY_NOW</buttonText>
            <principal>principal</principal>
            <logoMediaId>99991</logoMediaId>
            <logoMediaId2>99992</logoMediaId2>
            <logoMediaId3>99993</logoMediaId3>
            <prefix>pr</prefix>
            <suffix>suf</suffix>
            <brandColor>#FFFFFF</brandColor>
            <campaignBannerUrl>http://hogehoge.co.jp</campaignBannerUrl>
            <campaignBannerMediaId>99994</campaignBannerMediaId>
            <campaignBannerMediaId2>99995</campaignBannerMediaId2>
            <campaignBannerMediaId3>99996</campaignBannerMediaId3>
            <campaignBannerMediaId4>99997</campaignBannerMediaId4>
          </ad>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignId>10008</campaignId>
          <adGroupId>20008</adGroupId>
          <adName>BannerVideoAd</adName>
          <mediaId>88813</mediaId>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPVAdGroupAdBid">
            <type>MANUAL_CPV</type>
            <maxCpv>10000</maxCpv>
          </bid>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="BannerVideoAd">
            <type>BANNER_VIDEO_AD</type>
            <url>http://test.co.jp</url>
            <displayUrl>test.co.jp</displayUrl>
            <thumbnailMediaId>44444</thumbnailMediaId>
            <videoStartBeaconUrls>http://testtest.videoStartBeaconUrls.co.jp</videoStartBeaconUrls>
            <videoStartBeaconUrls>http://testtest.videoStartBeaconUrls2.co.jp</videoStartBeaconUrls>
            <video3SecBeaconUrls>http://testtest.video3SecBeaconUrls.co.jp</video3SecBeaconUrls>
            <video3SecBeaconUrls>http://testtest.video3SecBeaconUrls2.co.jp</video3SecBeaconUrls>
            <videoPaidBeaconUrls>http://testtest.videoPaidBeaconUrls.co.jp</videoPaidBeaconUrls>
            <videoPaidBeaconUrls>http://testtest.videoPaidBeaconUrls2.co.jp</videoPaidBeaconUrls>
            <videoCompleteBeaconUrls>http://testtest.videoCompleteBeaconUrls.co.jp</videoCompleteBeaconUrls>
            <videoCompleteBeaconUrls>http://testtest.videoCompleteBeaconUrls2.co.jp</videoCompleteBeaconUrls>
            <video25PercentBeaconUrls>http://testtest.video25PercentBeaconUrls.co.jp</video25PercentBeaconUrls>
            <video25PercentBeaconUrls>http://testtest.video25PercentBeaconUrls2.co.jp</video25PercentBeaconUrls>
            <video50PercentBeaconUrls>http://testtest.video50PercentBeaconUrls.co.jp</video50PercentBeaconUrls>
            <video50PercentBeaconUrls>http://testtest.video50PercentBeaconUrls2.co.jp</video50PercentBeaconUrls>
            <video75PercentBeaconUrls>http://testtest.video75PercentBeaconUrls.co.jp</video75PercentBeaconUrls>
            <video75PercentBeaconUrls>http://testtest.video75PercentBeaconUrls2.co.jp</video75PercentBeaconUrls>
          </ad>
          <thirdPartyTrackingScriptUrl>https://testtest.com/</thirdPartyTrackingScriptUrl>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス

| パラメータ | データ型 |
| -------- | ------- |
| rval | [AdGroupAdReturnValue](../data/AdGroupAd/AdGroupAdReturnValue.md) |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/AdGroupAd" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>AdGroupAd</ns2:service>
      <ns2:requestTime>1574393592412</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/AdGroupAd">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupAdReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>test campaign1</ns2:campaignName>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:adGroupName>test adGroup1</ns2:adGroupName>
            <ns2:adId>30001</ns2:adId>
            <ns2:adName>TextAd</ns2:adName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupAdBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TextAd">
              <ns2:type>TEXT_LONG_AD1</ns2:type>
              <ns2:url>http://testtest.co.jp</ns2:url>
              <ns2:displayUrl>testtest.co.jp</ns2:displayUrl>
              <ns2:headline>headline</ns2:headline>
              <ns2:description>description</ns2:description>
              <ns2:description2>description2</ns2:description2>
            </ns2:ad>
            <ns2:impressionBeaconUrls>https://test.com/</ns2:impressionBeaconUrls>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10002</ns2:campaignId>
            <ns2:campaignName>test campaign2</ns2:campaignName>
            <ns2:adGroupId>20002</ns2:adGroupId>
            <ns2:adGroupName>test adGroup2</ns2:adGroupName>
            <ns2:adId>30002</ns2:adId>
            <ns2:adName>PosAd</ns2:adName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupAdBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:PosAd">
              <ns2:type>POS_AD</ns2:type>
              <ns2:url>http://testtest.co.jp</ns2:url>
              <ns2:description>description</ns2:description>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10003</ns2:campaignId>
            <ns2:campaignName>test campaign3</ns2:campaignName>
            <ns2:adGroupId>20003</ns2:adGroupId>
            <ns2:adGroupName>test adGroup3</ns2:adGroupName>
            <ns2:adId>30003</ns2:adId>
            <ns2:adName>ResponsiveImageAd</ns2:adName>
            <ns2:mediaId>1111</ns2:mediaId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupAdBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ResponsiveImageAd">
              <ns2:type>RESPONSIVE_IMAGE_AD</ns2:type>
              <ns2:headline>headline</ns2:headline>
              <ns2:description>description</ns2:description>
              <ns2:url>http://testtest.co.jp</ns2:url>
              <ns2:displayUrl>testtest.co.jp</ns2:displayUrl>
              <ns2:buttonText>APPLY_NOW</ns2:buttonText>
              <ns2:principal>principal</ns2:principal>
              <ns2:logoMediaId>2222</ns2:logoMediaId>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10004</ns2:campaignId>
            <ns2:campaignName>test campaign4</ns2:campaignName>
            <ns2:adGroupId>20004</ns2:adGroupId>
            <ns2:adGroupName>test adGroup4</ns2:adGroupName>
            <ns2:adId>30004</ns2:adId>
            <ns2:adName>StaticFrameAd</ns2:adName>
            <ns2:mediaId>1111</ns2:mediaId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupAdBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:StaticFrameAd">
              <ns2:type>STATIC_FRAME_AD</ns2:type>
              <ns2:size>300X250</ns2:size>
              <ns2:headline>headline</ns2:headline>
              <ns2:description>description</ns2:description>
              <ns2:url>http://testtest.co.jp</ns2:url>
              <ns2:displayUrl>testtest.co.jp</ns2:displayUrl>
              <ns2:layout>SQUARE_BANNER_TOP</ns2:layout>
              <ns2:buttonText>APPLY_NOW</ns2:buttonText>
              <ns2:principal>principal</ns2:principal>
              <ns2:colorSetId>1000000005</ns2:colorSetId>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10005</ns2:campaignId>
            <ns2:campaignName>test campaign5</ns2:campaignName>
            <ns2:adGroupId>20005</ns2:adGroupId>
            <ns2:adGroupName>test adGroup5</ns2:adGroupName>
            <ns2:adId>30005</ns2:adId>
            <ns2:adName>BannerImageAd</ns2:adName>
            <ns2:mediaId>1111</ns2:mediaId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupAdBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:BannerImageAd">
              <ns2:type>BANNER_IMAGE_AD</ns2:type>
              <ns2:url>http://testtest.co.jp</ns2:url>
              <ns2:displayUrl>testtest.co.jp</ns2:displayUrl>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10006</ns2:campaignId>
            <ns2:campaignName>test campaign6</ns2:campaignName>
            <ns2:adGroupId>20006</ns2:adGroupId>
            <ns2:adGroupName>test adGroup6</ns2:adGroupName>
            <ns2:adId>30006</ns2:adId>
            <ns2:adName>ResponsiveVideoAd</ns2:adName>
            <ns2:mediaId>1111</ns2:mediaId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPVAdGroupAdBid">
              <ns2:type>MANUAL_CPV</ns2:type>
              <ns2:maxCpv>100000</ns2:maxCpv>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ResponsiveVideoAd">
              <ns2:type>RESPONSIVE_VIDEO_AD</ns2:type>
              <ns2:thumbnailMediaId>555555</ns2:thumbnailMediaId>
              <ns2:headline>headline</ns2:headline>
              <ns2:description>description</ns2:description>
              <ns2:url>http://testtest.co.jp</ns2:url>
              <ns2:displayUrl>testtest.co.jp</ns2:displayUrl>
              <ns2:buttonText>APPLY_NOW</ns2:buttonText>
              <ns2:principal>principal</ns2:principal>
              <ns2:logoMediaId>99999</ns2:logoMediaId>
              <ns2:videoStartBeaconUrls>http://testtest.videoStartBeaconUrls.co.jp</ns2:videoStartBeaconUrls>
              <ns2:videoStartBeaconUrls>http://testtest.videoStartBeaconUrls2.co.jp</ns2:videoStartBeaconUrls>
              <ns2:video3SecBeaconUrls>http://testtest.video3SecBeaconUrls.co.jp</ns2:video3SecBeaconUrls>
              <ns2:video3SecBeaconUrls>http://testtest.video3SecBeaconUrls2.co.jp</ns2:video3SecBeaconUrls>
              <ns2:videoPaidBeaconUrls>http://testtest.videoPaidBeaconUrls.co.jp</ns2:videoPaidBeaconUrls>
              <ns2:videoPaidBeaconUrls>http://testtest.videoPaidBeaconUrls2.co.jp</ns2:videoPaidBeaconUrls>
              <ns2:videoCompleteBeaconUrls>http://testtest.videoCompleteBeaconUrls.co.jp</ns2:videoCompleteBeaconUrls>
              <ns2:videoCompleteBeaconUrls>http://testtest.videoCompleteBeaconUrls2.co.jp</ns2:videoCompleteBeaconUrls>
              <ns2:video25PercentBeaconUrls>http://testtest.video25PercentBeaconUrls.co.jp</ns2:video25PercentBeaconUrls>
              <ns2:video25PercentBeaconUrls>http://testtest.video25PercentBeaconUrls2.co.jp</ns2:video25PercentBeaconUrls>
              <ns2:video50PercentBeaconUrls>http://testtest.video50PercentBeaconUrls.co.jp</ns2:video50PercentBeaconUrls>
              <ns2:video50PercentBeaconUrls>http://testtest.video50PercentBeaconUrls2.co.jp</ns2:video50PercentBeaconUrls>
              <ns2:video75PercentBeaconUrls>http://testtest.video75PercentBeaconUrls.co.jp</ns2:video75PercentBeaconUrls>
              <ns2:video75PercentBeaconUrls>http://testtest.video75PercentBeaconUrls2.co.jp</ns2:video75PercentBeaconUrls>
            </ns2:ad>
            <ns2:thirdPartyTrackingVendor>TEST</ns2:thirdPartyTrackingVendor>
            <ns2:thirdPartyTrackingScriptUrl>https://testtest.com/</ns2:thirdPartyTrackingScriptUrl>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10007</ns2:campaignId>
            <ns2:campaignName>test campaign7</ns2:campaignName>
            <ns2:adGroupId>20007</ns2:adGroupId>
            <ns2:adGroupName>test adGroup7</ns2:adGroupName>
            <ns2:adId>30007</ns2:adId>
            <ns2:adName>DynamicAd</ns2:adName>
            <ns2:mediaId>1111</ns2:mediaId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupAdBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:DynamicAd">
              <ns2:type>DYNAMIC_AD</ns2:type>
              <ns2:url>http://hogehoge.co.jp</ns2:url>
              <ns2:displayUrl>hogehoge.co.jp</ns2:displayUrl>
              <ns2:buttonText>APPLY_NOW</ns2:buttonText>
              <ns2:principal>principal</ns2:principal>
              <ns2:logoMediaId>99991</ns2:logoMediaId>
              <ns2:logoMediaId2>99992</ns2:logoMediaId2>
              <ns2:logoMediaId3>99993</ns2:logoMediaId3>
              <ns2:prefix>pr</ns2:prefix>
              <ns2:suffix>suf</ns2:suffix>
              <ns2:brandColor>#FFFFFF</ns2:brandColor>
              <ns2:campaignBannerUrl>http://hogehoge.co.jp</ns2:campaignBannerUrl>
              <ns2:campaignBannerMediaId>99994</ns2:campaignBannerMediaId>
              <ns2:campaignBannerMediaId2>99995</ns2:campaignBannerMediaId2>
              <ns2:campaignBannerMediaId3>99996</ns2:campaignBannerMediaId3>
              <ns2:campaignBannerMediaId4>99997</ns2:campaignBannerMediaId4>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AdGroupAd">
          <ns2:accountId>1234567890</ns2:accountId>
          <ns2:campaignId>10008</ns2:campaignId>
          <ns2:campaignName>test campaign8</ns2:campaignName>
          <ns2:adGroupId>20008</ns2:adGroupId>
          <ns2:adGroupName>test adGroup8</ns2:adGroupName>
          <ns2:adId>30008</ns2:adId>
          <ns2:adName>BannerVideoAd</ns2:adName>
          <ns2:mediaId>88813</ns2:mediaId>
          <ns2:userStatus>ACTIVE</ns2:userStatus>
          <ns2:bid xsi:type="ns2:ManualCPVAdGroupAdBid">
            <ns2:type>MANUAL_CPV</ns2:type>
            <ns2:maxCpv>10000</ns2:maxCpv>
          </ns2:bid>
          <ns2:ad xsi:type="ns2:BannerVideoAd">
            <ns2:type>BANNER_VIDEO_AD</ns2:type>
            <ns2:url>http://test.co.jp</ns2:url>
            <ns2:displayUrl>test.co.jp</ns2:displayUrl>
            <ns2:thumbnailMediaId>44444</ns2:thumbnailMediaId>
            <ns2:videoStartBeaconUrls>http://testtest.videoStartBeaconUrls.co.jp</ns2:videoStartBeaconUrls>
            <ns2:videoStartBeaconUrls>http://testtest.videoStartBeaconUrls2.co.jp</ns2:videoStartBeaconUrls>
            <ns2:video3SecBeaconUrls>http://testtest.video3SecBeaconUrls.co.jp</ns2:video3SecBeaconUrls>
            <ns2:video3SecBeaconUrls>http://testtest.video3SecBeaconUrls2.co.jp</ns2:video3SecBeaconUrls>
            <ns2:videoPaidBeaconUrls>http://testtest.videoPaidBeaconUrls.co.jp</ns2:videoPaidBeaconUrls>
            <ns2:videoPaidBeaconUrls>http://testtest.videoPaidBeaconUrls2.co.jp</ns2:videoPaidBeaconUrls>
            <ns2:videoCompleteBeaconUrls>http://testtest.videoCompleteBeaconUrls.co.jp</ns2:videoCompleteBeaconUrls>
            <ns2:videoCompleteBeaconUrls>http://testtest.videoCompleteBeaconUrls2.co.jp</ns2:videoCompleteBeaconUrls>
            <ns2:video25PercentBeaconUrls>http://testtest.video25PercentBeaconUrls.co.jp</ns2:video25PercentBeaconUrls>
            <ns2:video25PercentBeaconUrls>http://testtest.video25PercentBeaconUrls2.co.jp</ns2:video25PercentBeaconUrls>
            <ns2:video50PercentBeaconUrls>http://testtest.video50PercentBeaconUrls.co.jp</ns2:video50PercentBeaconUrls>
            <ns2:video50PercentBeaconUrls>http://testtest.video50PercentBeaconUrls2.co.jp</ns2:video50PercentBeaconUrls>
            <ns2:video75PercentBeaconUrls>http://testtest.video75PercentBeaconUrls.co.jp</ns2:video75PercentBeaconUrls>
            <ns2:video75PercentBeaconUrls>http://testtest.video75PercentBeaconUrls2.co.jp</ns2:video75PercentBeaconUrls>
          </ns2:ad>
          <ns2:thirdPartyTrackingVendor>TEST</ns2:thirdPartyTrackingVendor>
          <ns2:thirdPartyTrackingScriptUrl>https://testtest.com/</ns2:thirdPartyTrackingScriptUrl>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)

### リクエスト

広告を変更します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| operations | Yes | [AdGroupAdOperation](../data/AdGroupAd/AdGroupAdOperation.md) |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/AdGroupAd" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201911/AdGroupAd">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <accountId>0</accountId>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <adId>30001</adId>
          <adName>Set TextAd</adName>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPCAdGroupAdBid">
            <maxCpc>100</maxCpc>
          </bid>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="TextAd">
            <type>TEXT_LONG_AD1</type>
            <url>http://test.co.jp</url>
            <displayUrl>test.co.jp</displayUrl>
            <headline>headline</headline>
            <description>description</description>
            <description2>description2</description2>
          </ad>
          <impressionBeaconUrls>https://test.com</impressionBeaconUrls>
          <isRemoveBeaconUrls>TRUE</isRemoveBeaconUrls>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignId>10002</campaignId>
          <adGroupId>20002</adGroupId>
          <adId>30002</adId>
          <adName>Set PosAd</adName>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPCAdGroupAdBid">
            <maxCpc>100</maxCpc>
          </bid>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="PosAd">
            <type>POS_AD</type>
            <url>http://test.co.jp</url>
            <description>description</description>
          </ad>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignId>10003</campaignId>
          <adGroupId>20003</adGroupId>
          <adId>30003</adId>
          <adName>Set ResponsiveImageAd</adName>
          <mediaId>9999</mediaId>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPCAdGroupAdBid">
            <maxCpc>100</maxCpc>
          </bid>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ResponsiveImageAd">
            <type>RESPONSIVE_IMAGE_AD</type>
            <headline>headline</headline>
            <description>description</description>
            <url>http://test.co.jp</url>
            <displayUrl>test.co.jp</displayUrl>
            <buttonText>APPLY_NOW</buttonText>
            <principal>principal</principal>
            <logoMediaId>66666</logoMediaId>
          </ad>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignId>10004</campaignId>
          <adGroupId>20004</adGroupId>
          <adId>30004</adId>
          <adName>Set StaticFrameAd</adName>
          <mediaId>300000</mediaId>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPCAdGroupAdBid">
            <maxCpc>100</maxCpc>
          </bid>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="StaticFrameAd">
            <type>STATIC_FRAME_AD</type>
            <size>300X250</size>
            <headline>headline</headline>
            <description>description</description>
            <url>http://test.co.jp</url>
            <displayUrl>test.co.jp</displayUrl>
            <layout>SQUARE_BANNER_TOP</layout>
            <buttonText>APPLY_NOW</buttonText>
            <principal>principal</principal>
            <colorSetId>1000000005</colorSetId>
          </ad>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignId>10005</campaignId>
          <adGroupId>20005</adGroupId>
          <adId>30005</adId>
          <adName>Set BannerImageAd</adName>
          <mediaId>480003</mediaId>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPCAdGroupAdBid">
            <maxCpc>100</maxCpc>
          </bid>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="BannerImageAd">
            <type>BANNER_IMAGE_AD</type>
            <url>http://test.co.jp</url>
            <displayUrl>test.co.jp</displayUrl>
          </ad>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignId>10006</campaignId>
          <adGroupId>20006</adGroupId>
          <adId>30006</adId>
          <adName>Set ResponsiveVideoAd</adName>
          <mediaId>88812</mediaId>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPVAdGroupAdBid">
            <maxCpv>10000</maxCpv>
          </bid>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ResponsiveVideoAd">
            <type>RESPONSIVE_VIDEO_AD</type>
            <thumbnailMediaId>44444</thumbnailMediaId>
            <headline>headline</headline>
            <description>description</description>
            <url>http://test.co.jp</url>
            <displayUrl>test.co.jp</displayUrl>
            <buttonText>APPLY_NOW</buttonText>
            <principal>principal</principal>
            <logoMediaId>894651</logoMediaId>
            <videoStartBeaconUrls>http://testtest.videoStartBeaconUrls.co.jp</videoStartBeaconUrls>
            <videoStartBeaconUrls>http://testtest.videoStartBeaconUrls2.co.jp</videoStartBeaconUrls>
            <video3SecBeaconUrls>http://testtest.video3SecBeaconUrls.co.jp</video3SecBeaconUrls>
            <video3SecBeaconUrls>http://testtest.video3SecBeaconUrls2.co.jp</video3SecBeaconUrls>
            <videoPaidBeaconUrls>http://testtest.videoPaidBeaconUrls.co.jp</videoPaidBeaconUrls>
            <videoPaidBeaconUrls>http://testtest.videoPaidBeaconUrls2.co.jp</videoPaidBeaconUrls>
            <videoCompleteBeaconUrls>http://testtest.videoCompleteBeaconUrls.co.jp</videoCompleteBeaconUrls>
            <videoCompleteBeaconUrls>http://testtest.videoCompleteBeaconUrls2.co.jp</videoCompleteBeaconUrls>
            <isRemoveVideo25PercentBeaconUrls>TRUE</isRemoveVideo25PercentBeaconUrls>
            <isRemoveVideo50PercentBeaconUrls>TRUE</isRemoveVideo50PercentBeaconUrls>
            <isRemoveVideo75PercentBeaconUrls>TRUE</isRemoveVideo75PercentBeaconUrls>
          </ad>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignId>10007</campaignId>
          <adGroupId>20007</adGroupId>
          <adId>30007</adId>
          <adName>Set DynamicAd</adName>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPCAdGroupAdBid">
            <maxCpc>100</maxCpc>
          </bid>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="DynamicAd">
            <type>DYNAMIC_AD</type>
            <url>http://hogehoge.co.jp</url>
            <displayUrl>hogehoge.co.jp</displayUrl>
            <buttonText>APPLY_NOW</buttonText>
            <principal>principal</principal>
            <logoMediaId>99991</logoMediaId>
            <logoMediaId2>99992</logoMediaId2>
            <logoMediaId3>99993</logoMediaId3>
            <prefix>pr</prefix>
            <suffix>suf</suffix>
            <brandColor>#FFFFFF</brandColor>
            <isRemoveCampaignBannerUrl>TRUE</isRemoveCampaignBannerUrl>
            <isRemoveCampaignBannerMediaId>TRUE</isRemoveCampaignBannerMediaId>
            <isRemoveCampaignBannerMediaId2>TRUE</isRemoveCampaignBannerMediaId2>
            <isRemoveCampaignBannerMediaId3>TRUE</isRemoveCampaignBannerMediaId3>
            <isRemoveCampaignBannerMediaId4>TRUE</isRemoveCampaignBannerMediaId4>
          </ad>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス

| パラメータ | データ型 |
| -------- | ------- |
| rval | [AdGroupAdReturnValue](../data/AdGroupAd/AdGroupAdReturnValue.md) |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/AdGroupAd" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>AdGroupAd</ns2:service>
      <ns2:requestTime>1574393592574</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/AdGroupAd">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupAdReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>test campaign1</ns2:campaignName>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:adGroupName>test adGroup1</ns2:adGroupName>
            <ns2:adId>30001</ns2:adId>
            <ns2:adName>Set TextAd</ns2:adName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED_WITH_REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupAdBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TextAd">
              <ns2:type>TEXT_LONG_AD1</ns2:type>
              <ns2:url>http://testtest.co.jp</ns2:url>
              <ns2:displayUrl>testtest.co.jp</ns2:displayUrl>
              <ns2:headline>headline</ns2:headline>
              <ns2:description>description</ns2:description>
              <ns2:description2>description2</ns2:description2>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10002</ns2:campaignId>
            <ns2:campaignName>test campaign2</ns2:campaignName>
            <ns2:adGroupId>20002</ns2:adGroupId>
            <ns2:adGroupName>test adGroup2</ns2:adGroupName>
            <ns2:adId>30002</ns2:adId>
            <ns2:adName>Set PosAd</ns2:adName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED_WITH_REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupAdBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:PosAd">
              <ns2:type>POS_AD</ns2:type>
              <ns2:url>http://testtest.co.jp</ns2:url>
              <ns2:description>description</ns2:description>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10003</ns2:campaignId>
            <ns2:campaignName>test campaign3</ns2:campaignName>
            <ns2:adGroupId>20003</ns2:adGroupId>
            <ns2:adGroupName>test adGroup3</ns2:adGroupName>
            <ns2:adId>30003</ns2:adId>
            <ns2:adName>Set ResponsiveImageAd</ns2:adName>
            <ns2:mediaId>9999</ns2:mediaId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED_WITH_REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupAdBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ResponsiveImageAd">
              <ns2:type>RESPONSIVE_IMAGE_AD</ns2:type>
              <ns2:headline>headline</ns2:headline>
              <ns2:description>description</ns2:description>
              <ns2:url>http://testtest.co.jp</ns2:url>
              <ns2:displayUrl>testtest.co.jp</ns2:displayUrl>
              <ns2:buttonText>APPLY_NOW</ns2:buttonText>
              <ns2:principal>principal</ns2:principal>
              <ns2:logoMediaId>2222</ns2:logoMediaId>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10004</ns2:campaignId>
            <ns2:campaignName>test campaign4</ns2:campaignName>
            <ns2:adGroupId>20004</ns2:adGroupId>
            <ns2:adGroupName>test adGroup4</ns2:adGroupName>
            <ns2:adId>30004</ns2:adId>
            <ns2:adName>Set StaticFrameAd</ns2:adName>
            <ns2:mediaId>300000</ns2:mediaId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED_WITH_REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupAdBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:StaticFrameAd">
              <ns2:type>STATIC_FRAME_AD</ns2:type>
              <ns2:size>300X250</ns2:size>
              <ns2:headline>headline</ns2:headline>
              <ns2:description>description</ns2:description>
              <ns2:url>http://testtest.co.jp</ns2:url>
              <ns2:displayUrl>testtest.co.jp</ns2:displayUrl>
              <ns2:layout>SQUARE_BANNER_TOP</ns2:layout>
              <ns2:buttonText>APPLY_NOW</ns2:buttonText>
              <ns2:principal>principal</ns2:principal>
              <ns2:colorSetId>1000000005</ns2:colorSetId>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10005</ns2:campaignId>
            <ns2:campaignName>test campaign5</ns2:campaignName>
            <ns2:adGroupId>20005</ns2:adGroupId>
            <ns2:adGroupName>test adGroup5</ns2:adGroupName>
            <ns2:adId>30005</ns2:adId>
            <ns2:adName>Set BannerImageAd</ns2:adName>
            <ns2:mediaId>480003</ns2:mediaId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED_WITH_REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupAdBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:BannerImageAd">
              <ns2:type>BANNER_IMAGE_AD</ns2:type>
              <ns2:url>http://testtest.co.jp</ns2:url>
              <ns2:displayUrl>testtest.co.jp</ns2:displayUrl>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10006</ns2:campaignId>
            <ns2:campaignName>test campaign6</ns2:campaignName>
            <ns2:adGroupId>20006</ns2:adGroupId>
            <ns2:adGroupName>test adGroup6</ns2:adGroupName>
            <ns2:adId>30006</ns2:adId>
            <ns2:adName>Set ResponsiveVideoAd</ns2:adName>
            <ns2:mediaId>88812</ns2:mediaId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED_WITH_REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPVAdGroupAdBid">
              <ns2:type>MANUAL_CPV</ns2:type>
              <ns2:maxCpv>100000</ns2:maxCpv>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ResponsiveVideoAd">
              <ns2:type>RESPONSIVE_VIDEO_AD</ns2:type>
              <ns2:thumbnailMediaId>555555</ns2:thumbnailMediaId>
              <ns2:headline>headline</ns2:headline>
              <ns2:description>description</ns2:description>
              <ns2:url>http://testtest.co.jp</ns2:url>
              <ns2:displayUrl>testtest.co.jp</ns2:displayUrl>
              <ns2:buttonText>APPLY_NOW</ns2:buttonText>
              <ns2:principal>principal</ns2:principal>
              <ns2:logoMediaId>99999</ns2:logoMediaId>
              <ns2:videoStartBeaconUrls>http://testtest.videoStartBeaconUrls.co.jp</ns2:videoStartBeaconUrls>
              <ns2:videoStartBeaconUrls>http://testtest.videoStartBeaconUrls2.co.jp</ns2:videoStartBeaconUrls>
              <ns2:video3SecBeaconUrls>http://testtest.video3SecBeaconUrls.co.jp</ns2:video3SecBeaconUrls>
              <ns2:video3SecBeaconUrls>http://testtest.video3SecBeaconUrls2.co.jp</ns2:video3SecBeaconUrls>
              <ns2:videoPaidBeaconUrls>http://testtest.videoPaidBeaconUrls.co.jp</ns2:videoPaidBeaconUrls>
              <ns2:videoPaidBeaconUrls>http://testtest.videoPaidBeaconUrls2.co.jp</ns2:videoPaidBeaconUrls>
              <ns2:videoCompleteBeaconUrls>http://testtest.videoCompleteBeaconUrls.co.jp</ns2:videoCompleteBeaconUrls>
              <ns2:videoCompleteBeaconUrls>http://testtest.videoCompleteBeaconUrls2.co.jp</ns2:videoCompleteBeaconUrls>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10007</ns2:campaignId>
            <ns2:campaignName>test campaign7</ns2:campaignName>
            <ns2:adGroupId>20007</ns2:adGroupId>
            <ns2:adGroupName>test adGroup7</ns2:adGroupName>
            <ns2:adId>30007</ns2:adId>
            <ns2:adName>Set DynamicAd</ns2:adName>
            <ns2:mediaId>1111</ns2:mediaId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED_WITH_REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupAdBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:DynamicAd">
              <ns2:type>DYNAMIC_AD</ns2:type>
              <ns2:url>http://hogehoge.co.jp</ns2:url>
              <ns2:displayUrl>hogehoge.co.jp</ns2:displayUrl>
              <ns2:buttonText>APPLY_NOW</ns2:buttonText>
              <ns2:principal>principal</ns2:principal>
              <ns2:logoMediaId>99991</ns2:logoMediaId>
              <ns2:logoMediaId2>99992</ns2:logoMediaId2>
              <ns2:logoMediaId3>99993</ns2:logoMediaId3>
              <ns2:prefix>pr</ns2:prefix>
              <ns2:suffix>suf</ns2:suffix>
              <ns2:brandColor>#FFFFFF</ns2:brandColor>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)

### リクエスト

広告を削除します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| operations | Yes | [AdGroupAdOperation](../data/AdGroupAd/AdGroupAdOperation.md) |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/AdGroupAd" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201911/AdGroupAd">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1234567890</accountId>
        <operand>
          <accountId>1234567890</accountId>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <adId>2000001</adId>
        </operand>
        <operand>
          <accountId>1234567890</accountId>
          <campaignId>20001</campaignId>
          <adGroupId>30001</adGroupId>
          <adId>3000001</adId>
        </operand>
        <operand>
          <accountId>1234567890</accountId>
          <campaignId>20001</campaignId>
          <adGroupId>30001</adGroupId>
          <adId>3000001</adId>
        </operand>
        <operand>
          <accountId>1234567890</accountId>
          <campaignId>20001</campaignId>
          <adGroupId>30001</adGroupId>
          <adId>3000001</adId>
        </operand>
        <operand>
          <accountId>1234567890</accountId>
          <campaignId>20001</campaignId>
          <adGroupId>30001</adGroupId>
          <adId>3000001</adId>
        </operand>
        <operand>
          <accountId>1234567890</accountId>
          <campaignId>20001</campaignId>
          <adGroupId>30001</adGroupId>
          <adId>3000001</adId>
        </operand>
        <operand>
          <accountId>1234567890</accountId>
          <campaignId>20001</campaignId>
          <adGroupId>30001</adGroupId>
          <adId>3000001</adId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス

| パラメータ | データ型 |
| -------- | ------- |
| rval | [AdGroupAdReturnValue](../data/AdGroupAd/AdGroupAdReturnValue.md) |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/AdGroupAd" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>AdGroupAd</ns2:service>
      <ns2:requestTime>1574393592753</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/AdGroupAd">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupAdReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>test campaign.</ns2:campaignName>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:adGroupName>test adGroup.</ns2:adGroupName>
            <ns2:adId>2000001</ns2:adId>
            <ns2:adName>test ad name</ns2:adName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupAdBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TextAd">
              <ns2:type>TEXT_LONG_AD1</ns2:type>
              <ns2:url>http://testtest.co.jp</ns2:url>
              <ns2:displayUrl>testtest.co.jp</ns2:displayUrl>
              <ns2:headline>headline</ns2:headline>
              <ns2:description>description</ns2:description>
              <ns2:description2>description2</ns2:description2>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>20001</ns2:campaignId>
            <ns2:campaignName>test campaign.</ns2:campaignName>
            <ns2:adGroupId>30001</ns2:adGroupId>
            <ns2:adGroupName>test adGroup.</ns2:adGroupName>
            <ns2:adId>3000001</ns2:adId>
            <ns2:adName>test ad name</ns2:adName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupAdBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:PosAd">
              <ns2:type>POS_AD</ns2:type>
              <ns2:url>http://testtest.co.jp</ns2:url>
              <ns2:description>description</ns2:description>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>20001</ns2:campaignId>
            <ns2:campaignName>test campaign.</ns2:campaignName>
            <ns2:adGroupId>30001</ns2:adGroupId>
            <ns2:adGroupName>test adGroup.</ns2:adGroupName>
            <ns2:adId>3000001</ns2:adId>
            <ns2:adName>test ad name</ns2:adName>
            <ns2:mediaId>1111</ns2:mediaId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupAdBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ResponsiveImageAd">
              <ns2:type>RESPONSIVE_IMAGE_AD</ns2:type>
              <ns2:headline>headline</ns2:headline>
              <ns2:description>description</ns2:description>
              <ns2:url>http://testtest.co.jp</ns2:url>
              <ns2:displayUrl>testtest.co.jp</ns2:displayUrl>
              <ns2:buttonText>APPLY_NOW</ns2:buttonText>
              <ns2:principal>principal</ns2:principal>
              <ns2:logoMediaId>2222</ns2:logoMediaId>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>20001</ns2:campaignId>
            <ns2:campaignName>test campaign.</ns2:campaignName>
            <ns2:adGroupId>30001</ns2:adGroupId>
            <ns2:adGroupName>test adGroup.</ns2:adGroupName>
            <ns2:adId>3000001</ns2:adId>
            <ns2:adName>test ad name</ns2:adName>
            <ns2:mediaId>1111</ns2:mediaId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupAdBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:StaticFrameAd">
              <ns2:type>STATIC_FRAME_AD</ns2:type>
              <ns2:size>300X250</ns2:size>
              <ns2:headline>headline</ns2:headline>
              <ns2:description>description</ns2:description>
              <ns2:url>http://testtest.co.jp</ns2:url>
              <ns2:displayUrl>testtest.co.jp</ns2:displayUrl>
              <ns2:layout>SQUARE_BANNER_TOP</ns2:layout>
              <ns2:buttonText>APPLY_NOW</ns2:buttonText>
              <ns2:principal>principal</ns2:principal>
              <ns2:colorSetId>1000000005</ns2:colorSetId>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>20001</ns2:campaignId>
            <ns2:campaignName>test campaign.</ns2:campaignName>
            <ns2:adGroupId>30001</ns2:adGroupId>
            <ns2:adGroupName>test adGroup.</ns2:adGroupName>
            <ns2:adId>3000001</ns2:adId>
            <ns2:adName>test ad name</ns2:adName>
            <ns2:mediaId>1111</ns2:mediaId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupAdBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:BannerImageAd">
              <ns2:type>BANNER_IMAGE_AD</ns2:type>
              <ns2:url>http://testtest.co.jp</ns2:url>
              <ns2:displayUrl>testtest.co.jp</ns2:displayUrl>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>20001</ns2:campaignId>
            <ns2:campaignName>test campaign.</ns2:campaignName>
            <ns2:adGroupId>30001</ns2:adGroupId>
            <ns2:adGroupName>test adGroup.</ns2:adGroupName>
            <ns2:adId>3000001</ns2:adId>
            <ns2:adName>test ad name</ns2:adName>
            <ns2:mediaId>1111</ns2:mediaId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPVAdGroupAdBid">
              <ns2:type>MANUAL_CPV</ns2:type>
              <ns2:maxCpv>100000</ns2:maxCpv>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ResponsiveVideoAd">
              <ns2:type>RESPONSIVE_VIDEO_AD</ns2:type>
              <ns2:thumbnailMediaId>555555</ns2:thumbnailMediaId>
              <ns2:headline>headline</ns2:headline>
              <ns2:description>description</ns2:description>
              <ns2:url>http://testtest.co.jp</ns2:url>
              <ns2:displayUrl>testtest.co.jp</ns2:displayUrl>
              <ns2:buttonText>APPLY_NOW</ns2:buttonText>
              <ns2:principal>principal</ns2:principal>
              <ns2:logoMediaId>99999</ns2:logoMediaId>
              <ns2:videoStartBeaconUrls>http://testtest.videoStartBeaconUrls.co.jp</ns2:videoStartBeaconUrls>
              <ns2:videoStartBeaconUrls>http://testtest.videoStartBeaconUrls2.co.jp</ns2:videoStartBeaconUrls>
              <ns2:video3SecBeaconUrls>http://testtest.video3SecBeaconUrls.co.jp</ns2:video3SecBeaconUrls>
              <ns2:video3SecBeaconUrls>http://testtest.video3SecBeaconUrls2.co.jp</ns2:video3SecBeaconUrls>
              <ns2:videoPaidBeaconUrls>http://testtest.videoPaidBeaconUrls.co.jp</ns2:videoPaidBeaconUrls>
              <ns2:videoPaidBeaconUrls>http://testtest.videoPaidBeaconUrls2.co.jp</ns2:videoPaidBeaconUrls>
              <ns2:videoCompleteBeaconUrls>http://testtest.videoCompleteBeaconUrls.co.jp</ns2:videoCompleteBeaconUrls>
              <ns2:videoCompleteBeaconUrls>http://testtest.videoCompleteBeaconUrls2.co.jp</ns2:videoCompleteBeaconUrls>
            </ns2:ad>
            <ns2:thirdPartyTrackingScriptUrl>https://testtest.com/</ns2:thirdPartyTrackingScriptUrl>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>20001</ns2:campaignId>
            <ns2:campaignName>test campaign.</ns2:campaignName>
            <ns2:adGroupId>30001</ns2:adGroupId>
            <ns2:adGroupName>test adGroup.</ns2:adGroupName>
            <ns2:adId>3000001</ns2:adId>
            <ns2:adName>DynamicAd</ns2:adName>
            <ns2:mediaId>1111</ns2:mediaId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupAdBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:DynamicAd">
              <ns2:type>DYNAMIC_AD</ns2:type>
              <ns2:url>http://hogehoge.co.jp</ns2:url>
              <ns2:displayUrl>hogehoge.co.jp</ns2:displayUrl>
              <ns2:buttonText>APPLY_NOW</ns2:buttonText>
              <ns2:principal>principal</ns2:principal>
              <ns2:logoMediaId>99991</ns2:logoMediaId>
              <ns2:logoMediaId2>99992</ns2:logoMediaId2>
              <ns2:logoMediaId3>99993</ns2:logoMediaId3>
              <ns2:prefix>pr</ns2:prefix>
              <ns2:suffix>suf</ns2:suffix>
              <ns2:brandColor>#FFFFFF</ns2:brandColor>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

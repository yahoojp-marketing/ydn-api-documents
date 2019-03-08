# AdGroupAdService
Use this service to get, add, update or delete ad information.

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201812/AdGroupAdService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201812/AdGroupAdService?wsdl |

#### Namespace
http://im.yahooapis.jp/V201812/AdGroupAd

#### Service Overview
Retrieves and updates ads.

#### Operation
Explains operations provided by AdGroupAdService.

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)

#### Object
[AdGroupAd](../data/AdGroupAd)

## get

### Request
Retrieves ad information.

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| selector | required | [AdGroupAdSelector](../data/AdGroupAd/AdGroupAdSelector.md) | Contains a set of criteria (parameters) for get method. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/AdGroupAd" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201903/AdGroupAd" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <selector>
        <accountId>1234567890</accountId>
        <campaignIds>10001</campaignIds>
        <campaignIds>10002</campaignIds>
        <campaignIds>10003</campaignIds>
        <campaignIds>10004</campaignIds>
        <campaignIds>10005</campaignIds>
        <adGroupIds>20001</adGroupIds>
        <adGroupIds>20002</adGroupIds>
        <adGroupIds>20003</adGroupIds>
        <adGroupIds>20004</adGroupIds>
        <adGroupIds>20005</adGroupIds>
        <adIds>20001</adIds>
        <adIds>20002</adIds>
        <adIds>20003</adIds>
        <adIds>20004</adIds>
        <adIds>20005</adIds>
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
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [AdGroupAdPage](../data/AdGroupAd/AdGroupAdPage.md) | Contains the results (a list of all entities) for get method. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/AdGroupAd" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>AdGroupAd</ns2:service>
      <ns2:requestTime>1551686137905</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/AdGroupAd">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>AdGroupAdPage</Page.Type>
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
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ResponsiveAd">
              <ns2:type>RESPONSIVE_AD</ns2:type>
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
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:None">
              <ns2:type>NONE</ns2:type>
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
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:VideoAd">
              <ns2:type>VIDEO_AD</ns2:type>
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
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)

### Request
Adds an ad.

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| operations | required | [AdGroupAdOperation](../data/AdGroupAd/AdGroupAdOperation.md) | Contains the information of ad targeted for mutate method operation. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/AdGroupAd" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201903/AdGroupAd">
      <operations>
        <operator>ADD</operator>
        <accountId>1234567890</accountId>
        <operand>
          <accountId>0</accountId>
          <campaignId>100000</campaignId>
          <adGroupId>2000</adGroupId>
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
          <campaignId>22222</campaignId>
          <adGroupId>333333</adGroupId>
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
          <campaignId>44444</campaignId>
          <adGroupId>44444</adGroupId>
          <adName>ResponsiveAd</adName>
          <mediaId>9999</mediaId>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPCAdGroupAdBid">
            <type>MANUAL_CPC</type>
            <maxCpc>100</maxCpc>
          </bid>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ResponsiveAd">
            <type>RESPONSIVE_AD</type>
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
          <campaignId>3333</campaignId>
          <adGroupId>222222</adGroupId>
          <adName>StaticFrameAd</adName>
          <mediaId>300000</mediaId>
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
          <campaignId>19999</campaignId>
          <adGroupId>29999</adGroupId>
          <adName>None</adName>
          <mediaId>480003</mediaId>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPCAdGroupAdBid">
            <type>MANUAL_CPC</type>
            <maxCpc>100</maxCpc>
          </bid>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="None">
            <type>NONE</type>
            <url>http://test.co.jp</url>
            <displayUrl>test.co.jp</displayUrl>
          </ad>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignId>88888</campaignId>
          <adGroupId>7777</adGroupId>
          <adName>VideoAd</adName>
          <mediaId>88812</mediaId>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPVAdGroupAdBid">
            <type>MANUAL_CPV</type>
            <maxCpv>10000</maxCpv>
          </bid>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="VideoAd">
            <type>VIDEO_AD</type>
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
          </ad>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignId>88888</campaignId>
          <adGroupId>7777</adGroupId>
          <adName>DynamicAd</adName>
          <mediaId>88812</mediaId>
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
          </ad>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [AdGroupAdReturnValue](../data/AdGroupAd/AdGroupAdReturnValue.md) | Contains the results (a list of all entities) of mutate method. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/AdGroupAd" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>AdGroupAd</ns2:service>
      <ns2:requestTime>1551686137976</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/AdGroupAd">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupAdReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
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
            <ns2:impressionBeaconUrls>https://test.com/</ns2:impressionBeaconUrls>
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
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ResponsiveAd">
              <ns2:type>RESPONSIVE_AD</ns2:type>
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
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:None">
              <ns2:type>NONE</ns2:type>
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
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:VideoAd">
              <ns2:type>VIDEO_AD</ns2:type>
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

## mutate(SET)

### Request
Updates an ad.

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| operations | required | [AdGroupAdOperation](../data/AdGroupAd/AdGroupAdOperation.md) | Contains the information of ad targeted for mutate method operation. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/AdGroupAd" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201903/AdGroupAd">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <accountId>0</accountId>
          <campaignId>100000</campaignId>
          <adGroupId>2000</adGroupId>
          <adId>2222</adId>
          <adName>TextAd</adName>
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
          <campaignId>22222</campaignId>
          <adGroupId>333333</adGroupId>
          <adId>2223</adId>
          <adName>PosAd</adName>
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
          <campaignId>44444</campaignId>
          <adGroupId>44444</adGroupId>
          <adId>2224</adId>
          <adName>ResponsiveAd</adName>
          <mediaId>9999</mediaId>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPCAdGroupAdBid">
            <maxCpc>100</maxCpc>
          </bid>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ResponsiveAd">
            <type>RESPONSIVE_AD</type>
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
          <campaignId>3333</campaignId>
          <adGroupId>222222</adGroupId>
          <adId>2225</adId>
          <adName>StaticFrameAd</adName>
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
          <campaignId>19999</campaignId>
          <adGroupId>29999</adGroupId>
          <adId>2226</adId>
          <adName>None</adName>
          <mediaId>480003</mediaId>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPCAdGroupAdBid">
            <maxCpc>100</maxCpc>
          </bid>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="None">
            <type>NONE</type>
            <url>http://test.co.jp</url>
            <displayUrl>test.co.jp</displayUrl>
          </ad>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignId>88888</campaignId>
          <adGroupId>7777</adGroupId>
          <adId>2299</adId>
          <adName>VideoAd</adName>
          <mediaId>88812</mediaId>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPVAdGroupAdBid">
            <maxCpv>10000</maxCpv>
          </bid>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="VideoAd">
            <type>VIDEO_AD</type>
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
          </ad>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignId>88888</campaignId>
          <adGroupId>7777</adGroupId>
          <adName>DynamicAd</adName>
          <mediaId>88812</mediaId>
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
          </ad>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [AdGroupAdReturnValue](../data/AdGroupAd/AdGroupAdReturnValue.md) | Contains the results (a list of all entities) of mutate method. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/AdGroupAd" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>AdGroupAd</ns2:service>
      <ns2:requestTime>1551686138045</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/AdGroupAd">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupAdReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
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
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ResponsiveAd">
              <ns2:type>RESPONSIVE_AD</ns2:type>
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
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:None">
              <ns2:type>NONE</ns2:type>
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
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:VideoAd">
              <ns2:type>VIDEO_AD</ns2:type>
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

## mutate(REMOVE)

### Request
Removes an ad.

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| operations | required | [AdGroupAdOperation](../data/AdGroupAd/AdGroupAdOperation.md) | Contains the information of ad targeted for mutate method operation. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/AdGroupAd" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201903/AdGroupAd">
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

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [AdGroupAdReturnValue](../data/AdGroupAd/AdGroupAdReturnValue.md) | Contains the results (a list of all entities) of mutate method. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/AdGroupAd" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>AdGroupAd</ns2:service>
      <ns2:requestTime>1551686138108</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/AdGroupAd">
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
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ResponsiveAd">
              <ns2:type>RESPONSIVE_AD</ns2:type>
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
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:None">
              <ns2:type>NONE</ns2:type>
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
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:VideoAd">
              <ns2:type>VIDEO_AD</ns2:type>
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

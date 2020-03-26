# CampaignService

Use this service to get, add, update, or delete campaigns.

#### WSDL

| environment |                                      url                                      |
| ----------- | ----------------------------------------------------------------------------- |
| production  | https://location.im.yahooapis.jp/services/V201911/CampaignService?wsdl |
| sandbox     | https://sandbox.im.yahooapis.jp/services/V201911/CampaignService?wsdl  |

#### Namespace

http://im.yahooapis.jp/V201911/Campaign

#### Service Overview

Offers campaign operation.

##### ■Tips
See the following Best Practice to learn about how to create a campaign on Display Ads (Auction).  
[Create a campaign by objective on Display Ads (Auction)(V201911 only)](../../bestpractice/display_ads_campaign.md)


#### Operation

Explains operations provided by CampaignService.

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)

## get

### Request

Gets information related to campaigns.

| Parameter | Required | Data Type |
| --------- | -------- | --------- |
| selector | Yes | [CampaignSelector](../data/Campaign/CampaignSelector.md) |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/Campaign" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201911/Campaign" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <selector>
        <accountId>1234567890</accountId>
        <campaignIds>10001</campaignIds>
        <campaignIds>10002</campaignIds>
        <campaignIds>10003</campaignIds>
        <campaignIds>10004</campaignIds>
        <campaignIds>10005</campaignIds>
        <labelIds>3000</labelIds>
        <labelIds>3001</labelIds>
        <containsLabelIdFlg>true</containsLabelIdFlg>
        <userStatus>ACTIVE</userStatus>
        <userStatus>PAUSED</userStatus>
        <feedHolderIds>1001</feedHolderIds>
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

### Response

| Parameter | Data Type |
| -------- | ------- |
| rval | [CampaignPage](../data/Campaign/CampaignPage.md) |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/Campaign" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>Campaign</ns2:service>
      <ns2:requestTime>1574393678860</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/Campaign">
      <ns2:rval>
        <totalNumEntries>5</totalNumEntries>
        <Page.Type>CampaignPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>Standard Campaign.</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20371231</ns2:endDate>
            <ns2:budget>
              <ns2:amount>10000</ns2:amount>
              <ns2:deliveryMethod>STANDARD</ns2:deliveryMethod>
            </ns2:budget>
            <ns2:biddingStrategy xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPC">
              <ns2:type>MANUAL_CPC</ns2:type>
            </ns2:biddingStrategy>
            <ns2:adProductType>TARGET_MATCH</ns2:adProductType>
            <ns2:frequencyCap>
              <ns2:level>CAMPAIGN</ns2:level>
              <ns2:timeUnit>DAY</ns2:timeUnit>
              <ns2:impression>15</ns2:impression>
            </ns2:frequencyCap>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCampaignConversionOptimizer">
              <ns2:optimizerType>MANUAL</ns2:optimizerType>
              <ns2:eligibilityFlg>DISABLE</ns2:eligibilityFlg>
            </ns2:conversionOptimizer>
            <ns2:campaignType>STANDARD</ns2:campaignType>
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
            <ns2:campaignGoal>NONE</ns2:campaignGoal>
            <ns2:campaignBiddingStrategy>
              <ns2:type>NONE</ns2:type>
            </ns2:campaignBiddingStrategy>
          </ns2:campaign>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10002</ns2:campaignId>
            <ns2:campaignName>APP Campaign.</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20371231</ns2:endDate>
            <ns2:budget>
              <ns2:amount>10000</ns2:amount>
              <ns2:deliveryMethod>STANDARD</ns2:deliveryMethod>
            </ns2:budget>
            <ns2:biddingStrategy xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPC">
              <ns2:type>MANUAL_CPC</ns2:type>
            </ns2:biddingStrategy>
            <ns2:adProductType>TARGET_MATCH</ns2:adProductType>
            <ns2:frequencyCap>
              <ns2:level>CAMPAIGN</ns2:level>
              <ns2:timeUnit>DAY</ns2:timeUnit>
              <ns2:impression>15</ns2:impression>
            </ns2:frequencyCap>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCampaignConversionOptimizer">
              <ns2:optimizerType>MANUAL</ns2:optimizerType>
              <ns2:eligibilityFlg>DISABLE</ns2:eligibilityFlg>
            </ns2:conversionOptimizer>
            <ns2:campaignType>APP</ns2:campaignType>
            <ns2:appName>TestAppName</ns2:appName>
            <ns2:appId>jp.co.yahoo</ns2:appId>
            <ns2:appOs>ANDROID</ns2:appOs>
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
            <ns2:campaignGoal>NONE</ns2:campaignGoal>
            <ns2:campaignBiddingStrategy>
              <ns2:type>NONE</ns2:type>
            </ns2:campaignBiddingStrategy>
          </ns2:campaign>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10003</ns2:campaignId>
            <ns2:campaignName>Movie Campaign.</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20371231</ns2:endDate>
            <ns2:budget>
              <ns2:amount>10000</ns2:amount>
              <ns2:deliveryMethod>ACCELERATED</ns2:deliveryMethod>
            </ns2:budget>
            <ns2:biddingStrategy xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPV">
              <ns2:type>MANUAL_CPV</ns2:type>
            </ns2:biddingStrategy>
            <ns2:adProductType>VIDEO_AD</ns2:adProductType>
            <ns2:frequencyCap>
              <ns2:level>CAMPAIGN</ns2:level>
              <ns2:timeUnit>DAY</ns2:timeUnit>
              <ns2:impression>15</ns2:impression>
            </ns2:frequencyCap>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AutoCampaignConversionOptimizer">
              <ns2:optimizerType>AUTO</ns2:optimizerType>
              <ns2:targetCpa>100</ns2:targetCpa>
              <ns2:eligibilityFlg>DISABLE</ns2:eligibilityFlg>
            </ns2:conversionOptimizer>
            <ns2:campaignType>STANDARD</ns2:campaignType>
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
            <ns2:campaignGoal>NONE</ns2:campaignGoal>
            <ns2:campaignBiddingStrategy>
              <ns2:type>NONE</ns2:type>
            </ns2:campaignBiddingStrategy>
          </ns2:campaign>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10004</ns2:campaignId>
            <ns2:campaignName>DynamicAds Campaign.</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20371231</ns2:endDate>
            <ns2:budget>
              <ns2:amount>10000</ns2:amount>
              <ns2:deliveryMethod>STANDARD</ns2:deliveryMethod>
            </ns2:budget>
            <ns2:biddingStrategy xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPC">
              <ns2:type>MANUAL_CPC</ns2:type>
            </ns2:biddingStrategy>
            <ns2:adProductType>DYNAMIC_ADS</ns2:adProductType>
            <ns2:frequencyCap>
              <ns2:level>CAMPAIGN</ns2:level>
              <ns2:timeUnit>DAY</ns2:timeUnit>
              <ns2:impression>15</ns2:impression>
            </ns2:frequencyCap>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCampaignConversionOptimizer">
              <ns2:optimizerType>MANUAL</ns2:optimizerType>
              <ns2:eligibilityFlg>DISABLE</ns2:eligibilityFlg>
            </ns2:conversionOptimizer>
            <ns2:campaignType>STANDARD</ns2:campaignType>
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
            <ns2:feedHolderId>1001</ns2:feedHolderId>
            <ns2:campaignGoal>NONE</ns2:campaignGoal>
            <ns2:campaignBiddingStrategy>
              <ns2:type>NONE</ns2:type>
            </ns2:campaignBiddingStrategy>
          </ns2:campaign>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10005</ns2:campaignId>
            <ns2:campaignName>Campaign with campaignGoal (WEBSITE_TRAFFIC)</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20371231</ns2:endDate>
            <ns2:budget>
              <ns2:deliveryMethod>ACCELERATED</ns2:deliveryMethod>
            </ns2:budget>
            <ns2:campaignType>STANDARD</ns2:campaignType>
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
            <ns2:campaignGoal>WEBSITE_TRAFFIC</ns2:campaignGoal>
            <ns2:campaignBiddingStrategy>
              <ns2:type>MAX_VCPM</ns2:type>
              <ns2:maxVcpmBidValue>1000</ns2:maxVcpmBidValue>
            </ns2:campaignBiddingStrategy>
            <ns2:viewableFrequencyCap>
              <ns2:level>CAMPAIGN</ns2:level>
              <ns2:timeUnit>DAY</ns2:timeUnit>
              <ns2:vImps>10</ns2:vImps>
            </ns2:viewableFrequencyCap>
          </ns2:campaign>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)

### Request

Adds campaign information.

| Parameter | Required | Data Type |
| --------- | -------- | --------- |
| operations | Yes | [CampaignOperation](../data/Campaign/CampaignOperation.md) |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/Campaign" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201911/Campaign">
      <operations>
        <operator>ADD</operator>
        <accountId>1234567890</accountId>
        <operand>
          <accountId>0</accountId>
          <campaignName>Standard Campaign</campaignName>
          <userStatus>ACTIVE</userStatus>
          <startDate>20170101</startDate>
          <endDate>20371231</endDate>
          <budget>
            <amount>10000</amount>
            <deliveryMethod>STANDARD</deliveryMethod>
          </budget>
          <adProductType>TARGET_MATCH</adProductType>
          <frequencyCap>
            <level>CAMPAIGN</level>
            <timeUnit>DAY</timeUnit>
            <impression>15</impression>
          </frequencyCap>
          <campaignType>STANDARD</campaignType>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignName>App Campaign</campaignName>
          <userStatus>ACTIVE</userStatus>
          <startDate>20170101</startDate>
          <endDate>20371231</endDate>
          <budget>
            <amount>10000</amount>
            <deliveryMethod>STANDARD</deliveryMethod>
          </budget>
          <adProductType>TARGET_MATCH</adProductType>
          <campaignType>APP</campaignType>
          <appName>TestApp</appName>
          <appId>201607221800792</appId>
          <appOs>ANDROID</appOs>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignName>Video Campaign.</campaignName>
          <userStatus>ACTIVE</userStatus>
          <startDate>20170101</startDate>
          <endDate>20371231</endDate>
          <budget>
            <deliveryMethod>ACCELERATED</deliveryMethod>
          </budget>
          <adProductType>VIDEO_AD</adProductType>
          <campaignType>STANDARD</campaignType>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignName>DynamicAds Campaign</campaignName>
          <userStatus>ACTIVE</userStatus>
          <startDate>20170101</startDate>
          <endDate>20371231</endDate>
          <budget>
            <amount>10000</amount>
            <deliveryMethod>STANDARD</deliveryMethod>
          </budget>
          <adProductType>DYNAMIC_ADS</adProductType>
          <frequencyCap>
            <level>CAMPAIGN</level>
            <timeUnit>DAY</timeUnit>
            <impression>15</impression>
          </frequencyCap>
          <campaignType>STANDARD</campaignType>
          <feedHolderId>1001</feedHolderId>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignName>Campaign with campaignGoal (WEBSITE_TRAFFIC)</campaignName>
          <userStatus>ACTIVE</userStatus>
          <startDate>20170101</startDate>
          <endDate>20371231</endDate>
          <budget>
            <deliveryMethod>ACCELERATED</deliveryMethod>
          </budget>
          <campaignGoal>WEBSITE_TRAFFIC</campaignGoal>
          <campaignBiddingStrategy>
            <type>MAX_VCPM</type>
            <maxVcpmBidValue>1000</maxVcpmBidValue>
          </campaignBiddingStrategy>
          <viewableFrequencyCap>
            <level>CAMPAIGN</level>
            <timeUnit>DAY</timeUnit>
            <vImps>10</vImps>
          </viewableFrequencyCap>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

| Parameter | Data Type |
| -------- | ------- |
| rval | [CampaignReturnValue](../data/Campaign/CampaignReturnValue.md) |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/Campaign" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>Campaign</ns2:service>
      <ns2:requestTime>1574393678927</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/Campaign">
      <ns2:rval>
        <ListReturnValue.Type>CampaignReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>Standard Campaign.</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20371231</ns2:endDate>
            <ns2:budget>
              <ns2:amount>10000</ns2:amount>
              <ns2:deliveryMethod>STANDARD</ns2:deliveryMethod>
            </ns2:budget>
            <ns2:biddingStrategy xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPC">
              <ns2:type>MANUAL_CPC</ns2:type>
            </ns2:biddingStrategy>
            <ns2:adProductType>TARGET_MATCH</ns2:adProductType>
            <ns2:frequencyCap>
              <ns2:level>CAMPAIGN</ns2:level>
              <ns2:timeUnit>DAY</ns2:timeUnit>
              <ns2:impression>15</ns2:impression>
            </ns2:frequencyCap>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCampaignConversionOptimizer">
              <ns2:optimizerType>MANUAL</ns2:optimizerType>
              <ns2:eligibilityFlg>DISABLE</ns2:eligibilityFlg>
            </ns2:conversionOptimizer>
            <ns2:campaignType>STANDARD</ns2:campaignType>
            <ns2:campaignGoal>NONE</ns2:campaignGoal>
          </ns2:campaign>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>APP Campaign.</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20371231</ns2:endDate>
            <ns2:budget>
              <ns2:amount>10000</ns2:amount>
              <ns2:deliveryMethod>STANDARD</ns2:deliveryMethod>
            </ns2:budget>
            <ns2:biddingStrategy xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPC">
              <ns2:type>MANUAL_CPC</ns2:type>
            </ns2:biddingStrategy>
            <ns2:adProductType>TARGET_MATCH</ns2:adProductType>
            <ns2:frequencyCap>
              <ns2:level>CAMPAIGN</ns2:level>
              <ns2:timeUnit>DAY</ns2:timeUnit>
              <ns2:impression>15</ns2:impression>
            </ns2:frequencyCap>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCampaignConversionOptimizer">
              <ns2:optimizerType>MANUAL</ns2:optimizerType>
              <ns2:eligibilityFlg>DISABLE</ns2:eligibilityFlg>
            </ns2:conversionOptimizer>
            <ns2:campaignType>APP</ns2:campaignType>
            <ns2:appName>TestAppName</ns2:appName>
            <ns2:appId>jp.co.yahoo</ns2:appId>
            <ns2:appOs>ANDROID</ns2:appOs>
            <ns2:campaignGoal>NONE</ns2:campaignGoal>
          </ns2:campaign>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>Movie Campaign.</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20371231</ns2:endDate>
            <ns2:budget>
              <ns2:amount>10000</ns2:amount>
              <ns2:deliveryMethod>ACCELERATED</ns2:deliveryMethod>
            </ns2:budget>
            <ns2:biddingStrategy xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPV">
              <ns2:type>MANUAL_CPV</ns2:type>
            </ns2:biddingStrategy>
            <ns2:adProductType>VIDEO_AD</ns2:adProductType>
            <ns2:frequencyCap>
              <ns2:level>CAMPAIGN</ns2:level>
              <ns2:timeUnit>DAY</ns2:timeUnit>
              <ns2:impression>15</ns2:impression>
            </ns2:frequencyCap>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AutoCampaignConversionOptimizer">
              <ns2:optimizerType>AUTO</ns2:optimizerType>
              <ns2:targetCpa>100</ns2:targetCpa>
              <ns2:eligibilityFlg>DISABLE</ns2:eligibilityFlg>
            </ns2:conversionOptimizer>
            <ns2:campaignType>STANDARD</ns2:campaignType>
            <ns2:campaignGoal>NONE</ns2:campaignGoal>
          </ns2:campaign>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>DynamicAds Campaign.</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20371231</ns2:endDate>
            <ns2:budget>
              <ns2:amount>10000</ns2:amount>
              <ns2:deliveryMethod>STANDARD</ns2:deliveryMethod>
            </ns2:budget>
            <ns2:biddingStrategy xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPC">
              <ns2:type>MANUAL_CPC</ns2:type>
            </ns2:biddingStrategy>
            <ns2:adProductType>DYNAMIC_ADS</ns2:adProductType>
            <ns2:frequencyCap>
              <ns2:level>CAMPAIGN</ns2:level>
              <ns2:timeUnit>DAY</ns2:timeUnit>
              <ns2:impression>15</ns2:impression>
            </ns2:frequencyCap>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCampaignConversionOptimizer">
              <ns2:optimizerType>MANUAL</ns2:optimizerType>
              <ns2:eligibilityFlg>DISABLE</ns2:eligibilityFlg>
            </ns2:conversionOptimizer>
            <ns2:campaignType>STANDARD</ns2:campaignType>
            <ns2:feedHolderId>1001</ns2:feedHolderId>
            <ns2:campaignGoal>NONE</ns2:campaignGoal>
          </ns2:campaign>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>Campaign with campaignGoal (WEBSITE_TRAFFIC)</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20371231</ns2:endDate>
            <ns2:budget>
              <ns2:deliveryMethod>ACCELERATED</ns2:deliveryMethod>
            </ns2:budget>
            <ns2:campaignType>STANDARD</ns2:campaignType>
            <ns2:campaignGoal>WEBSITE_TRAFFIC</ns2:campaignGoal>
            <ns2:campaignBiddingStrategy>
              <ns2:type>MAX_VCPM</ns2:type>
              <ns2:maxVcpmBidValue>1000</ns2:maxVcpmBidValue>
            </ns2:campaignBiddingStrategy>
            <ns2:viewableFrequencyCap>
              <ns2:level>CAMPAIGN</ns2:level>
              <ns2:timeUnit>DAY</ns2:timeUnit>
              <ns2:vImps>10</ns2:vImps>
            </ns2:viewableFrequencyCap>
          </ns2:campaign>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)

### Request

Updates campaign information.

| Parameter | Required | Data Type |
| --------- | -------- | --------- |
| operations | Yes | [CampaignOperation](../data/Campaign/CampaignOperation.md) |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/Campaign" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201911/Campaign">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <accountId>0</accountId>
          <campaignId>10001</campaignId>
          <campaignName>set Standard Campaign</campaignName>
          <userStatus>ACTIVE</userStatus>
          <endDate>20301231</endDate>
          <budget>
            <amount>20000</amount>
          </budget>
          <frequencyCap>
            <level>CAMPAIGN</level>
            <timeUnit>DAY</timeUnit>
            <impression>20</impression>
          </frequencyCap>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignId>10002</campaignId>
          <campaignName>set Video Campaign</campaignName>
          <userStatus>ACTIVE</userStatus>
          <endDate>20301231</endDate>
          <budget>
            <amount>20000</amount>
          </budget>
          <conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AutoCampaignConversionOptimizer">
            <optimizerType>AUTO</optimizerType>
            <targetCpa>1</targetCpa>
          </conversionOptimizer>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignId>10003</campaignId>
          <campaignBiddingStrategy>
            <type>MAX_VCPM</type>
            <maxVcpmBidValue>1000</maxVcpmBidValue>
          </campaignBiddingStrategy>
          <viewableFrequencyCap>
            <level>CAMPAIGN</level>
            <timeUnit>DAY</timeUnit>
            <vImps>10</vImps>
          </viewableFrequencyCap>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

| Parameter | Data Type |
| -------- | ------- |
| rval | [CampaignReturnValue](../data/Campaign/CampaignReturnValue.md) |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/Campaign" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>Campaign</ns2:service>
      <ns2:requestTime>1574393678978</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/Campaign">
      <ns2:rval>
        <ListReturnValue.Type>CampaignReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>set Standard Campaign</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20301231</ns2:endDate>
            <ns2:budget>
              <ns2:amount>20000</ns2:amount>
              <ns2:deliveryMethod>STANDARD</ns2:deliveryMethod>
            </ns2:budget>
            <ns2:biddingStrategy xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPC">
              <ns2:type>MANUAL_CPC</ns2:type>
            </ns2:biddingStrategy>
            <ns2:adProductType>TARGET_MATCH</ns2:adProductType>
            <ns2:frequencyCap>
              <ns2:level>CAMPAIGN</ns2:level>
              <ns2:timeUnit>DAY</ns2:timeUnit>
              <ns2:impression>20</ns2:impression>
            </ns2:frequencyCap>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCampaignConversionOptimizer">
              <ns2:optimizerType>MANUAL</ns2:optimizerType>
              <ns2:eligibilityFlg>DISABLE</ns2:eligibilityFlg>
            </ns2:conversionOptimizer>
            <ns2:campaignType>STANDARD</ns2:campaignType>
            <ns2:campaignGoal>NONE</ns2:campaignGoal>
          </ns2:campaign>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10002</ns2:campaignId>
            <ns2:campaignName>set Video Campaign</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20301231</ns2:endDate>
            <ns2:budget>
              <ns2:amount>20000</ns2:amount>
              <ns2:deliveryMethod>ACCELERATED</ns2:deliveryMethod>
            </ns2:budget>
            <ns2:biddingStrategy xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPV">
              <ns2:type>MANUAL_CPV</ns2:type>
            </ns2:biddingStrategy>
            <ns2:adProductType>VIDEO_AD</ns2:adProductType>
            <ns2:frequencyCap>
              <ns2:level>CAMPAIGN</ns2:level>
              <ns2:timeUnit>DAY</ns2:timeUnit>
              <ns2:impression>15</ns2:impression>
            </ns2:frequencyCap>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AutoCampaignConversionOptimizer">
              <ns2:optimizerType>AUTO</ns2:optimizerType>
              <ns2:targetCpa>1</ns2:targetCpa>
              <ns2:eligibilityFlg>DISABLE</ns2:eligibilityFlg>
            </ns2:conversionOptimizer>
            <ns2:campaignType>STANDARD</ns2:campaignType>
            <ns2:campaignGoal>NONE</ns2:campaignGoal>
          </ns2:campaign>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10003</ns2:campaignId>
            <ns2:campaignName>set Campaign with campaignGoal (WEBSITE_TRAFFIC)</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20371231</ns2:endDate>
            <ns2:budget>
              <ns2:deliveryMethod>ACCELERATED</ns2:deliveryMethod>
            </ns2:budget>
            <ns2:campaignType>STANDARD</ns2:campaignType>
            <ns2:campaignGoal>WEBSITE_TRAFFIC</ns2:campaignGoal>
            <ns2:campaignBiddingStrategy>
              <ns2:type>MAX_VCPM</ns2:type>
              <ns2:maxVcpmBidValue>1000</ns2:maxVcpmBidValue>
            </ns2:campaignBiddingStrategy>
            <ns2:viewableFrequencyCap>
              <ns2:level>CAMPAIGN</ns2:level>
              <ns2:timeUnit>DAY</ns2:timeUnit>
              <ns2:vImps>10</ns2:vImps>
            </ns2:viewableFrequencyCap>
          </ns2:campaign>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)

### Request

Deletes campaign information.

| Parameter | Required | Data Type |
| --------- | -------- | --------- |
| operations | Yes | [CampaignOperation](../data/Campaign/CampaignOperation.md) |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/Campaign" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201911/Campaign">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1234567890</accountId>
        <operand>
          <accountId>0</accountId>
          <campaignId>10001</campaignId>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignId>10002</campaignId>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignId>10003</campaignId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

| Parameter | Data Type |
| -------- | ------- |
| rval | [CampaignReturnValue](../data/Campaign/CampaignReturnValue.md) |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/Campaign" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>Campaign</ns2:service>
      <ns2:requestTime>1574393679034</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/Campaign">
      <ns2:rval>
        <ListReturnValue.Type>CampaignReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>Standard Campaign.</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20371231</ns2:endDate>
            <ns2:budget>
              <ns2:amount>10000</ns2:amount>
              <ns2:deliveryMethod>STANDARD</ns2:deliveryMethod>
            </ns2:budget>
            <ns2:biddingStrategy xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPC">
              <ns2:type>MANUAL_CPC</ns2:type>
            </ns2:biddingStrategy>
            <ns2:adProductType>TARGET_MATCH</ns2:adProductType>
            <ns2:frequencyCap>
              <ns2:level>CAMPAIGN</ns2:level>
              <ns2:timeUnit>DAY</ns2:timeUnit>
              <ns2:impression>15</ns2:impression>
            </ns2:frequencyCap>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCampaignConversionOptimizer">
              <ns2:optimizerType>MANUAL</ns2:optimizerType>
              <ns2:eligibilityFlg>DISABLE</ns2:eligibilityFlg>
            </ns2:conversionOptimizer>
            <ns2:campaignType>STANDARD</ns2:campaignType>
          </ns2:campaign>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10002</ns2:campaignId>
            <ns2:campaignName>APP Campaign.</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20371231</ns2:endDate>
            <ns2:budget>
              <ns2:amount>10000</ns2:amount>
              <ns2:deliveryMethod>STANDARD</ns2:deliveryMethod>
            </ns2:budget>
            <ns2:biddingStrategy xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPC">
              <ns2:type>MANUAL_CPC</ns2:type>
            </ns2:biddingStrategy>
            <ns2:adProductType>TARGET_MATCH</ns2:adProductType>
            <ns2:frequencyCap>
              <ns2:level>CAMPAIGN</ns2:level>
              <ns2:timeUnit>DAY</ns2:timeUnit>
              <ns2:impression>15</ns2:impression>
            </ns2:frequencyCap>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCampaignConversionOptimizer">
              <ns2:optimizerType>MANUAL</ns2:optimizerType>
              <ns2:eligibilityFlg>DISABLE</ns2:eligibilityFlg>
            </ns2:conversionOptimizer>
            <ns2:campaignType>APP</ns2:campaignType>
            <ns2:appName>TestAppName</ns2:appName>
            <ns2:appId>jp.co.yahoo</ns2:appId>
            <ns2:appOs>ANDROID</ns2:appOs>
          </ns2:campaign>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10003</ns2:campaignId>
            <ns2:campaignName>Movie Campaign.</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20371231</ns2:endDate>
            <ns2:budget>
              <ns2:amount>10000</ns2:amount>
              <ns2:deliveryMethod>ACCELERATED</ns2:deliveryMethod>
            </ns2:budget>
            <ns2:biddingStrategy xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPV">
              <ns2:type>MANUAL_CPV</ns2:type>
            </ns2:biddingStrategy>
            <ns2:adProductType>VIDEO_AD</ns2:adProductType>
            <ns2:frequencyCap>
              <ns2:level>CAMPAIGN</ns2:level>
              <ns2:timeUnit>DAY</ns2:timeUnit>
              <ns2:impression>15</ns2:impression>
            </ns2:frequencyCap>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AutoCampaignConversionOptimizer">
              <ns2:optimizerType>AUTO</ns2:optimizerType>
              <ns2:targetCpa>100</ns2:targetCpa>
              <ns2:eligibilityFlg>DISABLE</ns2:eligibilityFlg>
            </ns2:conversionOptimizer>
            <ns2:campaignType>STANDARD</ns2:campaignType>
          </ns2:campaign>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

# AdGroupService

AdGroupServiceは広告グループの操作を提供します。

#### WSDL

| environment |                                      url                                      |
| ----------- | ----------------------------------------------------------------------------- |
| production  | https://location.im.yahooapis.jp/services/V201911/AdGroupService?wsdl |
| sandbox     | https://sandbox.im.yahooapis.jp/services/V201911/AdGroupService?wsdl  |

#### Namespace

http://im.yahooapis.jp/V201911/AdGroup

#### Service Overview

広告グループの情報取得と更新を行います。

#### Operation

AdGroupServiceで提供される操作を説明します。

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)

## get

### リクエスト

広告グループの情報を取得します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| selector | Yes | [AdGroupSelector](../data/AdGroup/AdGroupSelector.md) |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/AdGroup" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201911/AdGroup" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <selector>
        <accountId>1234567890</accountId>
        <campaignIds>10001</campaignIds>
        <campaignIds>10002</campaignIds>
        <campaignIds>10003</campaignIds>
        <campaignIds>10004</campaignIds>
        <adGroupIds>20001</adGroupIds>
        <adGroupIds>20002</adGroupIds>
        <adGroupIds>20003</adGroupIds>
        <adGroupIds>20004</adGroupIds>
        <labelIds>3000</labelIds>
        <labelIds>3001</labelIds>
        <containsLabelIdFlg>true</containsLabelIdFlg>
        <userStatuses>ACTIVE</userStatuses>
        <userStatuses>PAUSED</userStatuses>
        <feedSetIds>1000</feedSetIds>
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
| rval | [AdGroupPage](../data/AdGroup/AdGroupPage.md) |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/AdGroup" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>AdGroup</ns2:service>
      <ns2:requestTime>1574393614375</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/AdGroup">
      <ns2:rval>
        <totalNumEntries>4</totalNumEntries>
        <Page.Type>AdGroupPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroup>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>test campaign.</ns2:campaignName>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:adGroupName>test adGroup.</ns2:adGroupName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualAdGroupConversionOptimizer">
              <ns2:optimizerType>MANUAL</ns2:optimizerType>
              <ns2:eligibilityFlg>DISABLE</ns2:eligibilityFlg>
            </ns2:conversionOptimizer>
            <ns2:device>DESKTOP</ns2:device>
            <ns2:dynamicImageExtensions>ACTIVE</ns2:dynamicImageExtensions>
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
            <ns2:feedSetId>1000</ns2:feedSetId>
            <ns2:adGroupBiddingStrategy>
              <ns2:campaignBiddingStrategyType>NONE</ns2:campaignBiddingStrategyType>
            </ns2:adGroupBiddingStrategy>
          </ns2:adGroup>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroup>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10002</ns2:campaignId>
            <ns2:campaignName>test campaign.</ns2:campaignName>
            <ns2:adGroupId>20002</ns2:adGroupId>
            <ns2:adGroupName>test app adGroup.</ns2:adGroupName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AutoAdGroupConversionOptimizer">
              <ns2:optimizerType>AUTO</ns2:optimizerType>
              <ns2:targetCpa>1000</ns2:targetCpa>
            </ns2:conversionOptimizer>
            <ns2:device>TABLET</ns2:device>
            <ns2:deviceApp>APP</ns2:deviceApp>
            <ns2:deviceOs>ANDROID</ns2:deviceOs>
            <ns2:smartDeviceCarriers>DOCOMO</ns2:smartDeviceCarriers>
            <ns2:deviceOsVersion>[8.0]</ns2:deviceOsVersion>
            <ns2:dynamicImageExtensions>ACTIVE</ns2:dynamicImageExtensions>
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
            <ns2:feedSetId>1000</ns2:feedSetId>
            <ns2:adGroupBiddingStrategy>
              <ns2:campaignBiddingStrategyType>NONE</ns2:campaignBiddingStrategyType>
            </ns2:adGroupBiddingStrategy>
          </ns2:adGroup>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroup>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10003</ns2:campaignId>
            <ns2:campaignName>test campaign.</ns2:campaignName>
            <ns2:adGroupId>20003</ns2:adGroupId>
            <ns2:adGroupName>test video adGroup.</ns2:adGroupName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPVAdGroupBid">
              <ns2:type>MANUAL_CPV</ns2:type>
              <ns2:maxCpv>100</ns2:maxCpv>
            </ns2:bid>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:NoneAdGroupConversionOptimizer">
              <ns2:optimizerType>NONE</ns2:optimizerType>
            </ns2:conversionOptimizer>
            <ns2:device>SMARTPHONE</ns2:device>
            <ns2:deviceApp>APP</ns2:deviceApp>
            <ns2:deviceOs>ANDROID</ns2:deviceOs>
            <ns2:smartDeviceCarriers>NONE</ns2:smartDeviceCarriers>
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
            <ns2:feedSetId>1000</ns2:feedSetId>
            <ns2:adGroupBiddingStrategy>
              <ns2:campaignBiddingStrategyType>MAX_VCPM</ns2:campaignBiddingStrategyType>
              <ns2:maxVcpmBidValue>50</ns2:maxVcpmBidValue>
            </ns2:adGroupBiddingStrategy>
          </ns2:adGroup>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroup>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10004</ns2:campaignId>
            <ns2:campaignName>test dynamic_ads campaign.</ns2:campaignName>
            <ns2:adGroupId>20004</ns2:adGroupId>
            <ns2:adGroupName>test dynamic_ads adGroup.</ns2:adGroupName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualAdGroupConversionOptimizer">
              <ns2:optimizerType>MANUAL</ns2:optimizerType>
              <ns2:eligibilityFlg>DISABLE</ns2:eligibilityFlg>
            </ns2:conversionOptimizer>
            <ns2:device>DESKTOP</ns2:device>
            <ns2:dynamicImageExtensions>ACTIVE</ns2:dynamicImageExtensions>
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
            <ns2:feedSetId>1000</ns2:feedSetId>
            <ns2:adGroupBiddingStrategy>
              <ns2:campaignBiddingStrategyType>MAX_CPC</ns2:campaignBiddingStrategyType>
            </ns2:adGroupBiddingStrategy>
          </ns2:adGroup>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)

### リクエスト

広告グループを追加します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| operations | Yes | [AdGroupOperation](../data/AdGroup/AdGroupOperation.md) |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/AdGroup" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201911/AdGroup">
      <operations>
        <operator>ADD</operator>
        <accountId>1234567890</accountId>
        <operand>
          <accountId>1234567890</accountId>
          <campaignId>10001</campaignId>
          <adGroupName>test adGroup.</adGroupName>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPCAdGroupBid">
            <type>MANUAL_CPC</type>
            <maxCpc>100</maxCpc>
          </bid>
          <conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualAdGroupConversionOptimizer">
            <optimizerType>MANUAL</optimizerType>
          </conversionOptimizer>
          <device>DESKTOP</device>
          <dynamicImageExtensions>ACTIVE</dynamicImageExtensions>
        </operand>
        <operand>
          <accountId>1234567890</accountId>
          <campaignId>10001</campaignId>
          <adGroupName>test app adGroup.</adGroupName>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPCAdGroupBid">
            <type>MANUAL_CPC</type>
            <maxCpc>100</maxCpc>
          </bid>
          <conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AutoAdGroupConversionOptimizer">
            <optimizerType>AUTO</optimizerType>
            <targetCpa>1000</targetCpa>
          </conversionOptimizer>
          <device>TABLET</device>
          <device>SMARTPHONE</device>
          <deviceApp>APP</deviceApp>
          <deviceOs>ANDROID</deviceOs>
          <deviceOs>IOS</deviceOs>
          <smartDeviceCarriers>DOCOMO</smartDeviceCarriers>
          <smartDeviceCarriers>YMOBILE</smartDeviceCarriers>
          <dynamicImageExtensions>ACTIVE</dynamicImageExtensions>
        </operand>
        <operand>
          <accountId>1234567890</accountId>
          <campaignId>10001</campaignId>
          <adGroupName>test video adGroup.</adGroupName>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPVAdGroupBid">
            <type>MANUAL_CPV</type>
            <maxCpv>100</maxCpv>
          </bid>
          <device>SMARTPHONE</device>
          <deviceApp>APP</deviceApp>
          <deviceOs>ANDROID</deviceOs>
        </operand>
        <operand>
          <accountId>1234567890</accountId>
          <campaignId>10002</campaignId>
          <adGroupName>test adGroup with campaignGoal.</adGroupName>
          <userStatus>ACTIVE</userStatus>
          <conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualAdGroupConversionOptimizer">
            <optimizerType>MANUAL</optimizerType>
          </conversionOptimizer>
          <device>DESKTOP</device>
          <feedSetId>1000</feedSetId>
          <adGroupBiddingStrategy>
            <maxVcpmBidValue>1000</maxVcpmBidValue>
          </adGroupBiddingStrategy>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス

| パラメータ | データ型 |
| -------- | ------- |
| rval | [AdGroupReturnValue](../data/AdGroup/AdGroupReturnValue.md) |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/AdGroup" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>AdGroup</ns2:service>
      <ns2:requestTime>1574393614521</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/AdGroup">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroup>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>test campaign.</ns2:campaignName>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:adGroupName>test adGroup.</ns2:adGroupName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualAdGroupConversionOptimizer">
              <ns2:optimizerType>MANUAL</ns2:optimizerType>
              <ns2:eligibilityFlg>DISABLE</ns2:eligibilityFlg>
            </ns2:conversionOptimizer>
            <ns2:device>DESKTOP</ns2:device>
            <ns2:dynamicImageExtensions>ACTIVE</ns2:dynamicImageExtensions>
            <ns2:adGroupBiddingStrategy>
              <ns2:campaignBiddingStrategyType>NONE</ns2:campaignBiddingStrategyType>
            </ns2:adGroupBiddingStrategy>
          </ns2:adGroup>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroup>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>test campaign.</ns2:campaignName>
            <ns2:adGroupId>20002</ns2:adGroupId>
            <ns2:adGroupName>test app adGroup.</ns2:adGroupName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AutoAdGroupConversionOptimizer">
              <ns2:optimizerType>AUTO</ns2:optimizerType>
              <ns2:targetCpa>1000</ns2:targetCpa>
            </ns2:conversionOptimizer>
            <ns2:device>TABLET</ns2:device>
            <ns2:deviceApp>APP</ns2:deviceApp>
            <ns2:deviceOs>ANDROID</ns2:deviceOs>
            <ns2:smartDeviceCarriers>DOCOMO</ns2:smartDeviceCarriers>
            <ns2:deviceOsVersion>[8.0]</ns2:deviceOsVersion>
            <ns2:dynamicImageExtensions>ACTIVE</ns2:dynamicImageExtensions>
            <ns2:adGroupBiddingStrategy>
              <ns2:campaignBiddingStrategyType>NONE</ns2:campaignBiddingStrategyType>
            </ns2:adGroupBiddingStrategy>
          </ns2:adGroup>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroup>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>test campaign.</ns2:campaignName>
            <ns2:adGroupId>20003</ns2:adGroupId>
            <ns2:adGroupName>test video adGroup.</ns2:adGroupName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPVAdGroupBid">
              <ns2:type>MANUAL_CPV</ns2:type>
              <ns2:maxCpv>100</ns2:maxCpv>
            </ns2:bid>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:NoneAdGroupConversionOptimizer">
              <ns2:optimizerType>NONE</ns2:optimizerType>
            </ns2:conversionOptimizer>
            <ns2:device>SMARTPHONE</ns2:device>
            <ns2:deviceApp>APP</ns2:deviceApp>
            <ns2:deviceOs>ANDROID</ns2:deviceOs>
            <ns2:smartDeviceCarriers>NONE</ns2:smartDeviceCarriers>
            <ns2:adGroupBiddingStrategy>
              <ns2:campaignBiddingStrategyType>NONE</ns2:campaignBiddingStrategyType>
            </ns2:adGroupBiddingStrategy>
          </ns2:adGroup>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroup>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10002</ns2:campaignId>
            <ns2:campaignName>test campaign with campaignGoal.</ns2:campaignName>
            <ns2:adGroupId>20004</ns2:adGroupId>
            <ns2:adGroupName>test adGroup with campaignGoal.</ns2:adGroupName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualAdGroupConversionOptimizer">
              <ns2:optimizerType>MANUAL</ns2:optimizerType>
              <ns2:eligibilityFlg>DISABLE</ns2:eligibilityFlg>
            </ns2:conversionOptimizer>
            <ns2:device>DESKTOP</ns2:device>
            <ns2:feedSetId>1000</ns2:feedSetId>
            <ns2:adGroupBiddingStrategy>
              <ns2:campaignBiddingStrategyType>MAX_VCPM</ns2:campaignBiddingStrategyType>
              <ns2:maxVcpmBidValue>1000</ns2:maxVcpmBidValue>
            </ns2:adGroupBiddingStrategy>
          </ns2:adGroup>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)

### リクエスト

広告グループを変更します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| operations | Yes | [AdGroupOperation](../data/AdGroup/AdGroupOperation.md) |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/AdGroup" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201911/AdGroup">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <accountId>0</accountId>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <adGroupName>set test adGroup.</adGroupName>
          <userStatus>PAUSED</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPCAdGroupBid">
            <type>MANUAL_CPC</type>
            <maxCpc>1000</maxCpc>
          </bid>
          <conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AutoAdGroupConversionOptimizer">
            <optimizerType>AUTO</optimizerType>
            <targetCpa>1000</targetCpa>
          </conversionOptimizer>
          <device>TABLET</device>
          <deviceApp>APP</deviceApp>
          <deviceOs>ANDROID</deviceOs>
          <smartDeviceCarriers>DOCOMO</smartDeviceCarriers>
          <deviceOsVersion>[8.0]</deviceOsVersion>
          <dynamicImageExtensions>ACTIVE</dynamicImageExtensions>
          <isRemoveFeedSetId>true</isRemoveFeedSetId>
        </operand>
        <operand>
          <accountId>0</accountId>
          <campaignId>10002</campaignId>
          <adGroupId>20002</adGroupId>
          <adGroupName>set test adGroup2.</adGroupName>
          <userStatus>ACTIVE</userStatus>
          <bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualCPCAdGroupBid">
            <type>MANUAL_CPC</type>
            <maxCpc>100</maxCpc>
          </bid>
          <conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ManualAdGroupConversionOptimizer">
            <optimizerType>MANUAL</optimizerType>
            <eligibilityFlg>DISABLE</eligibilityFlg>
          </conversionOptimizer>
          <device>DESKTOP</device>
          <dynamicImageExtensions>ACTIVE</dynamicImageExtensions>
        </operand>
        <operand>
          <accountId>1234567890</accountId>
          <campaignId>10003</campaignId>
          <adGroupId>20003</adGroupId>
          <adGroupName>set test adGroup2.</adGroupName>
          <conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="NoneAdGroupConversionOptimizer">
            <optimizerType>NONE</optimizerType>
          </conversionOptimizer>
          <device>SMARTPHONE</device>
          <adGroupBiddingStrategy>
            <maxCpcBidValue>1000</maxCpcBidValue>
          </adGroupBiddingStrategy>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス

| パラメータ | データ型 |
| -------- | ------- |
| rval | [AdGroupReturnValue](../data/AdGroup/AdGroupReturnValue.md) |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/AdGroup" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>AdGroup</ns2:service>
      <ns2:requestTime>1574393614691</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/AdGroup">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroup>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>test campaign.</ns2:campaignName>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:adGroupName>test app adGroup.</ns2:adGroupName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>1000</ns2:maxCpc>
            </ns2:bid>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AutoAdGroupConversionOptimizer">
              <ns2:optimizerType>AUTO</ns2:optimizerType>
              <ns2:targetCpa>1000</ns2:targetCpa>
            </ns2:conversionOptimizer>
            <ns2:device>TABLET</ns2:device>
            <ns2:deviceApp>APP</ns2:deviceApp>
            <ns2:deviceOs>ANDROID</ns2:deviceOs>
            <ns2:smartDeviceCarriers>DOCOMO</ns2:smartDeviceCarriers>
            <ns2:deviceOsVersion>[8.0]</ns2:deviceOsVersion>
            <ns2:dynamicImageExtensions>ACTIVE</ns2:dynamicImageExtensions>
            <ns2:adGroupBiddingStrategy>
              <ns2:campaignBiddingStrategyType>NONE</ns2:campaignBiddingStrategyType>
            </ns2:adGroupBiddingStrategy>
          </ns2:adGroup>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroup>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10002</ns2:campaignId>
            <ns2:campaignName>test campaign2.</ns2:campaignName>
            <ns2:adGroupId>20002</ns2:adGroupId>
            <ns2:adGroupName>set test adGroup2.</ns2:adGroupName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualAdGroupConversionOptimizer">
              <ns2:optimizerType>MANUAL</ns2:optimizerType>
              <ns2:eligibilityFlg>DISABLE</ns2:eligibilityFlg>
            </ns2:conversionOptimizer>
            <ns2:device>DESKTOP</ns2:device>
            <ns2:smartDeviceCarriers>NONE</ns2:smartDeviceCarriers>
            <ns2:dynamicImageExtensions>ACTIVE</ns2:dynamicImageExtensions>
            <ns2:adGroupBiddingStrategy>
              <ns2:campaignBiddingStrategyType>NONE</ns2:campaignBiddingStrategyType>
            </ns2:adGroupBiddingStrategy>
          </ns2:adGroup>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroup>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10003</ns2:campaignId>
            <ns2:campaignName>test campaign with campaignGoal.</ns2:campaignName>
            <ns2:adGroupId>20003</ns2:adGroupId>
            <ns2:adGroupName>set test adGroup2.</ns2:adGroupName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:NoneAdGroupConversionOptimizer">
              <ns2:optimizerType>NONE</ns2:optimizerType>
            </ns2:conversionOptimizer>
            <ns2:device>SMARTPHONE</ns2:device>
            <ns2:adGroupBiddingStrategy>
              <ns2:campaignBiddingStrategyType>MAX_CPC</ns2:campaignBiddingStrategyType>
              <ns2:maxCpcBidValue>1000</ns2:maxCpcBidValue>
            </ns2:adGroupBiddingStrategy>
          </ns2:adGroup>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)

### リクエスト

広告グループを削除します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| operations | Yes | [AdGroupOperation](../data/AdGroup/AdGroupOperation.md) |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/AdGroup" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201911/AdGroup">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1234567890</accountId>
        <operand>
          <accountId>0</accountId>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス

| パラメータ | データ型 |
| -------- | ------- |
| rval | [AdGroupReturnValue](../data/AdGroup/AdGroupReturnValue.md) |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/AdGroup" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>AdGroup</ns2:service>
      <ns2:requestTime>1574393614819</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/AdGroup">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroup>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>test campaign.</ns2:campaignName>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:adGroupName>test adGroup.</ns2:adGroupName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:bid xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCPCAdGroupBid">
              <ns2:type>MANUAL_CPC</ns2:type>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
            <ns2:conversionOptimizer xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualAdGroupConversionOptimizer">
              <ns2:optimizerType>MANUAL</ns2:optimizerType>
              <ns2:eligibilityFlg>DISABLE</ns2:eligibilityFlg>
            </ns2:conversionOptimizer>
            <ns2:device>DESKTOP</ns2:device>
            <ns2:dynamicImageExtensions>ACTIVE</ns2:dynamicImageExtensions>
            <ns2:adGroupBiddingStrategy>
              <ns2:campaignBiddingStrategyType>NONE</ns2:campaignBiddingStrategyType>
            </ns2:adGroupBiddingStrategy>
          </ns2:adGroup>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

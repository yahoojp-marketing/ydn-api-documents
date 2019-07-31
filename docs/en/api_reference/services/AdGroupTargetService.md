# AdGroupTargetService
The service let you perform targeting settings operations (get, add, set, replace and remove) for ad group.
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201907/AdGroupTargetService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201907/AdGroupTargetService?wsdl |
#### Namespace
http://im.yahooapis.jp/V201907/AdGroupTarget
#### Service Overview
Performs target settings related operations (get, add, set, replace and remove) for ad group.
#### Operation
Explains operations provided by AdGroupTargetService.

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)
+ [replace](#replace)


#### Object
[AdGroupTarget](../data/AdGroupTarget)

## get

### Request
Gets target settings related for ad group.

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| selector | required | [AdGroupTargetSelector](../data/AdGroupTarget/AdGroupTargetSelector.md) | Contains a set of criteria (parameters) for get method. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/AdGroupTarget" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201907/AdGroupTarget" xmlns:ns2="http://im.yahooapis.jp/V201907">
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
        <targetTypes>AD_SCHEDULE_TARGET</targetTypes>
        <targetTypes>AGE_TARGET</targetTypes>
        <targetTypes>APP_TARGET</targetTypes>
        <targetTypes>CARRIER_TARGET</targetTypes>
        <targetTypes>GENDER_TARGET</targetTypes>
        <targetTypes>INTEREST_CATEGORY</targetTypes>
        <targetTypes>OS_TARGET</targetTypes>
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
| rval | [AdGroupTargetPage](../data/AdGroupTarget/AdGroupTargetPage.md) | Contains the results (a list of all entities) for get method. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/AdGroupTarget" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>AdGroupTarget</ns2:service>
      <ns2:requestTime>1551686143079</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/AdGroupTarget">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>AdGroupTargetPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AdScheduleTarget">
              <ns2:type>AD_SCHEDULE_TARGET</ns2:type>
              <ns2:targetId>aa111111</ns2:targetId>
              <ns2:dayOfWeek>MONDAY</ns2:dayOfWeek>
              <ns2:startHour>13</ns2:startHour>
              <ns2:endHour>14</ns2:endHour>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GeoTarget">
              <ns2:type>GEO_TARGET</ns2:type>
              <ns2:targetId>aa111111</ns2:targetId>
              <ns2:geoNameJa>岩手県</ns2:geoNameJa>
              <ns2:geoNameEn>iwate_pref</ns2:geoNameEn>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AgeTarget">
              <ns2:type>AGE_TARGET</ns2:type>
              <ns2:targetId>aa111112</ns2:targetId>
              <ns2:age>GT_RANGE18_19</ns2:age>
              <ns2:estimateFlg>ACTIVE</ns2:estimateFlg>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GenderTarget">
              <ns2:type>GENDER_TARGET</ns2:type>
              <ns2:targetId>aa111112</ns2:targetId>
              <ns2:gender>ST_FEMALE</ns2:gender>
              <ns2:estimateFlg>ACTIVE</ns2:estimateFlg>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:InterestCategoryTarget">
              <ns2:type>INTEREST_CATEGORY</ns2:type>
              <ns2:targetId>TC-IC-99999</ns2:targetId>
              <ns2:categoryFullNameJa>消費財</ns2:categoryFullNameJa>
              <ns2:categoryFullNameEn>Consumer Packaged Good</ns2:categoryFullNameEn>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SiteCategoryTarget">
              <ns2:type>SITE_CATEGORY</ns2:type>
              <ns2:targetId>TC-SC-999999</ns2:targetId>
              <ns2:categoryFullNameJa>ニュース</ns2:categoryFullNameJa>
              <ns2:categoryFullNameEn>News</ns2:categoryFullNameEn>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:PlacementTarget">
              <ns2:type>PLACEMENT_TARGET</ns2:type>
              <ns2:targetId>12345678</ns2:targetId>
              <ns2:placementUrlListName>c</ns2:placementUrlListName>
              <ns2:deliverType>WHITE_LIST</ns2:deliverType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SearchTarget">
              <ns2:type>SEARCH_TARGET</ns2:type>
              <ns2:targetId>123456789</ns2:targetId>
              <ns2:searchKeywordListName>News</ns2:searchKeywordListName>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SiteRetargetingTarget">
              <ns2:type>SITE_RETARGETING</ns2:type>
              <ns2:targetId>123456789</ns2:targetId>
              <ns2:targetListName>Default List</ns2:targetListName>
              <ns2:deliverType>INCLUDE</ns2:deliverType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:DeviceTarget">
              <ns2:type>DEVICE_TARGET</ns2:type>
              <ns2:targetId>de01</ns2:targetId>
              <ns2:deviceType>TABLET</ns2:deviceType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:CarrierTarget">
              <ns2:type>CARRIER_TARGET</ns2:type>
              <ns2:targetId>ca01</ns2:targetId>
              <ns2:mobileCarrier>DOCOMO</ns2:mobileCarrier>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppTarget">
              <ns2:type>APP_TARGET</ns2:type>
              <ns2:targetId>app01</ns2:targetId>
              <ns2:appType>APP</ns2:appType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:OsTarget">
              <ns2:type>OS_TARGET</ns2:type>
              <ns2:targetId>os01</ns2:targetId>
              <ns2:osType>ANDROID</ns2:osType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:OsVersionTarget">
              <ns2:type>OS_VERSION_TARGET</ns2:type>
              <ns2:targetId>ov01</ns2:targetId>
              <ns2:osVersion>8.0</ns2:osVersion>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)

### Request
Adds targeting information for an ad group

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| operations | required | [AdGroupTargetSelector](../data/AdGroupTarget/AdGroupTargetSelector.md) | Contains the targeting information for mutate/replace method. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/AdGroupTarget" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201907/AdGroupTarget">
      <operations>
        <operator>ADD</operator>
        <accountId>1234567890</accountId>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AdScheduleTarget">
            <type>AD_SCHEDULE_TARGET</type>
            <dayOfWeek>MONDAY</dayOfWeek>
            <startHour>13</startHour>
            <endHour>14</endHour>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="GeoTarget">
            <type>GEO_TARGET</type>
            <targetId>TC-CI-9999999</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AgeTarget">
            <type>AGE_TARGET</type>
            <age>GT_RANGE13_14</age>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="GenderTarget">
            <type>GENDER_TARGET</type>
            <gender>ST_FEMALE</gender>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="InterestCategoryTarget">
            <type>INTEREST_CATEGORY</type>
            <targetId>TC-IC-9999999</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SiteCategoryTarget">
            <type>SITE_CATEGORY</type>
            <targetId>TC-SC-9999999</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="PlacementTarget">
            <type>PLACEMENT_TARGET</type>
            <targetId>199999999</targetId>
            <deliverType>WHITE_LIST</deliverType>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SearchTarget">
            <type>SEARCH_TARGET</type>
            <targetId>299999999</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SiteRetargetingTarget">
            <type>SITE_RETARGETING</type>
            <targetId>20000000</targetId>
            <deliverType>INCLUDE</deliverType>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="DeviceTarget">
            <type>DEVICE_TARGET</type>
            <deviceType>SMARTPHONE</deviceType>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="CarrierTarget">
            <type>CARRIER_TARGET</type>
            <mobileCarrier>YMOBILE</mobileCarrier>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AppTarget">
            <type>APP_TARGET</type>
            <appType>APP</appType>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="OsVersionTarget">
            <type>OS_VERSION_TARGET</type>
            <osVersion>10.1</osVersion>
          </target>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [AdGroupTargetReturnValue](../data/AdGroupTarget/AdGroupTargetReturnValue.md) | Contains the results (a list of all entities) for mutate/replace method. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/AdGroupTarget" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>AdGroupTarget</ns2:service>
      <ns2:requestTime>1551686143113</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/AdGroupTarget">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupTargetReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AdScheduleTarget">
              <ns2:type>AD_SCHEDULE_TARGET</ns2:type>
              <ns2:targetId>aa111111</ns2:targetId>
              <ns2:dayOfWeek>MONDAY</ns2:dayOfWeek>
              <ns2:startHour>13</ns2:startHour>
              <ns2:endHour>14</ns2:endHour>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GeoTarget">
              <ns2:type>GEO_TARGET</ns2:type>
              <ns2:targetId>aa111111</ns2:targetId>
              <ns2:geoNameJa>岩手県</ns2:geoNameJa>
              <ns2:geoNameEn>iwate_pref</ns2:geoNameEn>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AgeTarget">
              <ns2:type>AGE_TARGET</ns2:type>
              <ns2:targetId>aa111112</ns2:targetId>
              <ns2:age>GT_RANGE18_19</ns2:age>
              <ns2:estimateFlg>ACTIVE</ns2:estimateFlg>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GenderTarget">
              <ns2:type>GENDER_TARGET</ns2:type>
              <ns2:targetId>aa111112</ns2:targetId>
              <ns2:gender>ST_FEMALE</ns2:gender>
              <ns2:estimateFlg>ACTIVE</ns2:estimateFlg>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:InterestCategoryTarget">
              <ns2:type>INTEREST_CATEGORY</ns2:type>
              <ns2:targetId>TC-IC-99999</ns2:targetId>
              <ns2:categoryFullNameJa>消費財</ns2:categoryFullNameJa>
              <ns2:categoryFullNameEn>Consumer Packaged Good</ns2:categoryFullNameEn>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SiteCategoryTarget">
              <ns2:type>SITE_CATEGORY</ns2:type>
              <ns2:targetId>TC-SC-999999</ns2:targetId>
              <ns2:categoryFullNameJa>ニュース</ns2:categoryFullNameJa>
              <ns2:categoryFullNameEn>News</ns2:categoryFullNameEn>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:PlacementTarget">
              <ns2:type>PLACEMENT_TARGET</ns2:type>
              <ns2:targetId>12345678</ns2:targetId>
              <ns2:placementUrlListName>c</ns2:placementUrlListName>
              <ns2:deliverType>WHITE_LIST</ns2:deliverType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SearchTarget">
              <ns2:type>SEARCH_TARGET</ns2:type>
              <ns2:targetId>123456789</ns2:targetId>
              <ns2:searchKeywordListName>News</ns2:searchKeywordListName>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SiteRetargetingTarget">
              <ns2:type>SITE_RETARGETING</ns2:type>
              <ns2:targetId>123456789</ns2:targetId>
              <ns2:targetListName>Default List</ns2:targetListName>
              <ns2:deliverType>INCLUDE</ns2:deliverType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:DeviceTarget">
              <ns2:type>DEVICE_TARGET</ns2:type>
              <ns2:targetId>de01</ns2:targetId>
              <ns2:deviceType>TABLET</ns2:deviceType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:CarrierTarget">
              <ns2:type>CARRIER_TARGET</ns2:type>
              <ns2:targetId>ca01</ns2:targetId>
              <ns2:mobileCarrier>DOCOMO</ns2:mobileCarrier>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppTarget">
              <ns2:type>APP_TARGET</ns2:type>
              <ns2:targetId>app01</ns2:targetId>
              <ns2:appType>APP</ns2:appType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:OsTarget">
              <ns2:type>OS_TARGET</ns2:type>
              <ns2:targetId>os01</ns2:targetId>
              <ns2:osType>ANDROID</ns2:osType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:OsVersionTarget">
              <ns2:type>OS_VERSION_TARGET</ns2:type>
              <ns2:targetId>ov01</ns2:targetId>
              <ns2:osVersion>8.0</ns2:osVersion>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)

### Request
Updates targeting information for an ad group

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| operations | required | [AdGroupTargetMutateOperation](../data/AdGroupTarget/AdGroupTargetMutateOperation.md) | Contains the targeting information for mutate/replace method. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/AdGroupTarget" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201907/AdGroupTarget">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AdScheduleTarget">
            <type>AD_SCHEDULE_TARGET</type>
            <targetId>as111111</targetId>
            <dayOfWeek>MONDAY</dayOfWeek>
            <startHour>13</startHour>
            <endHour>14</endHour>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="GeoTarget">
            <type>GEO_TARGET</type>
            <targetId>TC-CI-9999999</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AgeTarget">
            <type>AGE_TARGET</type>
            <targetId>ag9999</targetId>
            <age>GT_RANGE13_14</age>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="GenderTarget">
            <type>GENDER_TARGET</type>
            <targetId>ge0202</targetId>
            <gender>ST_FEMALE</gender>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="InterestCategoryTarget">
            <type>INTEREST_CATEGORY</type>
            <targetId>TC-IC-9999999</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SiteCategoryTarget">
            <type>SITE_CATEGORY</type>
            <targetId>TC-SC-9999999</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="PlacementTarget">
            <type>PLACEMENT_TARGET</type>
            <targetId>199999999</targetId>
            <deliverType>WHITE_LIST</deliverType>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SearchTarget">
            <type>SEARCH_TARGET</type>
            <targetId>299999999</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SiteRetargetingTarget">
            <type>SITE_RETARGETING</type>
            <targetId>20000000</targetId>
            <deliverType>INCLUDE</deliverType>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="DeviceTarget">
            <type>DEVICE_TARGET</type>
            <targetId>de001</targetId>
            <deviceType>SMARTPHONE</deviceType>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="CarrierTarget">
            <type>CARRIER_TARGET</type>
            <targetId>cr001</targetId>
            <mobileCarrier>YMOBILE</mobileCarrier>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AppTarget">
            <type>APP_TARGET</type>
            <targetId>ap001</targetId>
            <appType>APP</appType>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="OsTarget">
            <type>OS_TARGET</type>
            <targetId>os01</targetId>
            <osType>ANDROID</osType>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="OsVersionTarget">
            <type>OS_VERSION_TARGET</type>
            <targetId>ov001</targetId>
            <osVersion>10.1</osVersion>
          </target>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [AdGroupTargetReturnValue](../data/AdGroupTarget/AdGroupTargetReturnValue.md) | Contains the results (a list of all entities) for mutate/replace method. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/AdGroupTarget" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>AdGroupTarget</ns2:service>
      <ns2:requestTime>1551686143142</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/AdGroupTarget">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupTargetReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AdScheduleTarget">
              <ns2:type>AD_SCHEDULE_TARGET</ns2:type>
              <ns2:targetId>aa111111</ns2:targetId>
              <ns2:dayOfWeek>MONDAY</ns2:dayOfWeek>
              <ns2:startHour>13</ns2:startHour>
              <ns2:endHour>14</ns2:endHour>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GeoTarget">
              <ns2:type>GEO_TARGET</ns2:type>
              <ns2:targetId>aa111111</ns2:targetId>
              <ns2:geoNameJa>岩手県</ns2:geoNameJa>
              <ns2:geoNameEn>iwate_pref</ns2:geoNameEn>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AgeTarget">
              <ns2:type>AGE_TARGET</ns2:type>
              <ns2:targetId>aa111112</ns2:targetId>
              <ns2:age>GT_RANGE18_19</ns2:age>
              <ns2:estimateFlg>ACTIVE</ns2:estimateFlg>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GenderTarget">
              <ns2:type>GENDER_TARGET</ns2:type>
              <ns2:targetId>aa111112</ns2:targetId>
              <ns2:gender>ST_FEMALE</ns2:gender>
              <ns2:estimateFlg>ACTIVE</ns2:estimateFlg>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:InterestCategoryTarget">
              <ns2:type>INTEREST_CATEGORY</ns2:type>
              <ns2:targetId>TC-IC-99999</ns2:targetId>
              <ns2:categoryFullNameJa>消費財</ns2:categoryFullNameJa>
              <ns2:categoryFullNameEn>Consumer Packaged Good</ns2:categoryFullNameEn>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SiteCategoryTarget">
              <ns2:type>SITE_CATEGORY</ns2:type>
              <ns2:targetId>TC-SC-999999</ns2:targetId>
              <ns2:categoryFullNameJa>ニュース</ns2:categoryFullNameJa>
              <ns2:categoryFullNameEn>News</ns2:categoryFullNameEn>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:PlacementTarget">
              <ns2:type>PLACEMENT_TARGET</ns2:type>
              <ns2:targetId>12345678</ns2:targetId>
              <ns2:placementUrlListName>c</ns2:placementUrlListName>
              <ns2:deliverType>WHITE_LIST</ns2:deliverType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SearchTarget">
              <ns2:type>SEARCH_TARGET</ns2:type>
              <ns2:targetId>123456789</ns2:targetId>
              <ns2:searchKeywordListName>News</ns2:searchKeywordListName>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SiteRetargetingTarget">
              <ns2:type>SITE_RETARGETING</ns2:type>
              <ns2:targetId>123456789</ns2:targetId>
              <ns2:targetListName>Default List</ns2:targetListName>
              <ns2:deliverType>INCLUDE</ns2:deliverType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:DeviceTarget">
              <ns2:type>DEVICE_TARGET</ns2:type>
              <ns2:targetId>de01</ns2:targetId>
              <ns2:deviceType>TABLET</ns2:deviceType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:CarrierTarget">
              <ns2:type>CARRIER_TARGET</ns2:type>
              <ns2:targetId>ca01</ns2:targetId>
              <ns2:mobileCarrier>DOCOMO</ns2:mobileCarrier>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppTarget">
              <ns2:type>APP_TARGET</ns2:type>
              <ns2:targetId>app01</ns2:targetId>
              <ns2:appType>APP</ns2:appType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:OsTarget">
              <ns2:type>OS_TARGET</ns2:type>
              <ns2:targetId>os01</ns2:targetId>
              <ns2:osType>ANDROID</ns2:osType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:OsVersionTarget">
              <ns2:type>OS_VERSION_TARGET</ns2:type>
              <ns2:targetId>ov01</ns2:targetId>
              <ns2:osVersion>8.0</ns2:osVersion>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)

### Request
Removes targeting information for an ad group

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| operations | required | [AdGroupTargetMutateOperation](../data/AdGroupTarget/AdGroupTargetMutateOperation.md) | Contains the targeting information for mutate/replace method. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/AdGroupTarget" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201907/AdGroupTarget">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1234567890</accountId>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AdScheduleTarget">
            <type>AD_SCHEDULE_TARGET</type>
            <targetId>as111111</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="GeoTarget">
            <type>GEO_TARGET</type>
            <targetId>TC-CI-9999999</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AgeTarget">
            <type>AGE_TARGET</type>
            <targetId>ag9999</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="GenderTarget">
            <type>GENDER_TARGET</type>
            <targetId>ge0202</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="InterestCategoryTarget">
            <type>INTEREST_CATEGORY</type>
            <targetId>TC-IC-9999999</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SiteCategoryTarget">
            <type>SITE_CATEGORY</type>
            <targetId>TC-SC-9999999</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="PlacementTarget">
            <type>PLACEMENT_TARGET</type>
            <targetId>199999999</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SearchTarget">
            <type>SEARCH_TARGET</type>
            <targetId>299999999</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SiteRetargetingTarget">
            <type>SITE_RETARGETING</type>
            <targetId>20000000</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="DeviceTarget">
            <type>DEVICE_TARGET</type>
            <targetId>de001</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="CarrierTarget">
            <type>CARRIER_TARGET</type>
            <targetId>cr001</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AppTarget">
            <type>APP_TARGET</type>
            <targetId>ap001</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="OsTarget">
            <type>OS_TARGET</type>
            <targetId>os01</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="OsVersionTarget">
            <type>OS_VERSION_TARGET</type>
            <targetId>ov001</targetId>
          </target>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [AdGroupTargetReturnValue](../data/AdGroupTarget/AdGroupTargetReturnValue.md) | Contains the results (a list of all entities) for mutate/replace method. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/AdGroupTarget" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>AdGroupTarget</ns2:service>
      <ns2:requestTime>1551686143170</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/AdGroupTarget">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupTargetReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AdScheduleTarget">
              <ns2:type>AD_SCHEDULE_TARGET</ns2:type>
              <ns2:targetId>aa111111</ns2:targetId>
              <ns2:dayOfWeek>MONDAY</ns2:dayOfWeek>
              <ns2:startHour>13</ns2:startHour>
              <ns2:endHour>14</ns2:endHour>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GeoTarget">
              <ns2:type>GEO_TARGET</ns2:type>
              <ns2:targetId>aa111111</ns2:targetId>
              <ns2:geoNameJa>岩手県</ns2:geoNameJa>
              <ns2:geoNameEn>iwate_pref</ns2:geoNameEn>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AgeTarget">
              <ns2:type>AGE_TARGET</ns2:type>
              <ns2:targetId>aa111112</ns2:targetId>
              <ns2:age>GT_RANGE18_19</ns2:age>
              <ns2:estimateFlg>ACTIVE</ns2:estimateFlg>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GenderTarget">
              <ns2:type>GENDER_TARGET</ns2:type>
              <ns2:targetId>aa111112</ns2:targetId>
              <ns2:gender>ST_FEMALE</ns2:gender>
              <ns2:estimateFlg>ACTIVE</ns2:estimateFlg>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:InterestCategoryTarget">
              <ns2:type>INTEREST_CATEGORY</ns2:type>
              <ns2:targetId>TC-IC-99999</ns2:targetId>
              <ns2:categoryFullNameJa>消費財</ns2:categoryFullNameJa>
              <ns2:categoryFullNameEn>Consumer Packaged Good</ns2:categoryFullNameEn>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SiteCategoryTarget">
              <ns2:type>SITE_CATEGORY</ns2:type>
              <ns2:targetId>TC-SC-999999</ns2:targetId>
              <ns2:categoryFullNameJa>ニュース</ns2:categoryFullNameJa>
              <ns2:categoryFullNameEn>News</ns2:categoryFullNameEn>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:PlacementTarget">
              <ns2:type>PLACEMENT_TARGET</ns2:type>
              <ns2:targetId>12345678</ns2:targetId>
              <ns2:placementUrlListName>c</ns2:placementUrlListName>
              <ns2:deliverType>WHITE_LIST</ns2:deliverType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SearchTarget">
              <ns2:type>SEARCH_TARGET</ns2:type>
              <ns2:targetId>123456789</ns2:targetId>
              <ns2:searchKeywordListName>News</ns2:searchKeywordListName>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SiteRetargetingTarget">
              <ns2:type>SITE_RETARGETING</ns2:type>
              <ns2:targetId>123456789</ns2:targetId>
              <ns2:targetListName>Default List</ns2:targetListName>
              <ns2:deliverType>INCLUDE</ns2:deliverType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:DeviceTarget">
              <ns2:type>DEVICE_TARGET</ns2:type>
              <ns2:targetId>de01</ns2:targetId>
              <ns2:deviceType>TABLET</ns2:deviceType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:CarrierTarget">
              <ns2:type>CARRIER_TARGET</ns2:type>
              <ns2:targetId>ca01</ns2:targetId>
              <ns2:mobileCarrier>DOCOMO</ns2:mobileCarrier>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppTarget">
              <ns2:type>APP_TARGET</ns2:type>
              <ns2:targetId>app01</ns2:targetId>
              <ns2:appType>APP</ns2:appType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:OsTarget">
              <ns2:type>OS_TARGET</ns2:type>
              <ns2:targetId>os01</ns2:targetId>
              <ns2:osType>ANDROID</ns2:osType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:OsVersionTarget">
              <ns2:type>OS_VERSION_TARGET</ns2:type>
              <ns2:targetId>ov01</ns2:targetId>
              <ns2:osVersion>8.0</ns2:osVersion>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## replace

### Request
Replaces (deletes and adds) targeting information for an ad group.

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| operations | required | [AdGroupTargetOperation](../data/AdGroupTarget/AdGroupTargetOperation.md) | Contains the targeting information for mutate/replace method. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/AdGroupTarget" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <replace xmlns="http://im.yahooapis.jp/V201907/AdGroupTarget">
      <operations>
        <accountId>1234567890</accountId>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AdScheduleTarget">
            <type>AD_SCHEDULE_TARGET</type>
            <dayOfWeek>MONDAY</dayOfWeek>
            <startHour>13</startHour>
            <endHour>14</endHour>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="GeoTarget">
            <type>GEO_TARGET</type>
            <targetId>TC-CI-9999999</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AgeTarget">
            <type>AGE_TARGET</type>
            <age>GT_RANGE13_14</age>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="GenderTarget">
            <type>GENDER_TARGET</type>
            <gender>ST_FEMALE</gender>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="InterestCategoryTarget">
            <type>INTEREST_CATEGORY</type>
            <targetId>TC-IC-9999999</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SiteCategoryTarget">
            <type>SITE_CATEGORY</type>
            <targetId>TC-SC-9999999</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="PlacementTarget">
            <type>PLACEMENT_TARGET</type>
            <targetId>199999999</targetId>
            <deliverType>WHITE_LIST</deliverType>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SearchTarget">
            <type>SEARCH_TARGET</type>
            <targetId>299999999</targetId>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SiteRetargetingTarget">
            <type>SITE_RETARGETING</type>
            <targetId>20000000</targetId>
            <deliverType>INCLUDE</deliverType>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="DeviceTarget">
            <type>DEVICE_TARGET</type>
            <deviceType>SMARTPHONE</deviceType>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <bidMultiplier>1.1</bidMultiplier>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="CarrierTarget">
            <type>CARRIER_TARGET</type>
            <mobileCarrier>YMOBILE</mobileCarrier>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AppTarget">
            <type>APP_TARGET</type>
            <appType>APP</appType>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="OsVersionTarget">
            <type>OS_VERSION_TARGET</type>
            <osVersion>10.1</osVersion>
          </target>
        </operand>
      </operations>
    </replace>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [AdGroupTargetReturnValue](../data/AdGroupTarget/AdGroupTargetReturnValue.md) | Contains the results (a list of all entities) for mutate/replace method. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/AdGroupTarget" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>AdGroupTarget</ns2:service>
      <ns2:requestTime>1551686143201</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:replaceResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/AdGroupTarget">
      <ns2:rval>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AdScheduleTarget">
              <ns2:type>AD_SCHEDULE_TARGET</ns2:type>
              <ns2:targetId>aa111111</ns2:targetId>
              <ns2:dayOfWeek>MONDAY</ns2:dayOfWeek>
              <ns2:startHour>13</ns2:startHour>
              <ns2:endHour>14</ns2:endHour>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GeoTarget">
              <ns2:type>GEO_TARGET</ns2:type>
              <ns2:targetId>aa111111</ns2:targetId>
              <ns2:geoNameJa>岩手県</ns2:geoNameJa>
              <ns2:geoNameEn>iwate_pref</ns2:geoNameEn>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AgeTarget">
              <ns2:type>AGE_TARGET</ns2:type>
              <ns2:targetId>aa111112</ns2:targetId>
              <ns2:age>GT_RANGE18_19</ns2:age>
              <ns2:estimateFlg>ACTIVE</ns2:estimateFlg>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GenderTarget">
              <ns2:type>GENDER_TARGET</ns2:type>
              <ns2:targetId>aa111112</ns2:targetId>
              <ns2:gender>ST_FEMALE</ns2:gender>
              <ns2:estimateFlg>ACTIVE</ns2:estimateFlg>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:InterestCategoryTarget">
              <ns2:type>INTEREST_CATEGORY</ns2:type>
              <ns2:targetId>TC-IC-99999</ns2:targetId>
              <ns2:categoryFullNameJa>消費財</ns2:categoryFullNameJa>
              <ns2:categoryFullNameEn>Consumer Packaged Good</ns2:categoryFullNameEn>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SiteCategoryTarget">
              <ns2:type>SITE_CATEGORY</ns2:type>
              <ns2:targetId>TC-SC-999999</ns2:targetId>
              <ns2:categoryFullNameJa>ニュース</ns2:categoryFullNameJa>
              <ns2:categoryFullNameEn>News</ns2:categoryFullNameEn>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:PlacementTarget">
              <ns2:type>PLACEMENT_TARGET</ns2:type>
              <ns2:targetId>12345678</ns2:targetId>
              <ns2:placementUrlListName>c</ns2:placementUrlListName>
              <ns2:deliverType>WHITE_LIST</ns2:deliverType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SearchTarget">
              <ns2:type>SEARCH_TARGET</ns2:type>
              <ns2:targetId>123456789</ns2:targetId>
              <ns2:searchKeywordListName>News</ns2:searchKeywordListName>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SiteRetargetingTarget">
              <ns2:type>SITE_RETARGETING</ns2:type>
              <ns2:targetId>123456789</ns2:targetId>
              <ns2:targetListName>Default List</ns2:targetListName>
              <ns2:deliverType>INCLUDE</ns2:deliverType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:DeviceTarget">
              <ns2:type>DEVICE_TARGET</ns2:type>
              <ns2:targetId>de01</ns2:targetId>
              <ns2:deviceType>TABLET</ns2:deviceType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:bidMultiplier>1.15</ns2:bidMultiplier>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:CarrierTarget">
              <ns2:type>CARRIER_TARGET</ns2:type>
              <ns2:targetId>ca01</ns2:targetId>
              <ns2:mobileCarrier>DOCOMO</ns2:mobileCarrier>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppTarget">
              <ns2:type>APP_TARGET</ns2:type>
              <ns2:targetId>app01</ns2:targetId>
              <ns2:appType>APP</ns2:appType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:OsTarget">
              <ns2:type>OS_TARGET</ns2:type>
              <ns2:targetId>os01</ns2:targetId>
              <ns2:osType>ANDROID</ns2:osType>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupTargetList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:OsVersionTarget">
              <ns2:type>OS_VERSION_TARGET</ns2:type>
              <ns2:targetId>ov01</ns2:targetId>
              <ns2:osVersion>8.0</ns2:osVersion>
            </ns2:target>
          </ns2:adGroupTargetList>
        </ns2:values>
      </ns2:rval>
    </ns2:replaceResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

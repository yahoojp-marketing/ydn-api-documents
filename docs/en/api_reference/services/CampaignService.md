# CampaignService
Use this service to get, add, update, or delete campaigns.
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V5.2/CampaignService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/V5.2/CampaignService?wsdl|
#### Namespace
http://im.yahooapis.jp/V5
#### Service Overview
Offers campaign operation.
#### Operation
Describes operations provided by CampaignService.
## get
### Request
Gets information related to campaigns.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| selector | ○ | [CampaignSelector](../data/CampaignSelector.md) | Assigns campaign information to be acquired. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>1111-1111-1111-1111</ns1:license>
      <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
      <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:get>
      <ns1:selector>
        <ns1:accountId>1111111111</ns1:accountId>
        <ns1:campaignIds>1111111110</ns1:campaignIds>
        <ns1:campaignIds>2222222220</ns1:campaignIds>
        <ns1:userStatus>ACTIVE</ns1:userStatus>
        <ns1:userStatus>PAUSED</ns1:userStatus>               
        <ns1:paging>
          <ns1:startIndex>1</ns1:startIndex>
          <ns1:numberResults>20</ns1:numberResults>
        </ns1:paging>
      </ns1:selector>
    </ns1:get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>1111-1111-1111-1111</ns1:license>
      <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
      <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
      <ns1:accountId>1111111111</ns1:accountId>
      <ns1:onBehalfOfAccountId>33333-3333-33333-3333</ns1:onBehalfOfAccountId>
      <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:get>
      <ns1:selector>
        <ns1:accountId>1111111111</ns1:accountId>
        <ns1:campaignIds>1111111110</ns1:campaignIds>
        <ns1:campaignIds>2222222220</ns1:campaignIds>
        <ns1:userStatus>ACTIVE</ns1:userStatus>
        <ns1:userStatus>PAUSED</ns1:userStatus>       
        <ns1:paging>
          <ns1:startIndex>1</ns1:startIndex>
          <ns1:numberResults>20</ns1:numberResults>
        </ns1:paging>
      </ns1:selector>
    </ns1:get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [CampaignPage](../data/CampaignPage.md) | Container including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:rval>
                <ns1:Page.Type>CampaignPage</ns1:Page.Type>
                <ns1:totalNumEntries>2</ns1:totalNumEntries>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaign>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000001</ns1:campaignId>
                        <ns1:campaignName>campaign name1</ns1:campaignName>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:servingStatus>PENDING</ns1:servingStatus>
                        <ns1:startDate>20101201</ns1:startDate>
                        <ns1:endDate>20371231</ns1:endDate>
                        <ns1:budget>
                            <ns1:amount>10000000</ns1:amount>
                            <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                        </ns1:budget>
                        <ns1:biddingStrategy xsi:type="ns1:ManualCPC">
                            <ns1:type>MANUAL_CPC</ns1:type>
                        </ns1:biddingStrategy>
                        <ns1:adProductType>INTEREST_MATCH</ns1:adProductType>
<!-- No frequencyCap elements when frequency is not set -->
<!-- Conversion optimization setting in invalid condition -->
                        <ns1:conversionOptimizer>
                            <ns1:targetCpa>0</ns1:targetCpa>
                            <ns1:eligibilityFlg>DISABLE</ns1:eligibilityFlg>
                        </ns1:conversionOptimizer>
                    </ns1:campaign>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaign>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000002</ns1:campaignId>
                        <ns1:campaignName>campaign name2</ns1:campaignName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:servingStatus>SERVING</ns1:servingStatus>
                        <ns1:startDate>20120601</ns1:startDate>
                        <ns1:endDate>20371231</ns1:endDate>
                        <ns1:budget>
                            <ns1:deliveryMethod>ACCELERATED</ns1:deliveryMethod>
                        </ns1:budget>
                        <ns1:biddingStrategy xsi:type="ns1:ManualCPC">
                            <ns1:type>MANUAL_CPC</ns1:type>
                        </ns1:biddingStrategy>
                        <ns1:adProductType>TARGET_MATCH</ns1:adProductType>
                        <ns1:frequencyCap>
                            <ns1:level>AD_GROUP</ns1:level>
                            <ns1:timeUnit>MONTH</ns1:timeUnit>
                            <ns1:impression>15</ns1:impression>
                        </ns1:frequencyCap>
<!-- Conversion optimization setting in invalid condition -->
                        <ns1:conversionOptimizer>
                            <ns1:targetCpa>0</ns1:targetCpa>
                            <ns1:eligibilityFlg>DISABLE</ns1:eligibilityFlg>
                        </ns1:conversionOptimizer>
                    </ns1:campaign>
                </ns1:values>
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
### Request
Adds campaign information.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| operations | ○ | [CampaignOperation](../data/CampaignOperation.md) | Assigns campaign information for operation. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
     <ns1:RequestHeader>
          <ns1:license>1111-1111-1111-1111</ns1:license>
          <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
          <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
      </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignName>Sample campaign1</ns1:campaignName>
                    <ns1:userStatus>PAUSED</ns1:userStatus>
                    <ns1:startDate>20101201</ns1:startDate>
                    <ns1:endDate>20101231</ns1:endDate>
                    <ns1:budget>
                        <ns1:amount>10000</ns1:amount>
                        <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                    </ns1:budget>
                    <ns1:biddingStrategy xsi:type="ns1:ManualCPC">
                        <ns1:type>MANUAL_CPC</ns1:type>
                    </ns1:biddingStrategy>
                    <ns1:adProductType>INTEREST_MATCH</ns1:adProductType>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignName>Sample campaign2</ns1:campaignName>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:startDate>20121201</ns1:startDate>
                    <ns1:endDate>20121231</ns1:endDate>
                    <ns1:budget>
                        <ns1:deliveryMethod>ACCELERATED</ns1:deliveryMethod>
                    </ns1:budget>
                    <ns1:biddingStrategy xsi:type="ns1:ManualCPC">
                        <ns1:type>MANUAL_CPC</ns1:type>
                    </ns1:biddingStrategy>
                    <ns1:adProductType>TARGET_MATCH</ns1:adProductType>
                    <ns1:frequencyCap>
                        <ns1:level>AD_GROUP</ns1:level>
                        <ns1:timeUnit>MONTH</ns1:timeUnit>
                        <ns1:impression>15</ns1:impression>
                    </ns1:frequencyCap>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
       <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>1111111111</ns1:accountId>
            <ns1:onBehalfOfAccountId>33333-3333-33333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
       </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>1111111111</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>1111111111</ns1:accountId>
                    <ns1:campaignName>Sample campaign1</ns1:campaignName>
                    <ns1:userStatus>PAUSED</ns1:userStatus>
                    <ns1:startDate>20101201</ns1:startDate>
                    <ns1:endDate>20101231</ns1:endDate>
                    <ns1:budget>
                        <ns1:amount>10000</ns1:amount>
                        <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                    </ns1:budget>
                    <ns1:biddingStrategy xsi:type="ns1:ManualCPC">
                        <ns1:type>MANUAL_CPC</ns1:type>
                    </ns1:biddingStrategy>
                    <ns1:adProductType>INTEREST_MATCH</ns1:adProductType>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1111111111</ns1:accountId>
                    <ns1:campaignName>Sample campaign2</ns1:campaignName>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:startDate>20120601</ns1:startDate>
                    <ns1:endDate>20121231</ns1:endDate>
                    <ns1:budget>
                        <ns1:deliveryMethod>ACCELERATED</ns1:deliveryMethod>
                    </ns1:budget>
                    <ns1:biddingStrategy xsi:type="ns1:ManualCPC">
                        <ns1:type>MANUAL_CPC</ns1:type>
                    </ns1:biddingStrategy>
                    <ns1:adProductType>TARGET_MATCH</ns1:adProductType>
                    <ns1:frequencyCap>
                        <ns1:level>AD_GROUP</ns1:level>
                        <ns1:timeUnit>MONTH</ns1:timeUnit>
                        <ns1:impression>15</ns1:impression>
                    </ns1:frequencyCap>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [CampaignReturnValue](../data/CampaignReturnValue.md) | Container including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>2</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>CampaignReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>ADD</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaign>
                        <ns1:accountId>1111111111</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignName>Sample campaign1</ns1:campaignName>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:servingStatus>PENDING</ns1:servingStatus>
                        <ns1:startDate>20101201</ns1:startDate>
                        <ns1:endDate>20101231</ns1:endDate>
                        <ns1:budget>
                            <ns1:amount>10000</ns1:amount>
                            <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                        </ns1:budget>
                        <ns1:biddingStrategy xsi:type="ns1:ManualCPC">
                            <ns1:type>MANUAL_CPC</ns1:type>
                        </ns1:biddingStrategy>
                        <ns1:adProductType>INTEREST_MATCH</ns1:adProductType>
<!-- Conversion optimization setting is not valid -->
                        <ns1:conversionOptimizer>
                            <ns1:targetCpa>0</ns1:targetCpa>
                            <ns1:eligibilityFlg>DISABLE</ns1:eligibilityFlg>
                        </ns1:conversionOptimizer>
                   </ns1:campaign>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaign>
                        <ns1:accountId>1111111111</ns1:accountId>
                        <ns1:campaignId>100000002</ns1:campaignId>
                        <ns1:campaignName>Sample campaign2</ns1:campaignName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:servingStatus>SERVING</ns1:servingStatus>
                        <ns1:startDate>20120601</ns1:startDate>
                        <ns1:endDate>20121231</ns1:endDate>
                        <ns1:budget>
                            <ns1:deliveryMethod>ACCELERATED</ns1:deliveryMethod>
                        </ns1:budget>
                        <ns1:biddingStrategy xsi:type="ns1:ManualCPC">
                           <ns1:type>MANUAL_CPC</ns1:type>
                        </ns1:biddingStrategy>
                        <ns1:adProductType>TARGET_MATCH</ns1:adProductType>
                        <ns1:frequencyCap>
                            <ns1:level>AD_GROUP</ns1:level>
                            <ns1:timeUnit>MONTH</ns1:timeUnit>
                            <ns1:impression>15</ns1:impression>
                        </ns1:frequencyCap>
<!-- Conversion optimization setting is not valid -->
                        <ns1:conversionOptimizer>
                            <ns1:targetCpa>0</ns1:targetCpa>
                            <ns1:eligibilityFlg>DISABLE</ns1:eligibilityFlg>
                        </ns1:conversionOptimizer>
                    </ns1:campaign>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
### Request
Updates campaign information.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| operations | ○ | [CampaignOperation](../data/CampaignOperation.md) | Assigns campaign information for operation. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000001</ns1:campaignId>
                    <ns1:campaignName>Modify sample campaign001</ns1:campaignName>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:startDate>20130101</ns1:startDate>
                    <ns1:endDate>20131231</ns1:endDate>
                    <ns1:budget>
                        <ns1:amount>1000000</ns1:amount>
                        <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                    </ns1:budget>
                    <ns1:biddingStrategy xsi:type="ns1:ManualCPC">
                         <ns1:type>MANUAL_CPC</ns1:type>
                    </ns1:biddingStrategy>
<!-- No change if there is no requests in frequency settings -->
<!-- To validate the conversion optimizer, set targetCpa between 1 and 9999999999  -->
                    <ns1:conversionOptimizer>
                        <ns1:targetCpa>30</ns1:targetCpa>
                    </ns1:conversionOptimizer>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000002</ns1:campaignId>
                    <ns1:campaignName>Modify sample campaign002</ns1:campaignName>
<!-- To add frequency settings, request all of the necessary elements -->
                    <ns1:frequencyCap>
                        <ns1:level>CAMPAIGN</ns1:level>
                        <ns1:timeUnit>WEEK</ns1:timeUnit>
                        <ns1:impression>5</ns1:impression>
                    </ns1:frequencyCap>
<!-- To deactivate conversion optimization, set targetCpa to 0 -->
                    <ns1:conversionOptimizer>
                        <ns1:targetCpa>0</ns1:targetCpa>
                    </ns1:conversionOptimizer>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000003</ns1:campaignId>
                    <ns1:campaignName>Modify sample campaign002</ns1:campaignName>
<!-- Can request only the elements you want to change the frequency settings -->
                    <ns1:frequencyCap>
                        <ns1:impression>8</ns1:impression>
                    </ns1:frequencyCap>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000004</ns1:campaignId>
                    <ns1:campaignName>Modify sample campaign002</ns1:campaignName>
<!-- Frequecy setting will deactivate by not adding any elements -->
                    <ns1:frequencyCap></ns1:frequencyCap>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>1111111111</ns1:accountId>
            <ns1:onBehalfOfAccountId>33333-3333-33333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000001</ns1:campaignId>
                    <ns1:campaignName>Modify sample campaign001</ns1:campaignName>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:startDate>20130101</ns1:startDate>
                    <ns1:endDate>20131231</ns1:endDate>
                    <ns1:budget>
                        <ns1:amount>1000000</ns1:amount>
                        <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                    </ns1:budget>
                    <ns1:biddingStrategy xsi:type="ns1:ManualCPC">
                         <ns1:type>MANUAL_CPC</ns1:type>
                    </ns1:biddingStrategy>
<!-- No change if there is no requests in frequency settings -->
<!-- To validate the conversion optimizer, set targetCpa between 1 and 9999999999  -->
                    <ns1:conversionOptimizer>
                        <ns1:targetCpa>30</ns1:targetCpa>
                    </ns1:conversionOptimizer>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000002</ns1:campaignId>
                    <ns1:campaignName>Modify sample campaign002</ns1:campaignName>
<!-- To add frequency settings, request all of the necessary elements -->
                    <ns1:frequencyCap>
                        <ns1:level>CAMPAIGN</ns1:level>
                        <ns1:timeUnit>WEEK</ns1:timeUnit>
                        <ns1:impression>5</ns1:impression>
                    </ns1:frequencyCap>
<!-- To deactivate conversion optimization, set targetCpa to 0 -->
                    <ns1:conversionOptimizer>
                        <ns1:targetCpa>0</ns1:targetCpa>
                    </ns1:conversionOptimizer>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000003</ns1:campaignId>
                    <ns1:campaignName>Modify sample campaign003</ns1:campaignName>
<!-- Can request only the elements you want to change the frequency settings -->
                    <ns1:frequencyCap>
                        <ns1:impression>8</ns1:impression>
                    </ns1:frequencyCap>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000004</ns1:campaignId>
                    <ns1:campaignName>Modify sample campaign004</ns1:campaignName>
<!-- Frequecy setting will deactivate by not adding any elements -->
                    <ns1:frequencyCap></ns1:frequencyCap>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [CampaignReturnValue](../data/CampaignReturnValue.md) | Container including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>2</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>CampaignReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaign>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignName>Modify sample campaign001</ns1:campaignName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:servingStatus>PENDING</ns1:servingStatus>
                        <ns1:startDate>20130101</ns1:startDate>
                        <ns1:endDate>20131231</ns1:endDate>
                        <ns1:budget>
                           <ns1:amount>1000000</ns1:amount>
                           <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                        </ns1:budget>
                        <ns1:biddingStrategy xsi:type="ns1:ManualCPC">
                           <ns1:type>MANUAL_CPC</ns1:type>
                        </ns1:biddingStrategy>
                        <ns1:adProductType>INTEREST_MATCH</ns1:adProductType>
<!-- Conversion optimization is valid. targetCpa setting is possible, because eligibilityFlg=ENABLE -->
                        <ns1:conversionOptimizer>
                            <ns1:targetCpa>30</ns1:targetCpa>
                            <ns1:eligibilityFlg>ENABLE</ns1:eligibilityFlg>
                        </ns1:conversionOptimizer>
                   </ns1:campaign>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaign>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000002</ns1:campaignId>
                        <ns1:campaignName>Modify sample campaign002</ns1:campaignName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:servingStatus>SERVING</ns1:servingStatus>
                        <ns1:startDate>20120601</ns1:startDate>
                        <ns1:endDate>20121231</ns1:endDate>
                        <ns1:budget>
                           <ns1:deliveryMethod>ACCELERATED</ns1:deliveryMethod>
                        </ns1:budget>
                        <ns1:biddingStrategy xsi:type="ns1:ManualCPC">
                           <ns1:type>MANUAL_CPC</ns1:type>
                        </ns1:biddingStrategy>
                        <ns1:adProductType>TARGET_MATCH</ns1:adProductType>
<!-- No element in frequencyCap when there is no setting in frequency -->
<!-- Conversion optimization is not valid. targetCpa setting is possible, because eligibilityFlg=ENABLE -->
                        <ns1:conversionOptimizer>
                            <ns1:targetCpa>0</ns1:targetCpa>
                            <ns1:eligibilityFlg>ENABLE</ns1:eligibilityFlg>
                        </ns1:conversionOptimizer>
                    </ns1:campaign>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaign>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000003</ns1:campaignId>
                        <ns1:campaignName>Modify sample campaign003</ns1:campaignName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:servingStatus>SERVING</ns1:servingStatus>
                        <ns1:startDate>20130601</ns1:startDate>
                        <ns1:endDate>20131231</ns1:endDate>
                        <ns1:budget>
                           <ns1:deliveryMethod>ACCELERATED</ns1:deliveryMethod>
                        </ns1:budget>
                        <ns1:biddingStrategy xsi:type="ns1:ManualCPC">
                           <ns1:type>MANUAL_CPC</ns1:type>
                        </ns1:biddingStrategy>
                        <ns1:adProductType>TARGET_MATCH</ns1:adProductType>
                        <ns1:frequencyCap>
                            <ns1:level>AD_GROUP</ns1:level>
                            <ns1:timeUnit>MONTH</ns1:timeUnit>
                            <ns1:impression>15</ns1:impression>
                        </ns1:frequencyCap>
<!-- Conversion optimization is valid. eligibilityFlg is DISABLE, but targetCpa setting is possible. The setting will not be valid when updated to 0 -->
                        <ns1:conversionOptimizer>
                            <ns1:targetCpa>30</ns1:targetCpa>
                            <ns1:eligibilityFlg>DISABLE</ns1:eligibilityFlg>
                        </ns1:conversionOptimizer>
                    </ns1:campaign>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaign>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000004</ns1:campaignId>
                        <ns1:campaignName>Modify sample campaign004</ns1:campaignName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:servingStatus>SERVING</ns1:servingStatus>
                        <ns1:startDate>20130601</ns1:startDate>
                        <ns1:endDate>20131231</ns1:endDate>
                        <ns1:budget>
                           <ns1:deliveryMethod>ACCELERATED</ns1:deliveryMethod>
                        </ns1:budget>
                        <ns1:biddingStrategy xsi:type="ns1:ManualCPC">
                           <ns1:type>MANUAL_CPC</ns1:type>
                        </ns1:biddingStrategy>
                        <ns1:adProductType>TARGET_MATCH</ns1:adProductType>
                        
<!-- Conversion optimization is not valid. targetCpa setting is not possible, because eligibilityFlg=DISABLE and targetCpa=0-->
                        <ns1:conversionOptimizer>
                            <ns1:targetCpa>0</ns1:targetCpa>
                            <ns1:eligibilityFlg>DISABLE</ns1:eligibilityFlg>
                        </ns1:conversionOptimizer>
                    </ns1:campaign>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
### Request
Deletes campaign information.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| operations | ○ | [CampaignOperation](../data/CampaignOperation.md) | Assigns campaign information for operation. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000001</ns1:campaignId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000002</ns1:campaignId>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>1111111111</ns1:accountId>
            <ns1:onBehalfOfAccountId>33333-3333-33333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>1111111111</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>1111111111</ns1:accountId>
                    <ns1:campaignId>100000001</ns1:campaignId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1111111111</ns1:accountId>
                    <ns1:campaignId>100000002</ns1:campaignId>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [CampaignReturnValue](../data/CampaignReturnValue.md) | Container including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>2</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>CampaignReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaign>
                        <ns1:accountId>1111111111</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignName>Sample campaign1</ns1:campaignName>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:servingStatus>PENDING</ns1:servingStatus>
                        <ns1:startDate>20101201</ns1:startDate>
                        <ns1:endDate>20101231</ns1:endDate>
                        <ns1:budget>
                            <ns1:amount>10000</ns1:amount>
                            <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                        </ns1:budget>
                        <ns1:biddingStrategy xsi:type="ns1:ManualCPC">
                            <ns1:type>MANUAL_CPC</ns1:type>
                        </ns1:biddingStrategy>
                        <ns1:adProductType>INTEREST_MATCH</ns1:adProductType>
                        <ns1:conversionOptimizer>
                            <ns1:targetCpa>30</ns1:targetCpa>
                            <ns1:eligibilityFlg>ENABLE</ns1:eligibilityFlg>
                        </ns1:conversionOptimizer>
                   </ns1:campaign>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaign>
                        <ns1:accountId>1111111111</ns1:accountId>
                        <ns1:campaignId>100000002</ns1:campaignId>
                        <ns1:campaignName>Sample campaign2</ns1:campaignName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:servingStatus>SERVING</ns1:servingStatus>
                        <ns1:startDate>20120601</ns1:startDate>
                        <ns1:endDate>20121231</ns1:endDate>
                        <ns1:budget>
                           <ns1:deliveryMethod>ACCELERATED</ns1:deliveryMethod>
                        </ns1:budget>
                        <ns1:biddingStrategy xsi:type="ns1:ManualCPC">
                           <ns1:type>MANUAL_CPC</ns1:type>
                        </ns1:biddingStrategy>
                        <ns1:adProductType>TARGET_MATCH</ns1:adProductType>
                        <ns1:frequencyCap>
                            <ns1:level>AD_GROUP</ns1:level>
                            <ns1:timeUnit>MONTH</ns1:timeUnit>
                            <ns1:impression>15</ns1:impression>
                        </ns1:frequencyCap>
                        <ns1:conversionOptimizer>
                            <ns1:targetCpa>0</ns1:targetCpa>
                            <ns1:eligibilityFlg>ENABLE</ns1:eligibilityFlg>
                        </ns1:conversionOptimizer>
                    </ns1:campaign>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

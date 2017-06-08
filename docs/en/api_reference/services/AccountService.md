# AccountService
AccountService offers account operation.
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/Vx.x/AccountService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/Vx.x/AccountService?wsdl |
#### Namespace
http://im.yahooapis.jp/V6
#### Service Overview
Acquires and updates account information to be managed.
#### Operation
Describes operations provided by AccountService.
## get
### Request
Acquires account information.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| selector | required <br>(Can be omitted for regular authentication) | AccountSelector | Acquires account information.<br>*Account IDs under selector can also be omitted for regular authentication. Required for proxy authentication. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V6">
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
        <ns1:accountIds>1111111111</ns1:accountIds>
        <ns1:accountTypes>PREPAY</ns1:accountTypes>
        <ns1:accountStatuses>SERVING</ns1:accountStatuses>
        <ns1:accountStatuses>CANCELED</ns1:accountStatuses>
      </ns1:selector>
    </ns1:get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [AccountPage](../data/AccountPage.md) | Container including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>AccountService</ns1:service>
      <ns1:remainingQuota>42</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.6248</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getResponse>
      <ns1:rval>
        <ns1:totalNumEntries>2</ns1:totalNumEntries>
        <ns1:Page.Type>AccountPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:account>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:accountName>TEST_ACCOUNT_1</ns1:accountName>
            <ns1:accountType>PREPAY</ns1:accountType>
            <ns1:accountStatus>CANCELED</ns1:accountStatus>
          </ns1:account>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:account>
            <ns1:accountId>1000000002</ns1:accountId>
            <ns1:accountName>TEST_ACCOUNT_2</ns1:accountName>
            <ns1:accountType>INVOICE</ns1:accountType>
            <ns1:accountStatus>SERVING</ns1:accountStatus>
            <ns1:budget>
              <ns1:amount>100000</ns1:amount>
              <ns1:limitChargeType>MONTHLY</ns1:limitChargeType>
              <ns1:startDate>20120402</ns1:startDate>
              <ns1:endDate>20120802</ns1:endDate>
            </ns1:budget>
          </ns1:account>
        </ns1:values>
      </ns1:rval>
    </ns1:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
### Request
Operates account information.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| selector | required<br>(Can be omitted for regular authentication)|[AccountOperation](../data/AccountOperation.md)|Acquires account information.<br>*Account IDs under selector can also be omitted for regular authentication. Required for proxy authentication.| 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V6"> 
  <SOAP-ENV:Header> 
    <ns1:RequestHeader> 
      <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license> 
      <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId> 
      <ns1:apiAccountPassword>password</ns1:apiAccountPassword> 
    </ns1:RequestHeader> 
  </SOAP-ENV:Header> 
  <SOAP-ENV:Body> 
    <ns1:mutate> 
      <ns1:operations> 
        <ns1:operator>SET</ns1:operator> 
        <ns1:operand> 
          <ns1:accountId>1111111111</ns1:accountId> 
          <ns1:accountName>Test Account</ns1:accountName> 
          <ns1:deliveryStatus>ACTIVE</ns1:deliveryStatus> 
        </ns1:operand> 
      </ns1:operations> 
    </ns1:mutate> 
  </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [AccountReturnValue](../data/AccountReturnValue.md) | Container including operation results. | 
##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope
    xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns1="http://im.yahooapis.jp/V6"> 
    <SOAP-ENV:Header> 
        <ns1:ResponseHeader> 
            <ns1:service>AccountService</ns1:service> 
            <ns1:remainingQuota>100</ns1:remainingQuota> 
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest> 
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis> 
        </ns1:ResponseHeader> 
    </SOAP-ENV:Header> 
    <SOAP-ENV:Body> 
        <ns1:mutateResponse> 
            <ns1:rval> 
                <ns1:ListReturnValue.Type>AccountReturnValue</ns1:ListReturnValue.Type> 
                <ns1:Operation.Type>SET</ns1:Operation.Type> 
                <ns1:values> 
                    <ns1:operationSucceeded>true</ns1:operationSucceeded> 
                    <ns1:account> 
                        <ns1:accountId>1000000000</ns1:accountId> 
                        <ns1:accountName>Test Account</ns1:accountName> 
                        <ns1:accountType>INVOICE</ns1:accountType> 
                        <ns1:accountStatus>SERVING</ns1:accountStatus> 
                        <ns1:deliveryStatus>ACTIVE</ns1:deliveryStatus> 
                        <ns1:budget> 
                            <ns1:amount>1000000</ns1:amount> 
                            <ns1:limitChargeType>SUM</ns1:limitChargeType> 
                            <ns1:startDate>20091130</ns1:startDate> 
                            <ns1:endDate>20100120</ns1:endDate> 
                        </ns1:budget> 
                    </ns1:account> 
                </ns1:values> 
            </ns1:rval> 
        </ns1:mutateResponse> 
    </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

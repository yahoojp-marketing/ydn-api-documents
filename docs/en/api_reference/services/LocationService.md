# LocationService
LocationService retrieves account location information.
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/Vx.x/LocationService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/Vx.x/LocationService?wsdl|
#### Namespace
http://im.yahooapis.jp/V5
#### Service Overview
When requesting a Web service, first use LocationService, then acquire an account co-location. <br>
Next, use the URL prefix from the acquired co-location to create a local URL, and request the Web service. <br>
For the LocationService itself, use the main URL posted in the LocationService's WSDL
#### Operation
##### When using LocationService
Use the main URL to send a request for LocationService.<br>
The main URL is included in the LocationService's WSDL.
##### When using other Web services
Use a local URL to send a request. <br>
To create a local URL, you must use LocationService, and acquire the URL prefix for the co-location allotted to the account.<br>
After, combine the URL prefix with the current version and specific service name, then create the local URL. <br>
<br>
A valid period for the location information has not determined, but it will not change often, so it does not have to be acquired during each process. <br>
If invalid, an Invalid Location error occurs. <br>
In this case, it must be acquired again.

## get
### Request

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| accountId | ○ | xsd:long | An account ID. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:get>
      <ns1:accountId>1000000001</ns1:accountId>
    </ns1:get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Field

| Parameter | Data Type | Description | 
|---|---|---|
| rval | [LocationReturnValue](../data/LocationReturnValue.md) | Container holding location information, including operation results. | error | [Error](../data/Error.md) | An error. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>LocationService</ns1:service>
      <ns1:remainingQuota>4999</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.3899</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getResponse>
      <ns1:rval>
        <ns1:operationSucceeded>true</ns1:operationSucceeded>
        <ns1:value>colo01.im.yahooapis.jp</ns1:value>
      </ns1:rval>
    </ns1:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

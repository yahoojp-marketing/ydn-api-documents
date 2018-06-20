# LocationService
LocationService retrieves account location information.
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201806/LocationService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201806/LocationService?wsdl |
#### Namespace
http://im.yahooapis.jp/V201806/Location
#### Service Overview
When requesting a Web service, first use LocationService, then acquire an account co-location. <br>
Next, use the URL prefix from the acquired co-location to create a local URL, and request the Web service. <br>
For the LocationService itself, use the main URL posted in the LocationService's WSDL
#### Operation

+ [get](#get)

#### Object
[Location](../data/Location)

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
| accountId | required | xsd:long | An account ID. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201806/Location" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201806/Location">
      <accountId>1234567890</accountId>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Field

| Parameter | Data Type | Description |
|---|---|---|
| rval | [LocationReturnValue](../data/Location/LocationReturnValue.md) | Container holding location information, including operation results. | error | [Error](../data/Common/Error.md) | An error. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201806/Location" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:service>Location</ns2:service>
      <ns2:requestTime>1528278912485</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201806" xmlns:ns2="http://im.yahooapis.jp/V201806/Location">
      <ns2:rval>
        <operationSucceeded>true</operationSucceeded>
        <ns2:value>https://im.yahooapis.jp/test</ns2:value>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

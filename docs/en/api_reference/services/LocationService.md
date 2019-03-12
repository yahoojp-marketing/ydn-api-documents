# LocationService
LocationService retrieves account location information.
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201903/LocationService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201903/LocationService?wsdl |
#### Namespace
http://im.yahooapis.jp/V201903/Location
#### Service Overview
Provides the URL prefix for the colocation your account is assigned to.<br>
Requesting URL differs from other Services.

#### Operation

#### For LocationService
Use the main URL to send a request.<br>
Main URL is included in the LocationService's WSDL.

#### For other Services
Use a local URL to send a request.<br>
To create local URL:<br>
　1. Retrieve the URL prefix of assigned co-location.<br>
　2. Combine the URL prefix with the available version and Service name.<br>

*A valid period of location information is not determined.<br>
 It will not change frequently, so retrieve again when invalid error returns.

+ [get](#get)

#### Object
[Location](../data/Location)

## get
Retrieves the URL prefix of location of targeted account.

### Request

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| accountId | required | xsd:long | An account ID. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/Location" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201903/Location">
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
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/Location" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>Location</ns2:service>
      <ns2:requestTime>1551686142128</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/Location">
      <ns2:rval>
        <operationSucceeded>true</operationSucceeded>
        <ns2:value>https://im.yahooapis.jp/test</ns2:value>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

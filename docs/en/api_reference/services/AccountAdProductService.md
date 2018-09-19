# AccountAdProductService
AccountAdProductService provides the list of ad display methods.
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201809/AccountAdProductService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201809/AccountAdProductService?wsdl |
#### Namespace
http://im.yahooapis.jp/V201809/AccountAdProduct
#### Service Overview
AccountAdProductService searves the list of Ad display method.
#### Operation
Explains the control providing from AccountAdProductService.

+ [get](#get)

#### Object
[AccountAdProduct](../data/AccountAdProduct)

## get

### Request
Gets the ad display method that is available from account.

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| selector | required | [AccountAdProductSelector](../data/AccountAdProduct/AccountAdProductSelector.md) | Retrieve the ad display method available on account. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201809/AccountAdProduct" xmlns:ns2="http://im.yahooapis.jp/V201809">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201809/AccountAdProduct">
      <selector>
        <accountIds>1111</accountIds>
        <accountIds>2222</accountIds>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [AccountAdProductPage](../data/AccountAdProduct/AccountAdProductPage.md) | Container including operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201809/AccountAdProduct" xmlns:ns2="http://im.yahooapis.jp/V201809">
      <ns2:service>AccountAdProduct</ns2:service>
      <ns2:requestTime>1536568315540</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201809" xmlns:ns2="http://im.yahooapis.jp/V201809/AccountAdProduct">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:accountAdProduct>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:adProduct>
              <ns2:adProductType>INTEREST_MATCH</ns2:adProductType>
            </ns2:adProduct>
            <ns2:adProduct>
              <ns2:adProductType>VIDEO_AD</ns2:adProductType>
            </ns2:adProduct>
          </ns2:accountAdProduct>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

# BalanceService
Use this service to retrieve account balance
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201809/BalanceService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201809/BalanceService?wsdl |
#### Namespace
http://im.yahooapis.jp/V201809/Balance
#### Service Overview
Offers a budget acquisition function.
#### Operation
Describes operations provided by BalanceService.

+ [get](#get)

#### オブジェクト
[Balance](../data/Balance)

## get

### Request
Defines a budget acquisition target.

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| selector | required | [BalanceSelector](../data/Balance/BalanceSelector.md) | Defines a target to acquire a budget.  |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201809/Balance" xmlns:ns2="http://im.yahooapis.jp/V201809">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201809/Balance">
      <selector>
        <accountId>1111</accountId>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [BalancePage](../data/Balance/BalancePage.md) | A container that stores results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201809/Balance" xmlns:ns2="http://im.yahooapis.jp/V201809">
      <ns2:service>Balance</ns2:service>
      <ns2:requestTime>1536568321788</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201809" xmlns:ns2="http://im.yahooapis.jp/V201809/Balance">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:balance>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:balance>10000</ns2:balance>
          </ns2:balance>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

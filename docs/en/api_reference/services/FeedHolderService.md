# FeedHolderService
FeedHolderService provides functions to get, add, update or remove FeedHolder information.

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201812/FeedHolderService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201812/FeedHolderService?wsdl |

#### Namespace
http://im.yahooapis.jp/V201812/FeedHolder

#### Overview
Use this service to get, add, update or remove FeedHolder.

#### Operation
Describes the operation which provides by FeedHolderService.

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)

#### Object
[FeedHolder](../data/FeedHolder)

## get
Returns FeedHolder information.

#### Request
| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| selector | Req | [FeedHolderSelector](../data/FeedHolder/FeedHolderSelector.md) | Acquisition condition of FeedHolder |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201812/FeedHolder" xmlns:ns2="http://im.yahooapis.jp/V201812">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201812/FeedHolder" xmlns:ns2="http://im.yahooapis.jp/V201812">
      <selector>
        <accountId>1111</accountId>
        <feedHolderIds>222</feedHolderIds>
        <feedHolderIds>333</feedHolderIds>
        <feedHolderIds>444</feedHolderIds>
        <feedHolderIds>555</feedHolderIds>
        <feedHolderIds>666</feedHolderIds>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>10</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [FeedHolderPage](../data/FeedHolder/FeedHolderPage.md) | FeedHolder information that matches acquisition conditions |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201812/FeedHolder" xmlns:ns2="http://im.yahooapis.jp/V201812">
      <ns2:service>FeedHolder</ns2:service>
      <ns2:requestTime>1531887958474</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201812" xmlns:ns2="http://im.yahooapis.jp/V201812/FeedHolder">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedHolder>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:feedHolderId>2222</ns2:feedHolderId>
            <ns2:feedHolderName>testFeedHolder</ns2:feedHolderName>
            <ns2:itemCount>1</ns2:itemCount>
            <ns2:approvedItemCount>2</ns2:approvedItemCount>
            <ns2:disApprovedItemCount>3</ns2:disApprovedItemCount>
          </ns2:feedHolder>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
Add the FeedHolder information.

#### Request
| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| operations | Req | [FeedHolderOperation](../data/FeedHolder/FeedHolderOperation.md) | FeedHolder information to be registered |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201812/FeedHolder" xmlns:ns2="http://im.yahooapis.jp/V201812">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201812/FeedHolder">
      <operations>
        <operator>ADD</operator>
        <accountId>1111</accountId>
        <operand>
          <accountId>1111</accountId>
          <feedHolderName>testFeedHolder</feedHolderName>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [FeedHolderReturnValue](../data/FeedHolder/FeedHolderReturnValue.md) | Registration result |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201812/FeedHolder" xmlns:ns2="http://im.yahooapis.jp/V201812">
      <ns2:service>FeedHolder</ns2:service>
      <ns2:requestTime>1531887960345</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201812" xmlns:ns2="http://im.yahooapis.jp/V201812/FeedHolder">
      <ns2:rval>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedHolder>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:feedHolderId>2222</ns2:feedHolderId>
            <ns2:feedHolderName>testFeedHolder</ns2:feedHolderName>
          </ns2:feedHolder>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
Update the FeedHolder information.

#### Request
| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| operations | Req | [FeedHolderOperation](../data/FeedHolder/FeedHolderOperation.md) | FeedHolder information to be registered |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201812/FeedHolder" xmlns:ns2="http://im.yahooapis.jp/V201812">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201812/FeedHolder">
      <operations>
        <operator>SET</operator>
        <accountId>1111</accountId>
        <operand>
          <accountId>1111</accountId>
          <feedHolderId>2222</feedHolderId>
          <feedHolderName>testFeedHolder</feedHolderName>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [FeedHolderReturnValue](../data/FeedHolder/FeedHolderReturnValue.md) | Registration result |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201812/FeedHolder" xmlns:ns2="http://im.yahooapis.jp/V201812">
      <ns2:service>FeedHolder</ns2:service>
      <ns2:requestTime>1531887960442</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201812" xmlns:ns2="http://im.yahooapis.jp/V201812/FeedHolder">
      <ns2:rval>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedHolder>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:feedHolderId>2222</ns2:feedHolderId>
            <ns2:feedHolderName>testFeedHolder</ns2:feedHolderName>
          </ns2:feedHolder>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
Remove the FeedHolder information.

#### Request
| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| operations | Req | [FeedHolderOperation](../data/FeedHolder/FeedHolderOperation.md) | FeedHolder information to be registered |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201812/FeedHolder" xmlns:ns2="http://im.yahooapis.jp/V201812">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201812/FeedHolder">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1111</accountId>
        <operand>
          <accountId>1111</accountId>
          <feedHolderId>2222</feedHolderId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [FeedHolderReturnValue](../data/FeedHolder/FeedHolderReturnValue.md) | Registration result |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201812/FeedHolder" xmlns:ns2="http://im.yahooapis.jp/V201812">
      <ns2:service>FeedHolder</ns2:service>
      <ns2:requestTime>1531887960540</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201812" xmlns:ns2="http://im.yahooapis.jp/V201812/FeedHolder">
      <ns2:rval>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedHolder>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:feedHolderId>2222</ns2:feedHolderId>
            <ns2:feedHolderName>testFeedHolder</ns2:feedHolderName>
          </ns2:feedHolder>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

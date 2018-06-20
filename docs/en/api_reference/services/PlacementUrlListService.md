# PlacementUrlListService
In PlacementUrlListService, acquiring, creating, updating and deleting Placement URL list will be done.
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201806/PlacementUrlListService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201806/PlacementUrlListService?wsdl |
#### Namespace
http://im.yahooapis.jp/V201806/PlacementUrlList
#### Service Overview
In PlacementUrlListService, acquiring, creating, updating and deleting Placement URL list will be done.
#### Operation
Explains the control providing from PlacementUrlListService.

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)

#### Object
[PlacementUrlList](../data/PlacementUrlList)

## get

### Request
Request Body’s Parameter

| name | type | Requirement | Description |
|---|---|---|---|
| selector | [PlacementUrlListSelector](../data/PlacementUrlList/PlacementUrlListSelector.md) | required |  |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201806/PlacementUrlList" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201806/PlacementUrlList" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <selector>
        <accountId>111111</accountId>
        <urlListIds>222222</urlListIds>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>10</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| name | type | Requirement | Description |
|---|---|---|---|
| rval | [PlacementUrlListPage](../data/PlacementUrlList/PlacementUrlListPage.md) |  |  |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201806/PlacementUrlList" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:service>PlacementUrlList</ns2:service>
      <ns2:requestTime>1528278914107</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201806" xmlns:ns2="http://im.yahooapis.jp/V201806/PlacementUrlList">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:urlList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:urlListId>22222222</ns2:urlListId>
            <ns2:urlListName>TEST_LIST</ns2:urlListName>
            <ns2:description>TEST_DESCRIPTION</ns2:description>
            <ns2:isUnknownDomain>FALSE</ns2:isUnknownDomain>
            <ns2:urls>
              <ns2:placementUrl>yahoo.co.jp</ns2:placementUrl>
              <ns2:activeFlg>ACTIVE</ns2:activeFlg>
            </ns2:urls>
          </ns2:urlList>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)

### Request
Request Body’s Parameter.

| name | type | Requirement | Description |
|---|---|---|---|
| perations | [PlacementUrlListOperation](../data/PlacementUrlList/PlacementUrlListOperation.md) | required |  |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201806/PlacementUrlList" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201806/PlacementUrlList">
      <operations>
        <operator>ADD</operator>
        <accountId>1111</accountId>
        <operand>
          <accountId>1111</accountId>
          <urlListName>TestList</urlListName>
          <description>TestDataDesc</description>
          <isUnknownDomain>FALSE</isUnknownDomain>
          <urls>
            <placementUrl>yahoo.co.jp</placementUrl>
          </urls>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| name | type | Requirement | Description |
|---|---|---|---|
| rval | [PlacementUrlListReturnValue](../data/PlacementUrlList/PlacementUrlListReturnValue.md) |  |  |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201806/PlacementUrlList" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:service>PlacementUrlList</ns2:service>
      <ns2:requestTime>1528278914142</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201806" xmlns:ns2="http://im.yahooapis.jp/V201806/PlacementUrlList">
      <ns2:rval>
        <ListReturnValue.Type>PlacementUrlListReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:urlList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:urlListId>22222222</ns2:urlListId>
            <ns2:urlListName>TEST_LIST</ns2:urlListName>
            <ns2:description>TEST_DESCRIPTION</ns2:description>
            <ns2:isUnknownDomain>FALSE</ns2:isUnknownDomain>
            <ns2:urls>
              <ns2:placementUrl>yahoo.co.jp</ns2:placementUrl>
              <ns2:activeFlg>ACTIVE</ns2:activeFlg>
            </ns2:urls>
          </ns2:urlList>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)

### Request

| name | type | Requirement | Description |
|---|---|---|---|
| operations | [PlacementUrlListOperation](../data/PlacementUrlList/PlacementUrlListOperation.md) | required |  |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201806/PlacementUrlList" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201806/PlacementUrlList">
      <operations>
        <operator>SET</operator>
        <accountId>11111</accountId>
        <operand>
          <accountId>1111</accountId>
          <urlListId>22222222</urlListId>
          <urlListName>ChangeTestList</urlListName>
          <description>ChangeTestDataDesc</description>
          <isUnknownDomain>TRUE</isUnknownDomain>
          <urls>
            <placementUrl>yahoo1.co.jp</placementUrl>
          </urls>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| name | type | Requirement | Description |
|---|---|---|---|
| rval | [PlacementUrlListReturnValue](../data/PlacementUrlList/PlacementUrlListReturnValue.md) |  |  |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201806/PlacementUrlList" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:service>PlacementUrlList</ns2:service>
      <ns2:requestTime>1528278914177</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201806" xmlns:ns2="http://im.yahooapis.jp/V201806/PlacementUrlList">
      <ns2:rval>
        <ListReturnValue.Type>PlacementUrlListReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:urlList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:urlListId>22222222</ns2:urlListId>
            <ns2:urlListName>ChangeTestList</ns2:urlListName>
            <ns2:description>ChangeTestDataDesc</ns2:description>
            <ns2:isUnknownDomain>TRUE</ns2:isUnknownDomain>
            <ns2:urls>
              <ns2:placementUrl>yahoo1.co.jp</ns2:placementUrl>
              <ns2:activeFlg>ACTIVE</ns2:activeFlg>
            </ns2:urls>
          </ns2:urlList>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)

### Request

| name | type | Requirement | Description |
|---|---|---|---|
| operations | [PlacementUrlListOperation](../data/PlacementUrlList/PlacementUrlListOperation.md) | required |  |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201806/PlacementUrlList" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201806/PlacementUrlList">
      <operations>
        <operator>REMOVE</operator>
        <accountId>111111</accountId>
        <operand>
          <accountId>111111</accountId>
          <urlListId>222222</urlListId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| name | type | Requirement | Description |
|---|---|---|---|
| rval | [PlacementUrlListReturnValue](../data/PlacementUrlList/PlacementUrlListReturnValue.md) |  |  |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201806/PlacementUrlList" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:service>PlacementUrlList</ns2:service>
      <ns2:requestTime>1528278914213</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201806" xmlns:ns2="http://im.yahooapis.jp/V201806/PlacementUrlList">
      <ns2:rval>
        <ListReturnValue.Type>PlacementUrlListReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:urlList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:urlListId>22222222</ns2:urlListId>
            <ns2:urlListName>ChangeTestList</ns2:urlListName>
            <ns2:description>ChangeTestDataDesc</ns2:description>
            <ns2:isUnknownDomain>TRUE</ns2:isUnknownDomain>
            <ns2:urls>
              <ns2:placementUrl>yahoo1.co.jp</ns2:placementUrl>
              <ns2:activeFlg>ACTIVE</ns2:activeFlg>
            </ns2:urls>
          </ns2:urlList>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

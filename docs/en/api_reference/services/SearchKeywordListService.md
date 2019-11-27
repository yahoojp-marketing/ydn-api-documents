# SearchKeywordListService
SearchKeywordListService retrieves, add, update, and delete the search keyword list.<br>
It can set up to 500 keywords per list. <br>
It can set up to 100 lists per account.

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201911/SearchKeywordListService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201911/SearchKeywordListService?wsdl |
#### Namespace
http://im.yahooapis.jp/V201911/SearchKeywordList
#### Service Overview
Use this service for operation of search keyword list.
#### Operation
Explains operations provided by SearchKeywordListService.

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)

#### Object
[SearchKeywordList](../data/SearchKeywordList)

## get

### Request
Retrieces the search keyeord list.

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| selector | required | [SearchKeywordListSelector](../data/SearchKeywordList/SearchKeywordListSelector.md) | Retrives the search keyword list. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/SearchKeywordList" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201911/SearchKeywordList" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <selector>
        <accountId>11111</accountId>
        <searchKeywordListIds>22222</searchKeywordListIds>
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
| Parameter | Data Type | Description |
|---|---|---|
| rval | [SearchKeywordListPage](../data/SearchKeywordList/SearchKeywordListPage.md) | A container that stores results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/SearchKeywordList" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>SearchKeywordList</ns2:service>
      <ns2:requestTime>1574394495222</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/SearchKeywordList">
      <ns2:rval>
        <totalNumEntries>4</totalNumEntries>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:searchKeywordList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:searchKeywordListId>22222222</ns2:searchKeywordListId>
            <ns2:searchKeywordListName>TEST_SEARCH_KEYWORD</ns2:searchKeywordListName>
            <ns2:searchKeywordListDescription>TEST_SEARCH_DESCRIPTION</ns2:searchKeywordListDescription>
            <ns2:searchKeywordRecency>WITHIN_30DAYS</ns2:searchKeywordRecency>
            <ns2:searchKeywordFrequency>ONCE_OR_MORE</ns2:searchKeywordFrequency>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:searchKeyword>
              <ns2:searchKeywordId>22222</ns2:searchKeywordId>
            </ns2:searchKeyword>
          </ns2:searchKeywordList>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)

### Request
Add the search keyword list.

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| operations | ○ | [SearchKeywordListOperation](../data/SearchKeywordList/SearchKeywordListOperation.md) | Add the search keyword list.|

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/SearchKeywordList" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201911/SearchKeywordList">
      <operations>
        <operator>ADD</operator>
        <accountId>1234</accountId>
        <operand>
          <accountId>1234</accountId>
          <searchKeywordListName>TEST_SEARCH_KEYWORD</searchKeywordListName>
          <searchKeywordListDescription>TEST_SEARCH_DESCRIPTION</searchKeywordListDescription>
          <searchKeywordRecency>WITHIN_30DAYS</searchKeywordRecency>
          <searchKeywordFrequency>TWICE_OR_MORE</searchKeywordFrequency>
          <searchKeyword>
            <searchKeywordId>555555</searchKeywordId>
          </searchKeyword>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [SearchKeywordListReturnValue](../data/SearchKeywordList/SearchKeywordListReturnValue.md) | A container that stores results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/SearchKeywordList" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>SearchKeywordList</ns2:service>
      <ns2:requestTime>1574394495248</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/SearchKeywordList">
      <ns2:rval>
        <ListReturnValue.Type>SearchKeywordListReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:searchKeywordList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:searchKeywordListId>1111111</ns2:searchKeywordListId>
            <ns2:searchKeywordListName>TEST_SEARCH_KEYWORD</ns2:searchKeywordListName>
            <ns2:searchKeywordListDescription>TEST_SEARCH_DESCRIPTION</ns2:searchKeywordListDescription>
            <ns2:searchKeywordRecency>WITHIN_30DAYS</ns2:searchKeywordRecency>
            <ns2:searchKeywordFrequency>ONCE_OR_MORE</ns2:searchKeywordFrequency>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:searchKeyword>
              <ns2:searchKeywordId>22222</ns2:searchKeywordId>
            </ns2:searchKeyword>
          </ns2:searchKeywordList>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)

### Request
Set the search keyword list to be updated.

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| operations | ○ | [SearchKeywordListOperation](../data/SearchKeywordList/SearchKeywordListOperation.md) | Set the search keyword list to be updated. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/SearchKeywordList" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201911/SearchKeywordList">
      <operations>
        <operator>SET</operator>
        <accountId>11111</accountId>
        <operand>
          <accountId>11111</accountId>
          <searchKeywordListId>22222</searchKeywordListId>
          <searchKeywordListName>Change Name</searchKeywordListName>
          <searchKeywordListDescription>Change Description</searchKeywordListDescription>
          <searchKeywordRecency>WITHIN_1DAY</searchKeywordRecency>
          <searchKeywordFrequency>THREE_TIMES_OR_MORE</searchKeywordFrequency>
          <searchKeyword>
            <searchKeywordId>555555555</searchKeywordId>
          </searchKeyword>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [SearchKeywordListReturnValue](../data/SearchKeywordList/SearchKeywordListReturnValue.md) | A container that stores operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/SearchKeywordList" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>SearchKeywordList</ns2:service>
      <ns2:requestTime>1574394495290</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/SearchKeywordList">
      <ns2:rval>
        <ListReturnValue.Type>SearchKeywordListReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:searchKeywordList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:searchKeywordListId>1111111</ns2:searchKeywordListId>
            <ns2:searchKeywordListName>Change Name</ns2:searchKeywordListName>
            <ns2:searchKeywordListDescription>Change Description</ns2:searchKeywordListDescription>
            <ns2:searchKeywordRecency>WITHIN_1DAY</ns2:searchKeywordRecency>
            <ns2:searchKeywordFrequency>THREE_TIMES_OR_MORE</ns2:searchKeywordFrequency>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:searchKeyword>
              <ns2:searchKeywordId>555555</ns2:searchKeywordId>
            </ns2:searchKeyword>
          </ns2:searchKeywordList>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)

### Request
Removes the search keyword list.

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| operations | ○ | [SearchKeywordListOperation](../data/SearchKeywordList/SearchKeywordListOperation.md) |  Removes the search keyword list. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/SearchKeywordList" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201911/SearchKeywordList">
      <operations>
        <operator>REMOVE</operator>
        <accountId>111111</accountId>
        <operand>
          <accountId>111111</accountId>
          <searchKeywordListId>222222</searchKeywordListId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [SearchKeywordListReturnValue](../data/SearchKeywordList/SearchKeywordListReturnValue.md) | A container that stores results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/SearchKeywordList" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>SearchKeywordList</ns2:service>
      <ns2:requestTime>1574394495325</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/SearchKeywordList">
      <ns2:rval>
        <ListReturnValue.Type>SearchKeywordListReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:searchKeywordList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:searchKeywordListId>1111111</ns2:searchKeywordListId>
            <ns2:searchKeywordListName>TEST_SEARCH_KEYWORD</ns2:searchKeywordListName>
            <ns2:searchKeywordListDescription>TEST_SEARCH_DESCRIPTION</ns2:searchKeywordListDescription>
            <ns2:searchKeywordRecency>WITHIN_30DAYS</ns2:searchKeywordRecency>
            <ns2:searchKeywordFrequency>ONCE_OR_MORE</ns2:searchKeywordFrequency>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:searchKeyword>
              <ns2:searchKeywordId>22222</ns2:searchKeywordId>
            </ns2:searchKeyword>
          </ns2:searchKeywordList>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

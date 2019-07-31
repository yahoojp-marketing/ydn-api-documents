# FeedSetService
FeedSetService provides functions to get, add or remove Item Set information.

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201907/FeedSetService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201907/FeedSetService?wsdl |

#### Namespace
http://im.yahooapis.jp/V201907/FeedSet

#### Overview
Use this service to get, add or remove Item Set information.

#### Operation
Describes the operation which provides by FeedSetService.

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(REMOVE)](#mutateremove)

#### Object
[FeedSet](../data/FeedSet)

## get
Retrieves Item Set information.

#### Request
| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| selector | Req | [FeedSetSelector](../data/FeedSet/FeedSetSelector.md) | Acquisition condition of Item Set information |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/FeedSet" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201907/FeedSet">
      <selector>
        <accountId>1234567890</accountId>
        <feedHolderId>10001</feedHolderId>
        <feedSetIds>20001</feedSetIds>
        <feedSetIds>20002</feedSetIds>
        <feedSetIds>20003</feedSetIds>
        <feedSetIds>20004</feedSetIds>
        <feedSetIds>20005</feedSetIds>
        <includeItemCount>true</includeItemCount>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [FeedSetPage](../data/FeedSet/FeedSetPage.md) | Item Set information that matches acquisition conditions |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/FeedSet" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>FeedSet</ns2:service>
      <ns2:requestTime>1552637421581</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/FeedSet">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>FeedSetPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:FeedSet>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:feedHolderId>10001</ns2:feedHolderId>
            <ns2:feedSetId>20001</ns2:feedSetId>
            <ns2:feedSetName>sample feed set.</ns2:feedSetName>
            <ns2:isDefaultSet>false</ns2:isDefaultSet>
            <ns2:conditionSets>
              <ns2:type>CATEGORY_ID</ns2:type>
              <ns2:orConditions>
                <ns2:operator>EQUAL</ns2:operator>
                <ns2:value>sample</ns2:value>
              </ns2:orConditions>
            </ns2:conditionSets>
          </ns2:FeedSet>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
Adds Item Set information.

#### Request
| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| operations | Req | [FeedSetOperation](../data/FeedSet/FeedSetOperation.md) | Item Set information to be registered |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/FeedSet" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201907/FeedSet">
      <operations>
        <operator>ADD</operator>
        <accountId>1234567890</accountId>
        <operand>
          <feedHolderId>10001</feedHolderId>
          <feedSetName>sample feed set.</feedSetName>
          <conditionSets>
            <type>CATEGORY_ID</type>
            <orConditions>
              <operator>EQUAL</operator>
              <value>sample</value>
            </orConditions>
          </conditionSets>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [FeedSetReturnValue](../data/FeedSet/FeedSetReturnValue.md) | Registration result |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/FeedSet" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>FeedSet</ns2:service>
      <ns2:requestTime>1552637421608</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/FeedSet">
      <ns2:rval>
        <ListReturnValue.Type>FeedSetReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:FeedSet>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:feedHolderId>10001</ns2:feedHolderId>
            <ns2:feedSetId>20001</ns2:feedSetId>
            <ns2:feedSetName>sample feed set.</ns2:feedSetName>
            <ns2:isDefaultSet>false</ns2:isDefaultSet>
            <ns2:conditionSets>
              <ns2:type>CATEGORY_ID</ns2:type>
              <ns2:orConditions>
                <ns2:operator>EQUAL</ns2:operator>
                <ns2:value>sample</ns2:value>
              </ns2:orConditions>
            </ns2:conditionSets>
          </ns2:FeedSet>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
Removes Item Set information.

#### Request
| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| operations | Req | [FeedSetOperation](../data/FeedSet/FeedSetOperation.md) | Item Set information to be registered |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/FeedSet" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201907/FeedSet">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1234567890</accountId>
        <operand>
          <feedHolderId>10001</feedHolderId>
          <feedSetId>20001</feedSetId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [FeedSetReturnValue](../data/FeedSet/FeedSetReturnValue.md) | Registration result |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/FeedSet" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>FeedSet</ns2:service>
      <ns2:requestTime>1552637421640</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/FeedSet">
      <ns2:rval>
        <ListReturnValue.Type>FeedSetReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:FeedSet>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:feedHolderId>10001</ns2:feedHolderId>
            <ns2:feedSetId>20001</ns2:feedSetId>
            <ns2:feedSetName>sample feed set.</ns2:feedSetName>
            <ns2:isDefaultSet>false</ns2:isDefaultSet>
            <ns2:conditionSets>
              <ns2:type>CATEGORY_ID</ns2:type>
              <ns2:orConditions>
                <ns2:operator>EQUAL</ns2:operator>
                <ns2:value>sample</ns2:value>
              </ns2:orConditions>
            </ns2:conditionSets>
          </ns2:FeedSet>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

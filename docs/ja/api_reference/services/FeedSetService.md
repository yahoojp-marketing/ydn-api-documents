# FeedSetService
FeedSetServiceでは、商品セット情報の取得、登録、削除を行います。

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201903/FeedSetService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201903/FeedSetService?wsdl |

#### Namespace
http://im.yahooapis.jp/V201903/FeedSet

#### サービス概要
商品セット情報の取得、登録、削除を行います。

#### 操作
提供される操作を説明します。

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(REMOVE)](#mutateremove)

#### オブジェクト
[FeedSet](../data/FeedSet)

## get
商品セット情報を取得します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [FeedSetSelector](../data/FeedSet/FeedSetSelector.md) | 商品セット情報の取得条件 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/FeedSet" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201903/FeedSet">
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

#### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [FeedSetPage](../data/FeedSet/FeedSetPage.md) | 取得条件に合致する商品セット情報 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/FeedSet" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>FeedSet</ns2:service>
      <ns2:requestTime>1552637421478</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/FeedSet">
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
商品セット情報を新規登録します

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| operations | ○ | [FeedSetOperation](../data/FeedSet/FeedSetOperation.md) | 登録対象の商品セット情報 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/FeedSet" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201903/FeedSet">
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

#### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [FeedSetReturnValue](../data/FeedSet/FeedSetReturnValue.md) | 登録結果 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/FeedSet" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>FeedSet</ns2:service>
      <ns2:requestTime>1552637421525</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/FeedSet">
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
商品セット情報を削除します

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| operations | ○ | [FeedSetOperation](../data/FeedSet/FeedSetOperation.md) | 登録対象の商品セット情報 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/FeedSet" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201903/FeedSet">
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

#### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [FeedSetReturnValue](../data/FeedSet/FeedSetReturnValue.md) | 登録結果 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/FeedSet" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>FeedSet</ns2:service>
      <ns2:requestTime>1552637421551</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/FeedSet">
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

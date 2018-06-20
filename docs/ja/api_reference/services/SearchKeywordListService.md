# SearchKeywordListService
SearchKeywordListServiceは、サーチキーワードリストの取得および追加・更新・削除を行います。<br>
1キーワードリストに対して、500件までキーワードが設定可能です。<br>
1アカウントに対して、100件までキーワードリストを登録可能です。

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201806/SearchKeywordListService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201806/SearchKeywordListService?wsdl|
#### Namespace
http://im.yahooapis.jp/V201806/
#### サービス概要
サーチキーワードリストを操作します。
#### 操作
SearchKeywordListServiceで提供される操作を説明します。

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)

#### オブジェクト
[SearchKeywordList](../data/SearchKeywordList)

## get

### リクエスト
サーチキーワードリストを取得します。

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [SearchKeywordListSelector](../data/SearchKeywordList/SearchKeywordListSelector.md) | 取得するサーチキーワードリストを取得します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201806/SearchKeywordList" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201806/SearchKeywordList" xmlns:ns2="http://im.yahooapis.jp/V201806">
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

### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [SearchKeywordListPage](../data/SearchKeywordList/SearchKeywordListPage.md) | 操作結果を含むコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201806/SearchKeywordList" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:service>SearchKeywordList</ns2:service>
      <ns2:requestTime>1528957529191</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201806" xmlns:ns2="http://im.yahooapis.jp/V201806/SearchKeywordList">
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

### リクエスト
サーチキーワードリストを追加します。

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| operations | ○ | [SearchKeywordListOperation](../data/SearchKeywordList/SearchKeywordListOperation.md) | サーチキーワードリストを追加します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201806/SearchKeywordList" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201806/SearchKeywordList">
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

### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [SearchKeywordListReturnValue](../data/SearchKeywordList/SearchKeywordListReturnValue.md) | 操作結果を含むコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201806/SearchKeywordList" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:service>SearchKeywordList</ns2:service>
      <ns2:requestTime>1528957529209</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201806" xmlns:ns2="http://im.yahooapis.jp/V201806/SearchKeywordList">
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

### リクエスト
変更対象のサーチキーワードリストを設定します。

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| operations | ○ | [SearchKeywordListOperation](../data/SearchKeywordList/SearchKeywordListOperation.md) | 変更対象のサーチキーワードリストを設定します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201806/SearchKeywordList" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201806/SearchKeywordList">
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

### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [SearchKeywordListReturnValue](../data/SearchKeywordList/SearchKeywordListReturnValue.md) | 操作結果を含むコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201806/SearchKeywordList" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:service>SearchKeywordList</ns2:service>
      <ns2:requestTime>1528957529227</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201806" xmlns:ns2="http://im.yahooapis.jp/V201806/SearchKeywordList">
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

### リクエスト
サーチキーワードリストを削除します。

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| operations | ○ | [SearchKeywordListOperation](../data/SearchKeywordList/SearchKeywordListOperation.md) | サーチキーワードリストを削除します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201806/SearchKeywordList" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201806/SearchKeywordList">
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

### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [SearchKeywordListReturnValue](../data/SearchKeywordList/SearchKeywordListReturnValue.md) | 操作結果を含むコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201806/SearchKeywordList" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:service>SearchKeywordList</ns2:service>
      <ns2:requestTime>1528957529246</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201806" xmlns:ns2="http://im.yahooapis.jp/V201806/SearchKeywordList">
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

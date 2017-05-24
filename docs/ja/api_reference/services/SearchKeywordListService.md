# SearchKeywordListService
SearchKeywordListServiceは、サーチキーワードリストの取得および追加・更新・削除を行います。<br>
1キーワードリストに対して、500件までキーワードが設定可能です。<br>
1アカウントに対して、100件までキーワードリストを登録可能です。

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/Vx.x/SearchKeywordListService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/Vx.x/SearchKeywordListService?wsdl|
#### Namespace
http://im.yahooapis.jp/V6
#### サービス概要
サーチキーワードリストを操作します。
#### 操作
SearchKeywordListServiceで提供される操作を説明します。

## get
### リクエスト
サーチキーワードリストを取得します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [SearchKeywordListSelector](../data/SearchKeywordListSelector.md) | 取得するサーチキーワードリストを取得します。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
  xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
  xmlns:ns1="http://im.yahooapis.jp/V6"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <SOAP-ENV:Header>
      <ns1:RequestHeader>
         <ns1:license>1111-1111-1111-1111</ns1:license>
         <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
     </ns1:RequestHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:get>
         <ns1:selector>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:searchKeywordListIds>2000000001</ns1:searchKeywordListIds>
            <ns1:searchKeywordListIds>2000000002</ns1:searchKeywordListIds>
            <ns1:paging>
               <ns1:startIndex>1</ns1:startIndex>
               <ns1:numberResults>20</ns1:numberResults>
            </ns1:paging>
         </ns1:selector>
      </ns1:get>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [SearchKeywordListPage](../data/SearchKeywordListPage.md) | 操作結果を含むコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
  xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
  xmlns:ns1="http://im.yahooapis.jp/V6">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>SearchKeywordListService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:getResponse>
         <ns1:rval>
            <ns1:totalNumEntries>2</ns1:totalNumEntries>
            <ns1:Page.Type>SearchKeywordListPage</ns1:Page.Type>
            <ns1:values>
              <ns1:operationSucceeded>true</ns1:operationSucceeded>
              <ns1:searchKeywordList>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:searchKeywordListId>2000000001</ns1:searchKeywordListId>
                  <ns1:searchKeywordListName>Sample01</ns1:searchKeywordListName>
                  <ns1:searchKeywordListDescription>for Test</ns1:searchKeywordListDescription>
                  <ns1:deliveryStatus>PAUSED</ns1:deliveryStatus>
                  <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000001</ns1:searchKeywordId>
                  </ns1:searchKeyword>
                  <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000002</ns1:searchKeywordId>
                  </ns1:searchKeyword>
               </ns1:searchKeywordList>
            </ns1:values>
             <ns1:values>
              <ns1:operationSucceeded>true</ns1:operationSucceeded>
              <ns1:searchKeywordList>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:searchKeywordListId>2000000002</ns1:searchKeywordListId>
                  <ns1:searchKeywordListName>Sample02</ns1:searchKeywordListName>
                  <ns1:searchKeywordListDescription>for Test No2</ns1:searchKeywordListDescription>
                  <ns1:searchKeywordRecency>WITHIN_30DAYS</ns1:searchKeywordRecency>
                  <ns1:searchKeywordFrequency>ONCE_OR_MORE</ns1:searchKeywordFrequency>
                  <ns1:deliveryStatus>ACTIVE</ns1:deliveryStatus>
                  <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000003</ns1:searchKeywordId>
                  </ns1:searchKeyword>           
               </ns1:searchKeywordList>
            </ns1:values>
         </ns1:rval>
     </ns1:getResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```

## mutate(ADD)
### リクエスト
サーチキーワードリストを追加します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [SearchKeywordListOperation](../data/SearchKeywordListOperation.md) | サーチキーワードリストを追加します。 | 

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope
  xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
  xmlns:ns1="http://im.yahooapis.jp/V6">
   <SOAP-ENV:Header>
      <ns1:RequestHeader>
         <ns1:license>1111-1111-1111-1111</ns1:license>
         <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
         <ns1:accountId>100000001</ns1:accountId>
      </ns1:RequestHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:operand>
               <ns1:accountId>1000000001</ns1:accountId>
               <ns1:searchKeywordListName>Sample01</ns1:searchKeywordListName>
               <ns1:searchKeywordListDescription>for Test</ns1:searchKeywordListDescription>
               <ns1:searchKeyword>
                  <ns1:searchKeywordId>3000000001</ns1:searchKeywordId>
               </ns1:searchKeyword>
               <ns1:searchKeyword>
                  <ns1:searchKeywordId>3000000002</ns1:searchKeywordId>
               </ns1:searchKeyword>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>1000000001</ns1:accountId>
               <ns1:searchKeywordListName>Sample02</ns1:searchKeywordListName>
               <ns1:searchKeywordListDescription>for Test No2</ns1:searchKeywordListDescription>
               <ns1:searchKeywordRecency>WITHIN_14DAYS</ns1:searchKeywordRecency>
               <ns1:searchKeywordFrequency>TWICE_OR_MORE</ns1:searchKeywordFrequency>                                   
               <ns1:deliveryStatus>ACTIVE</ns1:deliveryStatus>
               <ns1:searchKeyword>
                  <ns1:searchKeywordId>3000000003</ns1:searchKeywordId>
               </ns1:searchKeyword>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [SearchKeywordListReturnValue](../data/SearchKeywordListReturnValue.md) | 操作結果を含むコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?> 
 <SOAP-ENV:Envelope
   xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
   xmlns:ns1="http://im.yahooapis.jp/V6">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>SearchKeywordListService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>2</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>SearchKeywordListReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>ADD</ns1:Operation.Type>
            <ns1:values>
              <ns1:operationSucceeded>true</ns1:operationSucceeded>
              <ns1:searchKeywordList>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:searchKeywordListId>2000000001</ns1:searchKeywordListId>
                  <ns1:searchKeywordListName>Sample01</ns1:searchKeywordListName>
                  <ns1:searchKeywordListDescription>for Test</ns1:searchKeywordListDescription>
                  <ns1:searchKeywordRecency>WITHIN_30DAYS</ns1:searchKeywordRecency>
                  <ns1:searchKeywordFrequency>ONCE_OR_MORE</ns1:searchKeywordFrequency>
                  <ns1:deliveryStatus>PAUSED</ns1:deliveryStatus>
                  <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000001</ns1:searchKeywordId>
                 </ns1:searchKeyword>
                 <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000002</ns1:searchKeywordId>
                  </ns1:searchKeyword>
               </ns1:searchKeywordList>
            </ns1:values>
            <ns1:values>
              <ns1:operationSucceeded>true</ns1:operationSucceeded>
              <ns1:searchKeywordList>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:searchKeywordListId>2000000002</ns1:searchKeywordListId>
                  <ns1:searchKeywordListName>Sample02</ns1:searchKeywordListName>
                  <ns1:searchKeywordListDescription>for Test No2</ns1:searchKeywordListDescription>
                  <ns1:searchKeywordRecency>WITHIN_14DAYS</ns1:searchKeywordRecency>
                  <ns1:searchKeywordFrequency>TWICE_OR_MORE</ns1:searchKeywordFrequency>
                  <ns1:deliveryStatus>ACTIVE</ns1:deliveryStatus>
                  <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000003</ns1:searchKeywordId>
                  </ns1:searchKeyword>
                  </ns1:searchKeywordList>
            </ns1:values>
         </ns1:rval>
     </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
### リクエスト
変更対象のサーチキーワードリストを設定します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [SearchKeywordListOperation](../data/SearchKeywordListOperation.md) | 変更対象のサーチキーワードリストを設定します。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V6">
   <SOAP-ENV:Header>
      <ns1:RequestHeader>
         <ns1:license>1111-1111-1111-1111</ns1:license>
         <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>SET</ns1:operator>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:operand>
               <ns1:accountId>1000000001</ns1:accountId>
               <ns1:searchKeywordListId>2000000001</ns1:searchKeywordListId>
               <ns1:searchKeywordListName>Sample01 update</ns1:searchKeywordListName>
               <ns1:searchKeywordListDescription>for Test update</ns1:searchKeywordListDescription>
               <ns1:searchKeyword>
                  <ns1:searchKeywordId>3000000001</ns1:searchKeywordId>
               </ns1:searchKeyword>
               <ns1:searchKeyword>
                  <ns1:searchKeywordId>3000000002</ns1:searchKeywordId>
               </ns1:searchKeyword>
               <ns1:searchKeyword>
                  <ns1:searchKeywordId>3000000003</ns1:searchKeywordId>
               </ns1:searchKeyword>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>1000000001</ns1:accountId>
               <ns1:searchKeywordListName>Sample02 update</ns1:searchKeywordListName>
               <ns1:searchKeywordListDescription>for Test No2 update</ns1:searchKeywordListDescription>
               <ns1:searchKeywordRecency>WITHIN_1DAY</ns1:searchKeywordRecency>
               <ns1:searchKeywordFrequency>TWICE_OR_MORE</ns1:searchKeywordFrequency>
               <ns1:searchKeyword>
                  <ns1:searchKeywordId>3000000001</ns1:searchKeywordId>
               </ns1:searchKeyword>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [SearchKeywordListReturnValue](../data/SearchKeywordListReturnValue.md) | 操作結果を含むコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V6">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>SearchKeywordListService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>2</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>SearchKeywordListReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>SET</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:searchKeywordList>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:searchKeywordListId>2000000001</ns1:searchKeywordListId>
                  <ns1:searchKeywordListName>Sample01 Updae</ns1:searchKeywordListName>
                  <ns1:searchKeywordListDescription>for Test Update</ns1:searchKeywordListDescription>
                  <ns1:searchKeywordRecency>WITHIN_30DAYS</ns1:searchKeywordRecency>
                  <ns1:searchKeywordFrequency>ONCE_OR_MORE</ns1:searchKeywordFrequency>
                  <ns1:deliveryStatus>PAUSED</ns1:deliveryStatus>
                  <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000001</ns1:searchKeywordId>
                  </ns1:searchKeyword>
                  <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000002</ns1:searchKeywordId>
                  </ns1:searchKeyword>
                  <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000003</ns1:searchKeywordId>
                  </ns1:searchKeyword>
               </ns1:searchKeywordList>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:searchKeywordList>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:searchKeywordListId>2000000002</ns1:searchKeywordListId>
                  <ns1:searchKeywordListName>Sample02 Update</ns1:searchKeywordListName>
                  <ns1:searchKeywordListDescription>for Test No2 Update</ns1:searchKeywordListDescription>
                  <ns1:searchKeywordRecency>WITHIN_1DAY</ns1:searchKeywordRecency>
                  <ns1:searchKeywordFrequency>TWICE_OR_MORE</ns1:searchKeywordFrequency>
                  <ns1:deliveryStatus>ACTIVE</ns1:deliveryStatus>
                  <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000001</ns1:searchKeywordId>
                  </ns1:searchKeyword>
               </ns1:searchKeywordList>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
### リクエスト
サーチキーワードリストを削除します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [SearchKeywordListOperation](../data/SearchKeywordListOperation.md) | サーチキーワードリストを削除します。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
 <SOAP-ENV:Envelope
   xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
   xmlns:ns1="http://im.yahooapis.jp/V6">
   <SOAP-ENV:Header>
      <ns1:RequestHeader>
         <ns1:license>1111-1111-1111-1111</ns1:license>
         <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>REMOVE</ns1:operator>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:operand>
               <ns1:accountId>1000000001</ns1:accountId>
               <ns1:searchKeywordListId>2000000001</ns1:searchKeywordListId>
           </ns1:operand>
            <ns1:operand>
               <ns1:accountId>1000000001</ns1:accountId>
               <ns1:searchKeywordListId>2000000002</ns1:searchKeywordListId>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [SearchKeywordListReturnValue](../data/SearchKeywordListReturnValue.md) | 操作結果を含むコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
 <SOAP-ENV:Envelope
   xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
   xmlns:ns1="http://im.yahooapis.jp/V6">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>SearchKeywordListService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>2</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>SearchKeywordListReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
            <ns1:values>
              <ns1:operationSucceeded>true</ns1:operationSucceeded>
              <ns1:searchKeywordList>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:searchKeywordListId>2000000001</ns1:searchKeywordListId>
                  <ns1:searchKeywordListName>Sample01</ns1:searchKeywordListName>
                  <ns1:searchKeywordListDescription>for Test</ns1:searchKeywordListDescription>
                  <ns1:deliveryStatus>PAUSED</ns1:deliveryStatus>
                  <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000001</ns1:searchKeywordId>
                 </ns1:searchKeyword>
                 <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000002</ns1:searchKeywordId>
                  </ns1:searchKeyword>
               </ns1:searchKeywordList>
            </ns1:values>
            <ns1:values>
              <ns1:operationSucceeded>true</ns1:operationSucceeded>
              <ns1:searchKeywordList>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:searchKeywordListId>2000000002</ns1:searchKeywordListId>
                  <ns1:searchKeywordListName>Sample02</ns1:searchKeywordListName>
                  <ns1:searchKeywordListDescription>for Test No2</ns1:searchKeywordListDescription>
                  <ns1:searchKeywordRecency>WITHIN_30DAYS</ns1:searchKeywordRecency>
                  <ns1:searchKeywordFrequency>ONCE_OR_MORE</ns1:searchKeywordFrequency>
                  <ns1:deliveryStatus>ACTIVE</ns1:deliveryStatus>
                  <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000003</ns1:searchKeywordId>
                 </ns1:searchKeyword>
                  </ns1:searchKeywordList>
            </ns1:values>
         </ns1:rval>
     </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

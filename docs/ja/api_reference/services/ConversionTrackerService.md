# ConversionTrackerService
ConversionTrackerServiceでは、コンバージョントラッカー情報の取得および追加・更新を行います。

#### WSDL
| environment | url |
|---|---|
| production  | https://im.yahooapis.jp/services/V5.2/ConversionTrackerService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/V5.2/ConversionTrackerService?wsdl|
#### Namespace
http://im.yahooapis.jp/V5
#### サービス概要
コンバージョントラッカー情報の取得およびコンバージョントラッカー情報の追加・更新を行います。
#### 操作
ConversionTrackerServiceで提供される操作を説明します。

## get
### リクエスト
指定アカウントのコンバージョントラッカー情報を取得します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [ConversionTrackerSelector](../data/ConversionTrackerSelector.md) | 操作の対象とするコンバージョントラッカー情報の設定です。 | 

##### ＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>1111-1111-1111-1111</ns1:license>
         <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:get>
         <ns1:selector>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:conversionTrackerIds>2222222</ns1:conversionTrackerIds>
            <ns1:statuses>ENABLED</ns1:statuses>
            <ns1:categories>DEFAULT</ns1:categories>
            <ns1:statsPeriod>REALTIME_TODAY</ns1:statsPeriod>
            <ns1:paging>
               <ns1:startIndex>1</ns1:startIndex>
               <ns1:numberResults>1000</ns1:numberResults>
            </ns1:paging>
         </ns1:selector>
      </ns1:get>
   </soapenv:Body>
</soapenv:Envelope>
```

##### ＜リクエストサンプル＞（代行認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>1111-1111-1111-1111</ns1:license>
         <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
         <ns1:accountId>1000000001</ns1:accountId>
         <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
         <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:get>
         <ns1:selector>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:conversionTrackerIds>2222222</ns1:conversionTrackerIds>
            <ns1:statuses>ENABLED</ns1:statuses>
            <ns1:categories>DEFAULT</ns1:categories>
            <ns1:statsPeriod>REALTIME_TODAY</ns1:statsPeriod>
            <ns1:paging>
               <ns1:startIndex>1</ns1:startIndex>
               <ns1:numberResults>1000</ns1:numberResults>
            </ns1:paging>
         </ns1:selector>
      </ns1:get>
   </soapenv:Body>
</soapenv:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [ConversionTrackerPage](../data/ConversionTrackerPage.md) | 取得されるコンバージョントラッカー情報に関するエントリーです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <ns1:ResponseHeader>
         <ns1:service>ConversionTrackerService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:getResponse>
         <ns1:rval>
            <ns1:totalNumEntries>1</ns1:totalNumEntries>
            <ns1:Page.Type>ConversionTrackerPage</ns1:Page.Type>
            <ns1:totalNumConversionEvents>100</ns1:totalNumConversionEvents>
            <ns1:totalConversionValue>1000</ns1:totalConversionValue>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:conversionTracker xsi:type="ns1:WebConversion">
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:conversionTrackerId>2222222</ns1:conversionTrackerId>
                  <ns1:conversionTrackerName>既存のコンバージョンタグ（Existing Conversion Tag）</ns1:conversionTrackerName>
                  <ns1:status>ENABLED</ns1:status>
                  <ns1:category>DEFAULT</ns1:category>
                  <ns1:numConversionEvents>100</ns1:numConversionEvents>
                  <ns1:conversionValue>1000</ns1:conversionValue>
                  <ns1:mostRecentConversionDate>20140815</ns1:mostRecentConversionDate>
                  <ns1:userRevenueValue>10</ns1:userRevenueValue>
                  <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
                  <ns1:snippet>
                     <ns1:type>JS</ns1:type>
                     <ns1:tag><script type=\"text/javascript\" language=\"javascript\">\n  /* <![CDATA[ */\n  var yahoo_ydn_conv_io = \"XXXXXXXXXXXXXX\";\n  var yahoo_ydn_conv_label = \"\";\n  var yahoo_ydn_conv_transaction_id = \"\";\n  var yahoo_ydn_conv_amount = \"10\";\n  /* ]]> */\n</script>\n<script type=\"text/javascript\" language=\"javascript\" charset=\"UTF-8\" src=\"//b90.yahoo.co.jp/conv.js\"></script></ns1:tag>
                  </ns1:snippet>
                  <ns1:snippet>
                     <ns1:type>IMG</ns1:type>
                     <ns1:tag><img src=\"//b90.yahoo.co.jp/c?yahoo_ydn_conv_io=XXXXXXXXXXXXXX&yahoo_ydn_conv_label=&yahoo_ydn_conv_transaction_id=&yahoo_ydn_conv_amount=10&guid=ON\" width=\"1\" height=\"1\" border=\"0\" /></ns1:tag>
                  </ns1:snippet>
               </ns1:conversionTracker>
            </ns1:values>
         </ns1:rval>
      </ns1:getResponse>
   </soapenv:Body>
</soapenv:Envelope>
```

## mutate(ADD)
### リクエスト
コンバージョントラッカー情報を追加します。

| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [ConversionTrackerOperation](../data/ConversionTrackerOperation.md) | 操作の対象となるコンバージョントラッカー情報および操作の内容を表します。 | 

##### ＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>1111-1111-1111-1111</ns1:license>
         <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:operand xsi:type="ns1:WebConversion">
               <ns1:accountId>1000000001</ns1:accountId>
               <ns1:conversionTrackerName>?</ns1:conversionTrackerName>
               <ns1:status>ENABLED</ns1:status>
               <ns1:category>DEFAULT</ns1:category>
               <ns1:userRevenueValue>10</ns1:userRevenueValue>
               <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

##### ＜リクエストサンプル＞（代行認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>1111-1111-1111-1111</ns1:license>
         <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
         <ns1:accountId>1000000001</ns1:accountId>
         <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
         <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:operand xsi:type="ns1:WebConversion">
               <ns1:accountId>1000000001</ns1:accountId>
               <ns1:conversionTrackerName>?</ns1:conversionTrackerName>
               <ns1:status>ENABLED</ns1:status>
               <ns1:category>DEFAULT</ns1:category>
               <ns1:userRevenueValue>10</ns1:userRevenueValue>
               <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [ConversionTrackerReturnValue](../data/ConversionTrackerReturnValue.md) | 操作結果を含むコンバージョントラッカー情報のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <ns1:ResponseHeader>
         <ns1:service>ConversionTrackerService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>ConversionTrackerReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>ADD</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:conversionTracker xsi:type="ns1:WebConversion">
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:conversionTrackerId>2222222</ns1:conversionTrackerId>
                  <ns1:conversionTrackerName>既存のコンバージョンタグ（Existing Conversion Tag）</ns1:conversionTrackerName>
                  <ns1:status>ENABLED</ns1:status>
                  <ns1:category>DEFAULT</ns1:category>
                  <ns1:numConversionEvents>100</ns1:numConversionEvents>
                  <ns1:conversionValue>1000</ns1:conversionValue>
                  <ns1:mostRecentConversionDate>20140815</ns1:mostRecentConversionDate>
                  <ns1:userRevenueValue>10</ns1:userRevenueValue>
                  <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
                  <ns1:snippet>
                     <ns1:type>JS</ns1:type>
                     <ns1:tag><script type=\"text/javascript\" language=\"javascript\">\n  /* <![CDATA[ */\n  var yahoo_ydn_conv_io = \"XXXXXXXXXXXXXX\";\n  var yahoo_ydn_conv_label = \"\";\n  var yahoo_ydn_conv_transaction_id = \"\";\n  var yahoo_ydn_conv_amount = \"10\";\n  /* ]]> */\n</script>\n<script type=\"text/javascript\" language=\"javascript\" charset=\"UTF-8\" src=\"//b90.yahoo.co.jp/conv.js\"></script></ns1:tag>
                  </ns1:snippet>
                  <ns1:snippet>
                     <ns1:type>IMG</ns1:type>
                     <ns1:tag><img src=\"//b90.yahoo.co.jp/c?yahoo_ydn_conv_io=XXXXXXXXXXXXXX&yahoo_ydn_conv_label=&yahoo_ydn_conv_transaction_id=&yahoo_ydn_conv_amount=10&guid=ON\" width=\"1\" height=\"1\" border=\"0\" /></ns1:tag>
                  </ns1:snippet>
               </ns1:conversionTracker>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </soapenv:Body>
</soapenv:Envelope>
```

## mutate(SET)
### リクエスト
コンバージョントラッカー情報を更新します。

| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [ConversionTrackerOperation](../data/ConversionTrackerOperation.md) | 操作の対象となるコンバージョントラッカー設定および操作の内容を表します。 | 

##### ＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>1111-1111-1111-1111</ns1:license>
         <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>SET</ns1:operator>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:operand xsi:type="ns1:WebConversion">
               <ns1:accountId>1000000001</ns1:accountId>
               <ns1:conversionTrackerId>2222222</ns1:conversionTrackerId>
               <ns1:conversionTrackerName>?</ns1:conversionTrackerName>
               <ns1:status>ENABLED</ns1:status>
               <ns1:category>DEFAULT</ns1:category>
               <ns1:userRevenueValue>10</ns1:userRevenueValue>
               <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

##### ＜リクエストサンプル＞（代行認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>1111-1111-1111-1111</ns1:license>
         <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
         <ns1:accountId>1000000001</ns1:accountId>
         <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
         <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>SET</ns1:operator>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:operand xsi:type="ns1:WebConversion">
               <ns1:accountId>1000000001</ns1:accountId>
               <ns1:conversionTrackerId>2222222</ns1:conversionTrackerId>
               <ns1:conversionTrackerName>?</ns1:conversionTrackerName>
               <ns1:status>ENABLED</ns1:status>
               <ns1:category>DEFAULT</ns1:category>
               <ns1:userRevenueValue>10</ns1:userRevenueValue>
               <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [ConversionTrackerReturnValue](../data/ConversionTrackerReturnValue.md) | 操作結果を含むコンバージョントラッカー設定に関する情報のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <ns1:ResponseHeader>
         <ns1:service>ConversionTrackerService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>ConversionTrackerReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>SET</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:conversionTracker xsi:type="ns1:WebConversion">
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:conversionTrackerId>2222222</ns1:conversionTrackerId>
                  <ns1:conversionTrackerName>既存のコンバージョンタグ（Existing Conversion Tag）</ns1:conversionTrackerName>
                  <ns1:status>ENABLED</ns1:status>
                  <ns1:category>DEFAULT</ns1:category>
                  <ns1:numConversionEvents>100</ns1:numConversionEvents>
                  <ns1:conversionValue>1000</ns1:conversionValue>
                  <ns1:mostRecentConversionDate>20140815</ns1:mostRecentConversionDate>
                  <ns1:userRevenueValue>10</ns1:userRevenueValue>
                  <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
                  <ns1:snippet>
                     <ns1:type>JS</ns1:type>
                     <ns1:tag><script type=\"text/javascript\" language=\"javascript\">\n  /* <![CDATA[ */\n  var yahoo_ydn_conv_io = \"XXXXXXXXXXXXXX\";\n  var yahoo_ydn_conv_label = \"\";\n  var yahoo_ydn_conv_transaction_id = \"\";\n  var yahoo_ydn_conv_amount = \"10\";\n  /* ]]> */\n</script>\n<script type=\"text/javascript\" language=\"javascript\" charset=\"UTF-8\" src=\"//b90.yahoo.co.jp/conv.js\"></script></ns1:tag>
                  </ns1:snippet>
                  <ns1:snippet>
                     <ns1:type>IMG</ns1:type>
                     <ns1:tag><img src=\"//b90.yahoo.co.jp/c?yahoo_ydn_conv_io=XXXXXXXXXXXXXX&yahoo_ydn_conv_label=&yahoo_ydn_conv_transaction_id=&yahoo_ydn_conv_amount=10&guid=ON\" width=\"1\" height=\"1\" border=\"0\" /></ns1:tag>
                  </ns1:snippet>
               </ns1:conversionTracker>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </soapenv:Body>
</soapenv:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

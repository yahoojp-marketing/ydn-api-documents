# ConversionTrackerService
ConversionTrackerServiceでは、コンバージョントラッカー情報の操作（取得、追加、更新）を行います。

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/Vx.x/ConversionTrackerService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/Vx.x/ConversionTrackerService?wsdl |

#### Namespace
http://im.yahooapis.jp/V6

#### サービス概要
コンバージョントラッカー情報の取得およびコンバージョントラッカー情報の追加・更新を行います。

#### 操作
ConversionTrackerServiceで提供される操作を説明します。

## get
### リクエスト
指定アカウントのコンバージョントラッカー情報を取得します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [ConversionTrackerSelector](../data/ConversionTrackerSelector.md) | getメソッドの検索条件（実行パラメータ）を保持します。 | 

##### ＜リクエストサンプル（コンバージョン情報）＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V6">
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
            <ns1:conversionTrackerIds>2222233</ns1:conversionTrackerIds>
            <ns1:conversionTrackerIds>2222244</ns1:conversionTrackerIds>
            <ns1:conversionTrackerTypes>WEB_CONVERSION</ns1:conversionTrackerTypes>
            <ns1:conversionTrackerTypes>APP_CONVERSION</ns1:conversionTrackerTypes>
            <ns1:statuses>ENABLED</ns1:statuses>
            <ns1:categories>DEFAULT</ns1:categories>
            <ns1:categories>DOWNLOAD</ns1:categories>
            <ns1:appIds>jp.co.yahoo.xxxx</ns1:appIds>
           <ns1:appPlatform>ANDROID_MARKET</ns1:appPlatform>
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
| rval | [ConversionTrackerPage](../data/ConversionTrackerPage.md) | getメソッドの実行結果（全Entityのリスト）を保持します。 | 

##### ＜レスポンスサンプル（コンバージョン情報）＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <ns1:ResponseHeader>
         <ns1:service>ConversionTrackerService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:getResponse>
         <ns1:rval>
            <ns1:totalNumEntries>2</ns1:totalNumEntries>
            <ns1:Page.Type>ConversionTrackerPage</ns1:Page.Type>
            <ns1:totalConversions>0</ns1:totalConversions>
            <ns1:totalConversionValue>0</ns1:totalConversionValue>
           <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:conversionTracker xsi:type="ns1:WebConversion">
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:conversionTrackerId>2222222</ns1:conversionTrackerId>
                  <ns1:conversionTrackerName>サンプルWebコンバージョン</ns1:conversionTrackerName>
                  <ns1:status>ENABLED</ns1:status>
                  <ns1:category>DEFAULT</ns1:category>
                 <ns1:userRevenueValue>10</ns1:userRevenueValue>
                  <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
                  <ns1:measurementPeriod>90</ns1:measurementPeriod>
                  <ns1:conversions>0</ns1:conversions>
                  <ns1:conversionValue>0</ns1:conversionValue>
                 <ns1:mostRecentConversionDate>20170701</ns1:mostRecentConversionDate>
                  <ns1:snippet>
                     <ns1:type>JS</ns1:type>
                     <ns1:tag>&lt;script type=\&quot;text/javascript\&quot; language=\&quot;javascript\&quot;&gt;\n  /* &lt;![CDATA[ */\n  var yahoo_ydn_conv_io = \&quot;HPoo.OhRlRKsTNUpTvF7\&quot;;\n  var yahoo_ydn_conv_label = \&quot;\&quot;;\n  var yahoo_ydn_conv_transaction_id = \&quot;\&quot;;\n  var yahoo_ydn_conv_amount = \&quot;10\&quot;;\n  /* ]]&gt; */\n&lt;/script&gt;\n&lt;script type=\&quot;text/javascript\&quot; language=\&quot;javascript\&quot; charset=\&quot;UTF-8\&quot; src=\&quot;//b90.yahoo.co.jp/conv.js\&quot;&gt;&lt;/script&gt;</ns1:tag>
                  </ns1:snippet>
                  <ns1:snippet>
                     <ns1:type>IMG</ns1:type>
                     <ns1:tag>&lt;img src=\&quot;//b90.yahoo.co.jp/c?yahoo_ydn_conv_io=HPoo.OhRlRKsTNUpTvF7&amp;yahoo_ydn_conv_label=&amp;yahoo_ydn_conv_transaction_id=&amp;yahoo_ydn_conv_amount=10&amp;guid=ON\&quot; width=\&quot;1\&quot; height=\&quot;1\&quot; border=\&quot;0\&quot; /&gt;</ns1:tag>
                  </ns1:snippet>
               </ns1:conversionTracker>
            </ns1:values>
           <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:conversionTracker xsi:type="ns1:AppConversion">
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:conversionTrackerId>2222233</ns1:conversionTrackerId>
                  <ns1:conversionTrackerName>サンプルアプリコンバージョン</ns1:conversionTrackerName>
                  <ns1:status>ENABLED</ns1:status>
                  <ns1:category>DOWNLOAD</ns1:category>
                 <ns1:userRevenueValue>10</ns1:userRevenueValue>
                  <ns1:conversionTrackerType>APP_CONVERSION</ns1:conversionTrackerType>
                 <ns1:measurementPeriod>90</ns1:measurementPeriod>
                  <ns1:conversions>0</ns1:conversions>
                  <ns1:conversionValue>0</ns1:conversionValue>
                 <ns1:mostRecentConversionDate>20170630</ns1:mostRecentConversionDate>
                  <ns1:appId>jp.co.yahoo.sample</ns1:appId>
                  <ns1:appPlatform>ANDROID_MARKET</ns1:appPlatform>
                  <ns1:appConversionType>FIRST_OPEN</ns1:appConversionType>
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
| operations | ○ | [ConversionTrackerOperation](../data/ConversionTrackerOperation.md) | mutateメソッドで操作対象となるコンバージョントラッカーを保持します。 | 

##### ＜リクエストサンプル（コンバージョン情報）＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
               <ns1:conversionTrackerName>サンプルWebコンバージョン</ns1:conversionTrackerName>
               <ns1:status>ENABLED</ns1:status>
               <ns1:category>DEFAULT</ns1:category>
               <ns1:userRevenueValue>10</ns1:userRevenueValue>
               <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
              <ns1:measurementPeriod>90</ns1:measurementPeriod>
            </ns1:operand>
            <ns1:operand xsi:type="ns1:AppConversion">
               <ns1:conversionTrackerName>サンプルAppコンバージョン</ns1:conversionTrackerName>
               <ns1:status>ENABLED</ns1:status>
               <ns1:category>DOWNLOAD</ns1:category>
               <ns1:userRevenueValue>10</ns1:userRevenueValue>
               <ns1:conversionTrackerType>APP_CONVERSION</ns1:conversionTrackerType>
               <ns1:measurementPeriod>90</ns1:measurementPeriod>
               <ns1:appId>jp.co.yahoo.samle</ns1:appId>
               <ns1:appPlatform>ANDROID_MARKET</ns1:appPlatform>
               <ns1:appConversionType>FIRST_OPEN</ns1:appConversionType>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [ConversionTrackerReturnValue](../data/ConversionTrackerReturnValue.md) | mutateメソッドの実行結果（全Entityのリスト）を保持します。 | 

##### ＜レスポンスサンプル（コンバージョン情報）＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <ns1:ResponseHeader>
         <ns1:service>ConversionTrackerService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
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
                  <ns1:conversionTrackerName>サンプルWebコンバージョン</ns1:conversionTrackerName>
                  <ns1:status>ENABLED</ns1:status>
                  <ns1:category>DEFAULT</ns1:category>
                 <ns1:userRevenueValue>10</ns1:userRevenueValue>
                  <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
                 <ns1:measurementPeriod>90</ns1:measurementPeriod>
                 <ns1:snippet>
                     <ns1:type>JS</ns1:type>
                     <ns1:tag>&lt;script type=\&quot;text/javascript\&quot; language=\&quot;javascript\&quot;&gt;\n  /* &lt;![CDATA[ */\n  var yahoo_ydn_conv_io = \&quot;HPoo.OhRlRKsTNUpTvF7\&quot;;\n  var yahoo_ydn_conv_label = \&quot;\&quot;;\n  var yahoo_ydn_conv_transaction_id = \&quot;\&quot;;\n  var yahoo_ydn_conv_amount = \&quot;10\&quot;;\n  /* ]]&gt; */\n&lt;/script&gt;\n&lt;script type=\&quot;text/javascript\&quot; language=\&quot;javascript\&quot; charset=\&quot;UTF-8\&quot; src=\&quot;//b90.yahoo.co.jp/conv.js\&quot;&gt;&lt;/script&gt;</ns1:tag>
                  </ns1:snippet>
                  <ns1:snippet>
                     <ns1:type>IMG</ns1:type>
                     <ns1:tag>&lt;img src=\&quot;//b90.yahoo.co.jp/c?yahoo_ydn_conv_io=HPoo.OhRlRKsTNUpTvF7&amp;yahoo_ydn_conv_label=&amp;yahoo_ydn_conv_transaction_id=&amp;yahoo_ydn_conv_amount=10&amp;guid=ON\&quot; width=\&quot;1\&quot; height=\&quot;1\&quot; border=\&quot;0\&quot; /&gt;</ns1:tag>
                  </ns1:snippet>
               </ns1:conversionTracker>
            </ns1:values>
           <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:conversionTracker xsi:type="ns1:AppConversion">
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:conversionTrackerId>2222233</ns1:conversionTrackerId>
                  <ns1:conversionTrackerName>サンプルアプリコンバージョン</ns1:conversionTrackerName>
                  <ns1:status>ENABLED</ns1:status>
                  <ns1:category>DOWNLOAD</ns1:category>
                 <ns1:userRevenueValue>10</ns1:userRevenueValue>
                  <ns1:conversionTrackerType>APP_CONVERSION</ns1:conversionTrackerType>
                 <ns1:measurementPeriod>90</ns1:measurementPeriod>
                 <ns1:appId>jp.co.yahoo.sample</ns1:appId>
                  <ns1:appPlatform>ANDROID_MARKET</ns1:appPlatform>
                  <ns1:appConversionType>FIRST_OPEN</ns1:appConversionType>
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
| operations | ○ | [ConversionTrackerOperation](../data/ConversionTrackerOperation.md) | mutateメソッドで操作対象となるコンバージョントラッカーを保持します。 | 

##### ＜リクエストサンプル（コンバージョン情報）＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:v4="http://im.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <v4:RequestHeader>
         <v4:license>1111-1111-1111-1111</v4:license>
         <v4:apiAccountId>2222-2222-2222-2222</v4:apiAccountId>
         <v4:apiAccountPassword>password</v4:apiAccountPassword>
      </v4:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <v4:mutate>
         <v4:operations>
            <v4:operator>SET</v4:operator>
            <v4:accountId>1000000001</v4:accountId>
            <v4:operand xsi:type="v4:WebConversion">
               <v4:accountId>1000000001</v4:accountId>
               <v4:conversionTrackerId>2222222</v4:conversionTrackerId>
               <v4:conversionTrackerName>modify サンプルWebコンバージョン</v4:conversionTrackerName>
               <v4:status>ENABLED</v4:status>
               <v4:category>DEFAULT</v4:category>
               <v4:userRevenueValue>10</v4:userRevenueValue>
               <v4:conversionTrackerType>WEB_CONVERSION</v4:conversionTrackerType>
            </v4:operand>
            <v4:operand xsi:type="v4:AppConversion">
               <v4:accountId>1000000001</v4:accountId>
               <v4:conversionTrackerId>2222233</v4:conversionTrackerId>
               <v4:conversionTrackerName>modify サンプルAppコンバージョン</v4:conversionTrackerName>
               <v4:status>ENABLED</v4:status>
               <v4:userRevenueValue>10</v4:userRevenueValue>
               <v4:conversionTrackerType>APP_CONVERSION</v4:conversionTrackerType>
               <v4:measurementPeriod>7</v4:measurementPeriod>
            </v4:operand>
         </v4:operations>
      </v4:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [ConversionTrackerReturnValue](../data/ConversionTrackerReturnValue.md) | mutateメソッドの実行結果（全Entityのリスト）を保持します。　| 

##### ＜レスポンスサンプル（コンバージョン情報）＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <ns1:ResponseHeader>
         <ns1:service>ConversionTrackerService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
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
                  <ns1:conversionTrackerName>modify サンプルWebコンバージョン</ns1:conversionTrackerName>
                  <ns1:status>ENABLED</ns1:status>
                  <ns1:category>DEFAULT</ns1:category>
                 <ns1:userRevenueValue>10</ns1:userRevenueValue>
                  <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
                  <ns1:measurementPeriod>90</ns1:measurementPeriod>
                  <ns1:conversions>0</ns1:conversions>
                  <ns1:conversionValue>0</ns1:conversionValue>
                  <ns1:mostRecentConversionDate>20170701</ns1:mostRecentConversionDate>
                  <ns1:snippet>
                     <ns1:type>JS</ns1:type>
                     <ns1:tag>&lt;script type=\&quot;text/javascript\&quot; language=\&quot;javascript\&quot;&gt;\n  /* &lt;![CDATA[ */\n  var yahoo_ydn_conv_io = \&quot;HPoo.OhRlRKsTNUpTvF7\&quot;;\n  var yahoo_ydn_conv_label = \&quot;\&quot;;\n  var yahoo_ydn_conv_transaction_id = \&quot;\&quot;;\n  var yahoo_ydn_conv_amount = \&quot;10\&quot;;\n  /* ]]&gt; */\n&lt;/script&gt;\n&lt;script type=\&quot;text/javascript\&quot; language=\&quot;javascript\&quot; charset=\&quot;UTF-8\&quot; src=\&quot;//b90.yahoo.co.jp/conv.js\&quot;&gt;&lt;/script&gt;</ns1:tag>
                  </ns1:snippet>
                  <ns1:snippet>
                     <ns1:type>IMG</ns1:type>
                     <ns1:tag>&lt;img src=\&quot;//b90.yahoo.co.jp/c?yahoo_ydn_conv_io=HPoo.OhRlRKsTNUpTvF7&amp;yahoo_ydn_conv_label=&amp;yahoo_ydn_conv_transaction_id=&amp;yahoo_ydn_conv_amount=10&amp;guid=ON\&quot; width=\&quot;1\&quot; height=\&quot;1\&quot; border=\&quot;0\&quot; /&gt;</ns1:tag>
                  </ns1:snippet>
               </ns1:conversionTracker>
            </ns1:values>
           <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:conversionTracker xsi:type="ns1:AppConversion">
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:conversionTrackerId>2222233</ns1:conversionTrackerId>
                  <ns1:conversionTrackerName>modify サンプルアプリコンバージョン</ns1:conversionTrackerName>
                  <ns1:status>ENABLED</ns1:status>
                  <ns1:category>DOWNLOAD</ns1:category>
                 <ns1:userRevenueValue>10</ns1:userRevenueValue>
                  <ns1:conversionTrackerType>APP_CONVERSION</ns1:conversionTrackerType>
                  <ns1:measurementPeriod>7</ns1:measurementPeriod>
                  <ns1:conversions>0</ns1:conversions>
                  <ns1:conversionValue>0</ns1:conversionValue>
                  <ns1:mostRecentConversionDate>20170630</ns1:mostRecentConversionDate>
                  <ns1:appId>jp.co.yahoo.sample</ns1:appId>
                  <ns1:appPlatform>ANDROID_MARKET</ns1:appPlatform>
                  <ns1:appConversionType>FIRST_OPEN</ns1:appConversionType>
              </ns1:conversionTracker>
            </ns1:values>           
         </ns1:rval>
      </ns1:mutateResponse>
   </soapenv:Body>
</soapenv:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

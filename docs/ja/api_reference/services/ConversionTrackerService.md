# ConversionTrackerService
ConversionTrackerServiceでは、コンバージョントラッカー情報の操作（取得、追加、更新）を行います。

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201907/ConversionTrackerService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201907/ConversionTrackerService?wsdl |

#### Namespace
http://im.yahooapis.jp/V201907/ConversionTracker

#### サービス概要
コンバージョントラッカー情報の取得およびコンバージョントラッカー情報の追加・更新を行います。

#### 操作
ConversionTrackerServiceで提供される操作を説明します。

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)

#### オブジェクト
[ConversionTracker](../data/ConversionTracker)

## get

### リクエスト
指定アカウントのコンバージョントラッカー情報を取得します。

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [ConversionTrackerSelector](../data/ConversionTracker/ConversionTrackerSelector.md) | getメソッドの検索条件（実行パラメータ）を保持します。 |

##### ＜リクエストサンプル（コンバージョン情報）＞

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/ConversionTracker" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201907/ConversionTracker" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <selector>
        <accountId>1111</accountId>
        <conversionTrackerIds>222</conversionTrackerIds>
        <conversionTrackerIds>333</conversionTrackerIds>
        <conversionTrackerIds>444</conversionTrackerIds>
        <conversionTrackerIds>555</conversionTrackerIds>
        <conversionTrackerIds>666</conversionTrackerIds>
        <conversionTrackerTypes>WEB_CONVERSION</conversionTrackerTypes>
        <conversionTrackerTypes>APP_CONVERSION</conversionTrackerTypes>
        <statuses>ENABLED</statuses>
        <statuses>DISABLED</statuses>
        <categories>DEFAULT</categories>
        <categories>PAGE_VIEW</categories>
        <categories>PURCHASE</categories>
        <categories>SIGNUP</categories>
        <categories>LEAD</categories>
        <categories>DOWNLOAD</categories>
        <categories>NONE</categories>
        <appIds>aaaaa</appIds>
        <appIds>bbbbb</appIds>
        <appIds>ccccc</appIds>
        <appIds>ddddd</appIds>
        <appIds>eeeee</appIds>
        <appPlatform>ANDROID_MARKET</appPlatform>
        <statsPeriod>DEFINITE_VALUE_YESTERDAY</statsPeriod>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>10</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### ＜リクエストサンプル＞(use CUSTOM_DATE)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/ConversionTracker" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201907/ConversionTracker" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <selector>
        <accountId>1111</accountId>
        <conversionTrackerIds>222</conversionTrackerIds>
        <conversionTrackerIds>333</conversionTrackerIds>
        <conversionTrackerIds>444</conversionTrackerIds>
        <conversionTrackerIds>555</conversionTrackerIds>
        <conversionTrackerIds>666</conversionTrackerIds>
        <conversionTrackerTypes>WEB_CONVERSION</conversionTrackerTypes>
        <conversionTrackerTypes>APP_CONVERSION</conversionTrackerTypes>
        <statuses>ENABLED</statuses>
        <statuses>DISABLED</statuses>
        <categories>DEFAULT</categories>
        <categories>PAGE_VIEW</categories>
        <categories>PURCHASE</categories>
        <categories>SIGNUP</categories>
        <categories>LEAD</categories>
        <categories>DOWNLOAD</categories>
        <categories>NONE</categories>
        <appIds>aaaaa</appIds>
        <appIds>bbbbb</appIds>
        <appIds>ccccc</appIds>
        <appIds>ddddd</appIds>
        <appIds>eeeee</appIds>
        <appPlatform>ANDROID_MARKET</appPlatform>
        <statsPeriod>CUSTOM_DATE</statsPeriod>
        <statsPeriodCustomDate>
          <statsStartDate>20180401</statsStartDate>
          <statsEndDate>20190301</statsEndDate>
        </statsPeriodCustomDate>
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
| rval | [ConversionTrackerPage](../data/ConversionTracker/ConversionTrackerPage.md) | getメソッドの実行結果（全Entityのリスト）を保持します。 |

##### ＜レスポンスサンプル（コンバージョン情報）＞

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/ConversionTracker" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>ConversionTracker</ns2:service>
      <ns2:requestTime>1551686139707</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/ConversionTracker">
      <ns2:rval>
        <totalNumEntries>3</totalNumEntries>
        <ns2:totalConversions>20</ns2:totalConversions>
        <ns2:totalConversionValue>20</ns2:totalConversionValue>
        <ns2:totalConversionsViaAdClick>200</ns2:totalConversionsViaAdClick>
        <ns2:totalConversionValueViaAdClick>300</ns2:totalConversionValueViaAdClick>
        <ns2:totalAllConversions>60</ns2:totalAllConversions>
        <ns2:totalAllConversionValue>80</ns2:totalAllConversionValue>
        <ns2:totalCrossDeviceConversions>400</ns2:totalCrossDeviceConversions>
        <ns2:period>
          <ns2:periodStartDate>
            <ns2:periodDate>20180101</ns2:periodDate>
            <ns2:periodTime>000000</ns2:periodTime>
          </ns2:periodStartDate>
          <ns2:periodEndDate>
            <ns2:periodDate>20190101</ns2:periodDate>
            <ns2:periodTime>000000</ns2:periodTime>
          </ns2:periodEndDate>
        </ns2:period>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppConversion">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:conversionTrackerId>1193197</ns2:conversionTrackerId>
            <ns2:conversionTrackerName>APP_ANDROID_FIRST_OPEN_Conversion Tracker</ns2:conversionTrackerName>
            <ns2:status>ENABLED</ns2:status>
            <ns2:category>DOWNLOAD</ns2:category>
            <ns2:userRevenueValue>1</ns2:userRevenueValue>
            <ns2:conversionTrackerType>APP_CONVERSION</ns2:conversionTrackerType>
            <ns2:countingType>ONE_PER_CLICK</ns2:countingType>
            <ns2:measurementPeriod>7</ns2:measurementPeriod>
            <ns2:measurementPeriodView>1</ns2:measurementPeriodView>
            <ns2:excludeFromBidding>TRUE</ns2:excludeFromBidding>
            <ns2:conversions>0</ns2:conversions>
            <ns2:conversionValue>0</ns2:conversionValue>
            <ns2:conversionsViaAdClick>200</ns2:conversionsViaAdClick>
            <ns2:conversionValueViaAdClick>300</ns2:conversionValueViaAdClick>
            <ns2:allConversions>20</ns2:allConversions>
            <ns2:crossDeviceConversions>400</ns2:crossDeviceConversions>
            <ns2:mostRecentConversionDate>20180101</ns2:mostRecentConversionDate>
            <ns2:appId>abc_1234</ns2:appId>
            <ns2:appPlatform>ANDROID_MARKET</ns2:appPlatform>
            <ns2:appConversionType>FIRST_OPEN</ns2:appConversionType>
          </ns2:conversionTracker>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppConversion">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:conversionTrackerId>1193196</ns2:conversionTrackerId>
            <ns2:conversionTrackerName>APP_ITUNES_FIRST_OPEN_Conversion Tracker</ns2:conversionTrackerName>
            <ns2:status>ENABLED</ns2:status>
            <ns2:category>DOWNLOAD</ns2:category>
            <ns2:userRevenueValue>1</ns2:userRevenueValue>
            <ns2:conversionTrackerType>APP_CONVERSION</ns2:conversionTrackerType>
            <ns2:countingType>ONE_PER_CLICK</ns2:countingType>
            <ns2:measurementPeriod>90</ns2:measurementPeriod>
            <ns2:measurementPeriodView>1</ns2:measurementPeriodView>
            <ns2:excludeFromBidding>TRUE</ns2:excludeFromBidding>
            <ns2:conversions>20</ns2:conversions>
            <ns2:conversionValue>20</ns2:conversionValue>
            <ns2:conversionsViaAdClick>0</ns2:conversionsViaAdClick>
            <ns2:conversionValueViaAdClick>0</ns2:conversionValueViaAdClick>
            <ns2:allConversions>20</ns2:allConversions>
            <ns2:crossDeviceConversions>0</ns2:crossDeviceConversions>
            <ns2:appId>abc_1234</ns2:appId>
            <ns2:appPlatform>ITUNES</ns2:appPlatform>
            <ns2:appConversionType>FIRST_OPEN</ns2:appConversionType>
          </ns2:conversionTracker>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:WebConversion">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:conversionTrackerId>1193194</ns2:conversionTrackerId>
            <ns2:conversionTrackerName>WEB_Conversion Tracker</ns2:conversionTrackerName>
            <ns2:status>ENABLED</ns2:status>
            <ns2:category>PAGE_VIEW</ns2:category>
            <ns2:userRevenueValue>100</ns2:userRevenueValue>
            <ns2:conversionTrackerType>WEB_CONVERSION</ns2:conversionTrackerType>
            <ns2:countingType>ONE_PER_CLICK</ns2:countingType>
            <ns2:measurementPeriod>30</ns2:measurementPeriod>
            <ns2:measurementPeriodView>1</ns2:measurementPeriodView>
            <ns2:excludeFromBidding>TRUE</ns2:excludeFromBidding>
            <ns2:conversions>0</ns2:conversions>
            <ns2:conversionValue>0</ns2:conversionValue>
            <ns2:conversionsViaAdClick>0</ns2:conversionsViaAdClick>
            <ns2:conversionValueViaAdClick>0</ns2:conversionValueViaAdClick>
            <ns2:allConversions>20</ns2:allConversions>
            <ns2:crossDeviceConversions>0</ns2:crossDeviceConversions>
            <ns2:snippet>
              <ns2:type>JS</ns2:type>
              <ns2:tag>&amp;amp;lt;!-- Yahoo Code for your Conversion Page --&amp;amp;gt;
&amp;amp;lt;script type="text/javascript"&amp;amp;gt;
    /* &amp;amp;lt;![CDATA[ */
    var yahoo_conversion_id = 1000661;
    var yahoo_conversion_label = "XXXXXXXXXXXXXXXXXX";
    var yahoo_conversion_value = 100;
    /* ]]&amp;amp;gt; */
&amp;amp;lt;/script&amp;amp;gt;
&amp;amp;lt;script type="text/javascript" src="//s.yimg.jp/images/listing/tool/cv/conversion.js"&amp;amp;gt;
&amp;amp;lt;/script&amp;amp;gt;
&amp;amp;lt;noscript&amp;amp;gt;
    &amp;amp;lt;div style="display:inline;"&amp;amp;gt;
        &amp;amp;lt;img height="1" width="1" style="border-style:none;" alt="" src="//b91.yahoo.co.jp/pagead/conversion/1000661/?value=100&amp;amp;amp;label=XXXXXXXXXXXXXXXXXX&amp;amp;amp;guid=ON&amp;amp;amp;script=0&amp;amp;amp;disvt=true"/&amp;amp;gt;
    &amp;amp;lt;/div&amp;amp;gt;
&amp;amp;lt;/noscript&amp;amp;gt;</ns2:tag>
            </ns2:snippet>
          </ns2:conversionTracker>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### ＜レスポンスサンプル＞(use CUSTOM_DATE)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/ConversionTracker" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>ConversionTracker</ns2:service>
      <ns2:requestTime>1551686139792</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/ConversionTracker">
      <ns2:rval>
        <totalNumEntries>3</totalNumEntries>
        <ns2:totalConversions>20</ns2:totalConversions>
        <ns2:totalConversionValue>20</ns2:totalConversionValue>
        <ns2:totalConversionsViaAdClick>100</ns2:totalConversionsViaAdClick>
        <ns2:totalConversionValueViaAdClick>200</ns2:totalConversionValueViaAdClick>
        <ns2:totalAllConversions>60</ns2:totalAllConversions>
        <ns2:totalAllConversionValue>80</ns2:totalAllConversionValue>
        <ns2:totalCrossDeviceConversions>300</ns2:totalCrossDeviceConversions>
        <ns2:period>
          <ns2:periodStartDate>
            <ns2:periodDate>20180101</ns2:periodDate>
            <ns2:periodTime>000000</ns2:periodTime>
          </ns2:periodStartDate>
          <ns2:periodEndDate>
            <ns2:periodDate>20190101</ns2:periodDate>
            <ns2:periodTime>000000</ns2:periodTime>
          </ns2:periodEndDate>
        </ns2:period>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppConversion">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:conversionTrackerId>1193197</ns2:conversionTrackerId>
            <ns2:conversionTrackerName>APP_ANDROID_FIRST_OPEN_Conversion Tracker</ns2:conversionTrackerName>
            <ns2:status>ENABLED</ns2:status>
            <ns2:category>DOWNLOAD</ns2:category>
            <ns2:userRevenueValue>1</ns2:userRevenueValue>
            <ns2:conversionTrackerType>APP_CONVERSION</ns2:conversionTrackerType>
            <ns2:countingType>ONE_PER_CLICK</ns2:countingType>
            <ns2:measurementPeriod>7</ns2:measurementPeriod>
            <ns2:measurementPeriodView>2</ns2:measurementPeriodView>
            <ns2:excludeFromBidding>TRUE</ns2:excludeFromBidding>
            <ns2:conversions>0</ns2:conversions>
            <ns2:conversionValue>0</ns2:conversionValue>
            <ns2:conversionsViaAdClick>100</ns2:conversionsViaAdClick>
            <ns2:conversionValueViaAdClick>200</ns2:conversionValueViaAdClick>
            <ns2:allConversions>20</ns2:allConversions>
            <ns2:crossDeviceConversions>300</ns2:crossDeviceConversions>
            <ns2:mostRecentConversionDate>20180101</ns2:mostRecentConversionDate>
            <ns2:appId>abc_1234</ns2:appId>
            <ns2:appPlatform>ANDROID_MARKET</ns2:appPlatform>
            <ns2:appConversionType>FIRST_OPEN</ns2:appConversionType>
          </ns2:conversionTracker>
          <ns2:statsPeriodCustomDate>
            <ns2:statsStartDate>20180401</ns2:statsStartDate>
            <ns2:statsEndDate>20190301</ns2:statsEndDate>
          </ns2:statsPeriodCustomDate>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppConversion">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:conversionTrackerId>1193196</ns2:conversionTrackerId>
            <ns2:conversionTrackerName>APP_ITUNES_FIRST_OPEN_Conversion Tracker</ns2:conversionTrackerName>
            <ns2:status>ENABLED</ns2:status>
            <ns2:category>DOWNLOAD</ns2:category>
            <ns2:userRevenueValue>1</ns2:userRevenueValue>
            <ns2:conversionTrackerType>APP_CONVERSION</ns2:conversionTrackerType>
            <ns2:countingType>ONE_PER_CLICK</ns2:countingType>
            <ns2:measurementPeriod>90</ns2:measurementPeriod>
            <ns2:measurementPeriodView>2</ns2:measurementPeriodView>
            <ns2:excludeFromBidding>TRUE</ns2:excludeFromBidding>
            <ns2:conversions>20</ns2:conversions>
            <ns2:conversionValue>20</ns2:conversionValue>
            <ns2:conversionsViaAdClick>0</ns2:conversionsViaAdClick>
            <ns2:conversionValueViaAdClick>0</ns2:conversionValueViaAdClick>
            <ns2:allConversions>20</ns2:allConversions>
            <ns2:crossDeviceConversions>300</ns2:crossDeviceConversions>
            <ns2:appId>abc_1234</ns2:appId>
            <ns2:appPlatform>ITUNES</ns2:appPlatform>
            <ns2:appConversionType>FIRST_OPEN</ns2:appConversionType>
          </ns2:conversionTracker>
          <ns2:statsPeriodCustomDate>
            <ns2:statsStartDate>20180401</ns2:statsStartDate>
            <ns2:statsEndDate>20190301</ns2:statsEndDate>
          </ns2:statsPeriodCustomDate>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:WebConversion">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:conversionTrackerId>1193194</ns2:conversionTrackerId>
            <ns2:conversionTrackerName>WEB_Conversion Tracker</ns2:conversionTrackerName>
            <ns2:status>ENABLED</ns2:status>
            <ns2:category>PAGE_VIEW</ns2:category>
            <ns2:userRevenueValue>100</ns2:userRevenueValue>
            <ns2:conversionTrackerType>WEB_CONVERSION</ns2:conversionTrackerType>
            <ns2:countingType>ONE_PER_CLICK</ns2:countingType>
            <ns2:measurementPeriod>30</ns2:measurementPeriod>
            <ns2:measurementPeriodView>2</ns2:measurementPeriodView>
            <ns2:excludeFromBidding>TRUE</ns2:excludeFromBidding>
            <ns2:conversionsViaAdClick>0</ns2:conversionsViaAdClick>
            <ns2:conversionValueViaAdClick>0</ns2:conversionValueViaAdClick>
            <ns2:allConversions>20</ns2:allConversions>
            <ns2:crossDeviceConversions>300</ns2:crossDeviceConversions>
            <ns2:snippet>
              <ns2:type>JS</ns2:type>
              <ns2:tag>&amp;amp;lt;!-- Yahoo Code for your Conversion Page --&amp;amp;gt;
&amp;amp;lt;script type="text/javascript"&amp;amp;gt;
    /* &amp;amp;lt;![CDATA[ */
    var yahoo_conversion_id = 1000661;
    var yahoo_conversion_label = "XXXXXXXXXXXXXXXXXX";
    var yahoo_conversion_value = 100;
    /* ]]&amp;amp;gt; */
&amp;amp;lt;/script&amp;amp;gt;
&amp;amp;lt;script type="text/javascript" src="//s.yimg.jp/images/listing/tool/cv/conversion.js"&amp;amp;gt;
&amp;amp;lt;/script&amp;amp;gt;
&amp;amp;lt;noscript&amp;amp;gt;
    &amp;amp;lt;div style="display:inline;"&amp;amp;gt;
        &amp;amp;lt;img height="1" width="1" style="border-style:none;" alt="" src="//b91.yahoo.co.jp/pagead/conversion/1000661/?value=100&amp;amp;amp;label=XXXXXXXXXXXXXXXXXX&amp;amp;amp;guid=ON&amp;amp;amp;script=0&amp;amp;amp;disvt=true"/&amp;amp;gt;
    &amp;amp;lt;/div&amp;amp;gt;
&amp;amp;lt;/noscript&amp;amp;gt;</ns2:tag>
            </ns2:snippet>
          </ns2:conversionTracker>
          <ns2:statsPeriodCustomDate>
            <ns2:statsStartDate>20180401</ns2:statsStartDate>
            <ns2:statsEndDate>20190301</ns2:statsEndDate>
          </ns2:statsPeriodCustomDate>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)

### リクエスト
コンバージョントラッカー情報を追加します。

| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [ConversionTrackerOperation](../data/ConversionTracker/ConversionTrackerOperation.md) | mutateメソッドで操作対象となるコンバージョントラッカーを保持します。 |

##### ＜リクエストサンプル（コンバージョン情報）＞

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/ConversionTracker" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201907/ConversionTracker">
      <operations>
        <operator>ADD</operator>
        <accountId>0</accountId>
        <operand xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="WebConversion">
          <conversionTrackerName>WebConversion</conversionTrackerName>
          <status>ENABLED</status>
          <category>DEFAULT</category>
          <userRevenueValue>100</userRevenueValue>
          <conversionTrackerType>WEB_CONVERSION</conversionTrackerType>
          <countingType>MANY_PER_CLICK</countingType>
          <measurementPeriod>30</measurementPeriod>
          <measurementPeriodView>10</measurementPeriodView>
          <excludeFromBidding>FALSE</excludeFromBidding>
        </operand>
        <operand xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AppConversion">
          <conversionTrackerName>AppConversion</conversionTrackerName>
          <status>ENABLED</status>
          <category>DOWNLOAD</category>
          <userRevenueValue>100</userRevenueValue>
          <conversionTrackerType>APP_CONVERSION</conversionTrackerType>
          <countingType>ONE_PER_CLICK</countingType>
          <measurementPeriod>30</measurementPeriod>
          <measurementPeriodView>10</measurementPeriodView>
          <excludeFromBidding>FALSE</excludeFromBidding>
          <appId>abc_1234</appId>
          <appPlatform>ANDROID_MARKET</appPlatform>
          <appConversionType>FIRST_OPEN</appConversionType>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [ConversionTrackerReturnValue](../data/ConversionTracker/ConversionTrackerReturnValue.md) | mutateメソッドの実行結果（全Entityのリスト）を保持します。 |

##### ＜レスポンスサンプル（コンバージョン情報）＞

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/ConversionTracker" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>ConversionTracker</ns2:service>
      <ns2:requestTime>1551686139740</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/ConversionTracker">
      <ns2:rval>
        <ListReturnValue.Type>AccountTrackingUrlReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppConversion">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:conversionTrackerId>1193197</ns2:conversionTrackerId>
            <ns2:conversionTrackerName>APP_ANDROID_FIRST_OPEN_Conversion Tracker</ns2:conversionTrackerName>
            <ns2:status>ENABLED</ns2:status>
            <ns2:category>DOWNLOAD</ns2:category>
            <ns2:userRevenueValue>1</ns2:userRevenueValue>
            <ns2:conversionTrackerType>APP_CONVERSION</ns2:conversionTrackerType>
            <ns2:countingType>ONE_PER_CLICK</ns2:countingType>
            <ns2:measurementPeriod>7</ns2:measurementPeriod>
            <ns2:measurementPeriodView>10</ns2:measurementPeriodView>
            <ns2:excludeFromBidding>TRUE</ns2:excludeFromBidding>
            <ns2:conversions>0</ns2:conversions>
            <ns2:conversionValue>0</ns2:conversionValue>
            <ns2:conversionsViaAdClick>0</ns2:conversionsViaAdClick>
            <ns2:conversionValueViaAdClick>0</ns2:conversionValueViaAdClick>
            <ns2:allConversions>20</ns2:allConversions>
            <ns2:crossDeviceConversions>0</ns2:crossDeviceConversions>
            <ns2:mostRecentConversionDate>20180101</ns2:mostRecentConversionDate>
            <ns2:appId>abc_1234</ns2:appId>
            <ns2:appPlatform>ANDROID_MARKET</ns2:appPlatform>
            <ns2:appConversionType>FIRST_OPEN</ns2:appConversionType>
          </ns2:conversionTracker>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppConversion">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:conversionTrackerId>1193196</ns2:conversionTrackerId>
            <ns2:conversionTrackerName>APP_ITUNES_FIRST_OPEN_Conversion Tracker</ns2:conversionTrackerName>
            <ns2:status>ENABLED</ns2:status>
            <ns2:category>DOWNLOAD</ns2:category>
            <ns2:userRevenueValue>1</ns2:userRevenueValue>
            <ns2:conversionTrackerType>APP_CONVERSION</ns2:conversionTrackerType>
            <ns2:countingType>ONE_PER_CLICK</ns2:countingType>
            <ns2:measurementPeriod>90</ns2:measurementPeriod>
            <ns2:measurementPeriodView>10</ns2:measurementPeriodView>
            <ns2:excludeFromBidding>TRUE</ns2:excludeFromBidding>
            <ns2:conversions>20</ns2:conversions>
            <ns2:conversionValue>20</ns2:conversionValue>
            <ns2:conversionsViaAdClick>0</ns2:conversionsViaAdClick>
            <ns2:conversionValueViaAdClick>0</ns2:conversionValueViaAdClick>
            <ns2:allConversions>20</ns2:allConversions>
            <ns2:crossDeviceConversions>0</ns2:crossDeviceConversions>
            <ns2:appId>abc_1234</ns2:appId>
            <ns2:appPlatform>ITUNES</ns2:appPlatform>
            <ns2:appConversionType>FIRST_OPEN</ns2:appConversionType>
          </ns2:conversionTracker>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:WebConversion">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:conversionTrackerId>1193194</ns2:conversionTrackerId>
            <ns2:conversionTrackerName>WEB_Conversion Tracker</ns2:conversionTrackerName>
            <ns2:status>ENABLED</ns2:status>
            <ns2:category>PAGE_VIEW</ns2:category>
            <ns2:userRevenueValue>100</ns2:userRevenueValue>
            <ns2:conversionTrackerType>WEB_CONVERSION</ns2:conversionTrackerType>
            <ns2:countingType>ONE_PER_CLICK</ns2:countingType>
            <ns2:measurementPeriod>30</ns2:measurementPeriod>
            <ns2:measurementPeriodView>10</ns2:measurementPeriodView>
            <ns2:excludeFromBidding>TRUE</ns2:excludeFromBidding>
            <ns2:conversions>20</ns2:conversions>
            <ns2:conversionValue>20</ns2:conversionValue>
            <ns2:conversionsViaAdClick>0</ns2:conversionsViaAdClick>
            <ns2:conversionValueViaAdClick>0</ns2:conversionValueViaAdClick>
            <ns2:allConversions>20</ns2:allConversions>
            <ns2:crossDeviceConversions>0</ns2:crossDeviceConversions>
            <ns2:snippet>
              <ns2:type>JS</ns2:type>
              <ns2:tag>&amp;amp;lt;!-- Yahoo Code for your Conversion Page --&amp;amp;gt;
&amp;amp;lt;script type="text/javascript"&amp;amp;gt;
    /* &amp;amp;lt;![CDATA[ */
    var yahoo_conversion_id = 1000661;
    var yahoo_conversion_label = "XXXXXXXXXXXXXXXXXX";
    var yahoo_conversion_value = 100;
    /* ]]&amp;amp;gt; */
&amp;amp;lt;/script&amp;amp;gt;
&amp;amp;lt;script type="text/javascript" src="//s.yimg.jp/images/listing/tool/cv/conversion.js"&amp;amp;gt;
&amp;amp;lt;/script&amp;amp;gt;
&amp;amp;lt;noscript&amp;amp;gt;
    &amp;amp;lt;div style="display:inline;"&amp;amp;gt;
        &amp;amp;lt;img height="1" width="1" style="border-style:none;" alt="" src="//b91.yahoo.co.jp/pagead/conversion/1000661/?value=100&amp;amp;amp;label=XXXXXXXXXXXXXXXXXX&amp;amp;amp;guid=ON&amp;amp;amp;script=0&amp;amp;amp;disvt=true"/&amp;amp;gt;
    &amp;amp;lt;/div&amp;amp;gt;
&amp;amp;lt;/noscript&amp;amp;gt;</ns2:tag>
            </ns2:snippet>
          </ns2:conversionTracker>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)

### リクエスト
コンバージョントラッカー情報を更新します。

| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [ConversionTrackerOperation](../data/ConversionTracker/ConversionTrackerOperation.md) | mutateメソッドで操作対象となるコンバージョントラッカーを保持します。 |

##### ＜リクエストサンプル（コンバージョン情報）＞

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/ConversionTracker" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201907/ConversionTracker">
      <operations>
        <operator>SET</operator>
        <accountId>0</accountId>
        <operand xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="WebConversion">
          <conversionTrackerId>1193194</conversionTrackerId>
          <conversionTrackerName>WebConversion_update</conversionTrackerName>
          <status>DISABLED</status>
          <category>DEFAULT</category>
          <userRevenueValue>100</userRevenueValue>
          <conversionTrackerType>WEB_CONVERSION</conversionTrackerType>
          <countingType>MANY_PER_CLICK</countingType>
          <measurementPeriod>30</measurementPeriod>
          <measurementPeriodView>2</measurementPeriodView>
          <excludeFromBidding>FALSE</excludeFromBidding>
        </operand>
        <operand xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AppConversion">
          <conversionTrackerId>1193193</conversionTrackerId>
          <conversionTrackerName>AppConversion_update</conversionTrackerName>
          <status>DISABLED</status>
          <category>DOWNLOAD</category>
          <userRevenueValue>100</userRevenueValue>
          <conversionTrackerType>APP_CONVERSION</conversionTrackerType>
          <countingType>ONE_PER_CLICK</countingType>
          <measurementPeriod>30</measurementPeriod>
          <measurementPeriodView>2</measurementPeriodView>
          <excludeFromBidding>FALSE</excludeFromBidding>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [ConversionTrackerReturnValue](../data/ConversionTracker/ConversionTrackerReturnValue.md) | mutateメソッドの実行結果（全Entityのリスト）を保持します。　|

##### ＜レスポンスサンプル（コンバージョン情報）＞

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/ConversionTracker" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>ConversionTracker</ns2:service>
      <ns2:requestTime>1551686139765</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/ConversionTracker">
      <ns2:rval>
        <ListReturnValue.Type>AccountTrackingUrlReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppConversion">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:conversionTrackerId>1193197</ns2:conversionTrackerId>
            <ns2:conversionTrackerName>APP_ANDROID_FIRST_OPEN_Conversion Tracker</ns2:conversionTrackerName>
            <ns2:status>ENABLED</ns2:status>
            <ns2:category>DOWNLOAD</ns2:category>
            <ns2:userRevenueValue>1</ns2:userRevenueValue>
            <ns2:conversionTrackerType>APP_CONVERSION</ns2:conversionTrackerType>
            <ns2:countingType>ONE_PER_CLICK</ns2:countingType>
            <ns2:measurementPeriod>7</ns2:measurementPeriod>
            <ns2:measurementPeriodView>2</ns2:measurementPeriodView>
            <ns2:excludeFromBidding>TRUE</ns2:excludeFromBidding>
            <ns2:conversions>0</ns2:conversions>
            <ns2:conversionValue>0</ns2:conversionValue>
            <ns2:conversionsViaAdClick>0</ns2:conversionsViaAdClick>
            <ns2:conversionValueViaAdClick>0</ns2:conversionValueViaAdClick>
            <ns2:allConversions>20</ns2:allConversions>
            <ns2:crossDeviceConversions>0</ns2:crossDeviceConversions>
            <ns2:mostRecentConversionDate>20180101</ns2:mostRecentConversionDate>
            <ns2:appId>abc_1234</ns2:appId>
            <ns2:appPlatform>ANDROID_MARKET</ns2:appPlatform>
            <ns2:appConversionType>FIRST_OPEN</ns2:appConversionType>
          </ns2:conversionTracker>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppConversion">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:conversionTrackerId>1193196</ns2:conversionTrackerId>
            <ns2:conversionTrackerName>APP_ITUNES_FIRST_OPEN_Conversion Tracker</ns2:conversionTrackerName>
            <ns2:status>ENABLED</ns2:status>
            <ns2:category>DOWNLOAD</ns2:category>
            <ns2:userRevenueValue>1</ns2:userRevenueValue>
            <ns2:conversionTrackerType>APP_CONVERSION</ns2:conversionTrackerType>
            <ns2:countingType>ONE_PER_CLICK</ns2:countingType>
            <ns2:measurementPeriod>90</ns2:measurementPeriod>
            <ns2:measurementPeriodView>2</ns2:measurementPeriodView>
            <ns2:excludeFromBidding>TRUE</ns2:excludeFromBidding>
            <ns2:conversions>20</ns2:conversions>
            <ns2:conversionValue>20</ns2:conversionValue>
            <ns2:conversionsViaAdClick>0</ns2:conversionsViaAdClick>
            <ns2:conversionValueViaAdClick>0</ns2:conversionValueViaAdClick>
            <ns2:allConversions>20</ns2:allConversions>
            <ns2:crossDeviceConversions>0</ns2:crossDeviceConversions>
            <ns2:appId>abc_1234</ns2:appId>
            <ns2:appPlatform>ITUNES</ns2:appPlatform>
            <ns2:appConversionType>FIRST_OPEN</ns2:appConversionType>
          </ns2:conversionTracker>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:WebConversion">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:conversionTrackerId>1193194</ns2:conversionTrackerId>
            <ns2:conversionTrackerName>WEB_Conversion Tracker</ns2:conversionTrackerName>
            <ns2:status>ENABLED</ns2:status>
            <ns2:category>PAGE_VIEW</ns2:category>
            <ns2:userRevenueValue>100</ns2:userRevenueValue>
            <ns2:conversionTrackerType>WEB_CONVERSION</ns2:conversionTrackerType>
            <ns2:countingType>ONE_PER_CLICK</ns2:countingType>
            <ns2:measurementPeriod>30</ns2:measurementPeriod>
            <ns2:excludeFromBidding>TRUE</ns2:excludeFromBidding>
            <ns2:conversionsViaAdClick>0</ns2:conversionsViaAdClick>
            <ns2:conversionValueViaAdClick>0</ns2:conversionValueViaAdClick>
            <ns2:allConversions>20</ns2:allConversions>
            <ns2:crossDeviceConversions>0</ns2:crossDeviceConversions>
            <ns2:snippet>
              <ns2:type>JS</ns2:type>
              <ns2:tag>&amp;amp;lt;!-- Yahoo Code for your Conversion Page --&amp;amp;gt;
&amp;amp;lt;script type="text/javascript"&amp;amp;gt;
    /* &amp;amp;lt;![CDATA[ */
    var yahoo_conversion_id = 1000661;
    var yahoo_conversion_label = "XXXXXXXXXXXXXXXXXX";
    var yahoo_conversion_value = 100;
    /* ]]&amp;amp;gt; */
&amp;amp;lt;/script&amp;amp;gt;
&amp;amp;lt;script type="text/javascript" src="//s.yimg.jp/images/listing/tool/cv/conversion.js"&amp;amp;gt;
&amp;amp;lt;/script&amp;amp;gt;
&amp;amp;lt;noscript&amp;amp;gt;
    &amp;amp;lt;div style="display:inline;"&amp;amp;gt;
        &amp;amp;lt;img height="1" width="1" style="border-style:none;" alt="" src="//b91.yahoo.co.jp/pagead/conversion/1000661/?value=100&amp;amp;amp;label=XXXXXXXXXXXXXXXXXX&amp;amp;amp;guid=ON&amp;amp;amp;script=0&amp;amp;amp;disvt=true"/&amp;amp;gt;
    &amp;amp;lt;/div&amp;amp;gt;
&amp;amp;lt;/noscript&amp;amp;gt;</ns2:tag>
            </ns2:snippet>
          </ns2:conversionTracker>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

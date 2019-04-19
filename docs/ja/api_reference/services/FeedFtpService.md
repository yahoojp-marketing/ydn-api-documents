# FeedFtpService
FeedFtpServiceでは、FTP設定情報の取得、登録、更新を行います。

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201903/FeedFtpService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201903/FeedFtpService?wsdl |

#### Namespace
http://im.yahooapis.jp/V201903/FeedFtp

#### サービス概要
FTP設定情報の取得、登録、更新を行います。

#### 操作
提供される操作を説明します。

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)

#### オブジェクト
[FeedFtp](../data/FeedFtp)

## get
FTP設定情報を取得します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [FeedFtpSelector](../data/FeedFtp/FeedFtpSelector.md) | FTP設定報の取得条件 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/FeedFtp" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201903/FeedFtp">
      <selector>
        <accountId>1234567890</accountId>
        <feedHolderIds>10001</feedHolderIds>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [FeedFtpPage](../data/FeedFtp/FeedFtpPage.md) | 取得条件に合致するFTP設定情報 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/FeedFtp" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>FeedFtp</ns2:service>
      <ns2:requestTime>1552638879331</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/FeedFtp">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>FeedFtpPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedFtp>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:feedHolderId>10001</ns2:feedHolderId>
            <ns2:itemListUploadType>UPDATE_ALL</ns2:itemListUploadType>
            <ns2:schedule xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ScheduleHourly">
              <ns2:type>HOURLY</ns2:type>
              <ns2:interval>1</ns2:interval>
            </ns2:schedule>
            <ns2:feedUrl>ftp://test.com/test1.tsv</ns2:feedUrl>
            <ns2:userName>user_name_1</ns2:userName>
            <ns2:activeStatus>ACTIVE</ns2:activeStatus>
          </ns2:feedFtp>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
FTP設定情報を新規登録します

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| operations | ○ | [FeedFtpOperation](../data/FeedFtp/FeedFtpOperation.md) | 登録対象のFTP設定情報 |

##### ＜リクエストサンプル＞(use HOURLY)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/FeedFtp" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201903/FeedFtp">
      <operations>
        <operator>ADD</operator>
        <accountId>1234567890</accountId>
        <operand>
          <feedHolderId>10001</feedHolderId>
          <itemListUploadType>UPDATE_ALL</itemListUploadType>
          <schedule xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ScheduleHourly">
            <type>HOURLY</type>
            <interval>1</interval>
          </schedule>
          <feedUrl>ftp://test.com/test1.tsv</feedUrl>
          <userName>user_name_1</userName>
          <userPassword>user_password_1</userPassword>
          <activeStatus>ACTIVE</activeStatus>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### ＜リクエストサンプル＞(use DAILY)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/FeedFtp" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201903/FeedFtp">
      <operations>
        <operator>ADD</operator>
        <accountId>1234567890</accountId>
        <operand>
          <feedHolderId>10001</feedHolderId>
          <itemListUploadType>UPDATE_PART</itemListUploadType>
          <schedule xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ScheduleDaily">
            <type>DAILY</type>
            <time>11</time>
          </schedule>
          <feedUrl>ftp://test.com/test2.tsv</feedUrl>
          <userName>user_name_2</userName>
          <userPassword>user_password_2</userPassword>
          <activeStatus>INACTIVE</activeStatus>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### ＜リクエストサンプル＞(use WEEKLY)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/FeedFtp" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201903/FeedFtp">
      <operations>
        <operator>ADD</operator>
        <accountId>1234567890</accountId>
        <operand>
          <feedHolderId>10001</feedHolderId>
          <itemListUploadType>UPDATE_ALL</itemListUploadType>
          <schedule xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ScheduleWeekly">
            <type>WEEKLY</type>
            <time>11</time>
            <week>FRI</week>
          </schedule>
          <feedUrl>ftp://test.com/test3.tsv</feedUrl>
          <userName>user_name_3</userName>
          <userPassword>user_password_3</userPassword>
          <activeStatus>ACTIVE</activeStatus>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [FeedFtpReturnValue](../data/FeedFtp/FeedFtpReturnValue.md) | 登録結果 |

##### ＜レスポンスサンプル＞(use HOURLY)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/FeedFtp" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>FeedFtp</ns2:service>
      <ns2:requestTime>1552638879367</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/FeedFtp">
      <ns2:rval>
        <ListReturnValue.Type>FeedSetReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedFtp>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:feedHolderId>10001</ns2:feedHolderId>
            <ns2:itemListUploadType>UPDATE_ALL</ns2:itemListUploadType>
            <ns2:schedule xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ScheduleHourly">
              <ns2:type>HOURLY</ns2:type>
              <ns2:interval>1</ns2:interval>
            </ns2:schedule>
            <ns2:feedUrl>ftp://test.com/test1.tsv</ns2:feedUrl>
            <ns2:userName>user_name_1</ns2:userName>
            <ns2:activeStatus>ACTIVE</ns2:activeStatus>
          </ns2:feedFtp>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### ＜レスポンスサンプル＞(use DAILY)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/FeedFtp" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>FeedFtp</ns2:service>
      <ns2:requestTime>1552638879389</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/FeedFtp">
      <ns2:rval>
        <ListReturnValue.Type>FeedSetReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedFtp>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:feedHolderId>10001</ns2:feedHolderId>
            <ns2:itemListUploadType>UPDATE_PART</ns2:itemListUploadType>
            <ns2:schedule xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ScheduleDaily">
              <ns2:type>DAILY</ns2:type>
              <ns2:time>11</ns2:time>
            </ns2:schedule>
            <ns2:feedUrl>ftp://test.com/test2.tsv</ns2:feedUrl>
            <ns2:userName>user_name_2</ns2:userName>
            <ns2:activeStatus>INACTIVE</ns2:activeStatus>
          </ns2:feedFtp>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### ＜レスポンスサンプル＞(use WEEKLY)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/FeedFtp" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>FeedFtp</ns2:service>
      <ns2:requestTime>1552638879418</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/FeedFtp">
      <ns2:rval>
        <ListReturnValue.Type>FeedSetReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedFtp>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:feedHolderId>10001</ns2:feedHolderId>
            <ns2:itemListUploadType>UPDATE_ALL</ns2:itemListUploadType>
            <ns2:schedule xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ScheduleWeekly">
              <ns2:type>WEEKLY</ns2:type>
              <ns2:time>11</ns2:time>
              <ns2:week>FRI</ns2:week>
            </ns2:schedule>
            <ns2:feedUrl>ftp://test.com/test3.tsv</ns2:feedUrl>
            <ns2:userName>user_name_3</ns2:userName>
            <ns2:activeStatus>ACTIVE</ns2:activeStatus>
          </ns2:feedFtp>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
FTP設定情報を更新します

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| operations | ○ | [FeedFtpOperation](../data/FeedFtp/FeedFtpOperation.md) | 登録対象のFTP設定情報 |

##### ＜リクエストサンプル＞(use HOURLY)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/FeedFtp" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201903/FeedFtp">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <feedHolderId>10001</feedHolderId>
          <itemListUploadType>UPDATE_ALL</itemListUploadType>
          <schedule xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ScheduleHourly">
            <type>HOURLY</type>
            <interval>1</interval>
          </schedule>
          <feedUrl>ftp://test.com/test1.tsv</feedUrl>
          <userName>user_name_1</userName>
          <userPassword>user_password_1</userPassword>
          <activeStatus>ACTIVE</activeStatus>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### ＜リクエストサンプル＞(use DAILY)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/FeedFtp" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201903/FeedFtp">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <feedHolderId>10001</feedHolderId>
          <itemListUploadType>UPDATE_PART</itemListUploadType>
          <schedule xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ScheduleDaily">
            <type>DAILY</type>
            <time>23</time>
          </schedule>
          <feedUrl>ftp://test.com/test2.tsv</feedUrl>
          <userName>user_name_2</userName>
          <userPassword>user_password_2</userPassword>
          <activeStatus>INACTIVE</activeStatus>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### ＜リクエストサンプル＞(use WEEKLY)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/FeedFtp" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201903/FeedFtp">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <feedHolderId>10001</feedHolderId>
          <itemListUploadType>UPDATE_ALL</itemListUploadType>
          <schedule xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ScheduleWeekly">
            <type>WEEKLY</type>
            <time>11</time>
            <week>MON</week>
          </schedule>
          <feedUrl>ftp://test.com/test3.tsv</feedUrl>
          <userName>user_name_3</userName>
          <userPassword>user_password_3</userPassword>
          <activeStatus>ACTIVE</activeStatus>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [FeedFtpReturnValue](../data/FeedFtp/FeedFtpReturnValue.md) | 登録結果 |

##### ＜レスポンスサンプル＞(use HOURLY)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/FeedFtp" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>FeedFtp</ns2:service>
      <ns2:requestTime>1552638879443</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/FeedFtp">
      <ns2:rval>
        <ListReturnValue.Type>FeedFtpReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedFtp>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:feedHolderId>10001</ns2:feedHolderId>
            <ns2:itemListUploadType>UPDATE_ALL</ns2:itemListUploadType>
            <ns2:schedule xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ScheduleHourly">
              <ns2:type>HOURLY</ns2:type>
              <ns2:interval>1</ns2:interval>
            </ns2:schedule>
            <ns2:feedUrl>ftp://test.com/test1.tsv</ns2:feedUrl>
            <ns2:userName>user_name_1</ns2:userName>
            <ns2:activeStatus>ACTIVE</ns2:activeStatus>
          </ns2:feedFtp>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### ＜レスポンスサンプル＞(use DAILY)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/FeedFtp" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>FeedFtp</ns2:service>
      <ns2:requestTime>1552638879464</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/FeedFtp">
      <ns2:rval>
        <ListReturnValue.Type>FeedFtpReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedFtp>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:feedHolderId>10001</ns2:feedHolderId>
            <ns2:itemListUploadType>UPDATE_PART</ns2:itemListUploadType>
            <ns2:schedule xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ScheduleDaily">
              <ns2:type>DAILY</ns2:type>
              <ns2:time>23</ns2:time>
            </ns2:schedule>
            <ns2:feedUrl>ftp://test.com/test2.tsv</ns2:feedUrl>
            <ns2:userName>user_name_2</ns2:userName>
            <ns2:activeStatus>INACTIVE</ns2:activeStatus>
          </ns2:feedFtp>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### ＜レスポンスサンプル＞(use WEEKLY)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/FeedFtp" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>FeedFtp</ns2:service>
      <ns2:requestTime>1552638879489</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/FeedFtp">
      <ns2:rval>
        <ListReturnValue.Type>FeedFtpReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedFtp>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:feedHolderId>10001</ns2:feedHolderId>
            <ns2:itemListUploadType>UPDATE_ALL</ns2:itemListUploadType>
            <ns2:schedule xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ScheduleWeekly">
              <ns2:type>WEEKLY</ns2:type>
              <ns2:time>11</ns2:time>
              <ns2:week>MON</ns2:week>
            </ns2:schedule>
            <ns2:feedUrl>ftp://test.com/test3.tsv</ns2:feedUrl>
            <ns2:userName>user_name_3</ns2:userName>
            <ns2:activeStatus>ACTIVE</ns2:activeStatus>
          </ns2:feedFtp>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

# DictionaryService
DictionaryServiceは、審査否認理由、地域情報、インタレストカテゴリー、サイトカテゴリーの一覧を提供します。

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/Vx.x/DictionaryService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/Vx.x/DictionaryService?wsdl |

#### Namespace
http://im.yahooapis.jp/V6

#### サービス概要
各種情報の一覧を取得します。

#### 操作
DictionaryServiceで提供される操作を説明します。

## getDisapprovalReason
### リクエスト
EditorialReasonと推奨する対応方法の一覧を取得します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [DisapprovalReasonSelector](../data/DisapprovalReasonSelector.md) | 取得するEditorialReason一覧の言語を指定します。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
      <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getDisapprovalReason>
      <ns1:selector>
        <ns1:lang>JA</ns1:lang>
      </ns1:selector>
    </ns1:getDisapprovalReason>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [DisapprovalReasonPage](../data/DisapprovalReasonPage.md) | 操作結果を含むコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>DictionaryService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getDisapprovalReasonResponse>
      <ns1:rval>
        <ns1:totalNumEntries>3</ns1:totalNumEntries>
        <ns1:Page.Type>DisapprovalReasonPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:disapprovalReason>
            <ns1:disapprovalReasonCode>1</ns1:disapprovalReasonCode>
            <ns1:lang>JA</ns1:lang>
            <ns1:title>宗教の活動告知</ns1:title>
            <ns1:description>宗教団体による活動告知については掲載をお断りしています。</ns1:description>
            <ns1:recommend></ns1:recommend>
          </ns1:disapprovalReason>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:disapprovalReason>
            <ns1:disapprovalReasonCode>2</ns1:disapprovalReasonCode>
            <ns1:lang>JA</ns1:lang>
            <ns1:title>表示できないサイト</ns1:title>
            <ns1:description>リンク先ページが正しく読み込みできません。</ns1:description>
            <ns1:recommend>URLに誤字や使用できない記号がないか、またURLが正しく動作するかをご確認の上、再度審査をご依頼ください。</ns1:recommend>
          </ns1:disapprovalReason>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:disapprovalReason>
            <ns1:disapprovalReasonCode>3</ns1:disapprovalReasonCode>
            <ns1:lang>JA</ns1:lang>
            <ns1:title>比較表記、安全性などを保証する表現</ns1:title>
            <ns1:description>サイト、タイトルまたは説明文内で、比較表記、誇大広告、効果、安全性等を保証する表現が見受けられました。</ns1:description>
            <ns1:recommend>使用できない表現を修正のうえ、再度審査をご依頼ください。</ns1:recommend>
          </ns1:disapprovalReason>
        </ns1:values>
      </ns1:rval>
    </ns1:getDisapprovalReasonResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getGeographicLocation
### リクエスト
地域情報の一覧を取得します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | - | [GeographicLocationSelector](../data/GeographicLocationSelector.md) | 地域情報の一覧を取得します。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getGeographicLocation>
          <ns1:selector>
            <ns1:lang>JA</ns1:lang>
          </ns1:selector>
        </ns1:getGeographicLocation>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [GeographicLocationPage](../data/GeographicLocationPage.md) | 操作結果を含むコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>DictionaryService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getRegionResponse>
      <ns1:rval>
        <ns1:Page.Type>GeographicLocationPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:geographicLocation>
            <ns1:code>TC-CI-00000100</ns1:code>
            <ns1:name>北海道</ns1:name>
            <ns1:fullname>北海道</ns1:fullname>
            <ns1:child>
              <ns1:code>TC-CI-00000217</ns1:code>
              <ns1:parent>TC-CI-00000100</ns1:parent>
              <ns1:name>赤平市</ns1:name>
              <ns1:fullname>北海道 赤平市</ns1:fullname>
            </ns1:child>
            <ns1:child>
              <ns1:code>TC-CI-00000200</ns1:code>
              <ns1:parent>TC-CI-00000100</ns1:parent>
              <ns1:name>札幌市</ns1:name>
              <ns1:fullname>北海道 札幌市</ns1:fullname>
              <ns1:child>
                <ns1:code>TC-CI-00002000</ns1:code>
                <ns1:parent>TC-CI-00000200</ns1:parent>
                <ns1:name>厚別区</ns1:name>
                <ns1:fullname>北海道 札幌市 厚別区</ns1:fullname>
              </ns1:child>
            </ns1:child>
          </ns1:geographicLocation>
        </ns1:values>
      </ns1:rval>
    </ns1:getRegionResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getInterestCategory
### リクエスト
インタレストカテゴリーリストを取得します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | - | [CategorySelector](../data/CategorySelector.md) | インタレストカテゴリーリストを取得します。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getInterestCategory>
          <ns1:selector>
            <ns1:lang>JA</ns1:lang>
          </ns1:selector>
        </ns1:getInterestCategory>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [CategoryPage](../data/CategoryPage.md) | 操作結果を含むコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>DictionaryService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getInterestCategoryResponse>
      <ns1:rval>
        <ns1:totalNumEntries>2</ns1:totalNumEntries>
        <ns1:Page.Type>InterestCategoryPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:category>
            <ns1:name>ニュース、情報系</ns1:name>
            <ns1:child>
              <ns1:code>TC-SC-10110100100100</ns1:code>
              <ns1:name>ニュース</ns1:name>
              <ns1:fullName>ニュース</ns1:fullName>
            </ns1:child>
            <ns1:child>
              <ns1:code>TC-SC-10110120100100</ns1:code>
              <ns1:name>海外</ns1:name>
              <ns1:fullName>ニュース/海外</ns1:fullName>
            </ns1:child>
          </ns1:category>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:category>
            <ns1:name>ソーシャルサービス</ns1:name>
            <ns1:child>
              <ns1:code>TC-SC-20110110100100</ns1:code>
              <ns1:name>Q&A</ns1:name>
              <ns1:fullName>ソーシャルサービス/Q&A</ns1:fullName>
            </ns1:child>
            <ns1:child>
              <ns1:code>TC-SC-20110120100100</ns1:code>
              <ns1:name>ブログ</ns1:name>
              <ns1:fullName>ソーシャルサービス/ブログ</ns1:fullName>
            </ns1:child>
          </ns1:category>
        </ns1:values>
      </ns1:rval>
    </ns1:getInterestCategoryResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getSiteCategory
### リクエスト
サイトトカテゴリーリストを取得します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | - | [CategorySelector](../data/CategorySelector.md) | サイトカテゴリーリストを取得します。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getSiteCategory>
          <ns1:selector>
            <ns1:lang>JA</ns1:lang>
          </ns1:selector>
        </ns1:getSiteCategory>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [CategoryPage](../data/CategoryPage.md) | 操作結果を含むコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>DictionaryService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getSiteCategoryResponse>
      <ns1:rval>
        <ns1:totalNumEntries>2</ns1:totalNumEntries>
        <ns1:Page.Type>SiteCategoryPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:category>
            <ns1:name>ニュース、情報系</ns1:name>
            <ns1:child>
              <ns1:code>TC-SC-10110100100100</ns1:code>
              <ns1:name>ニュース</ns1:name>
              <ns1:fullName>ニュース</ns1:fullName>
            </ns1:child>
            <ns1:child>
              <ns1:code>TC-SC-10110120100100</ns1:code>
              <ns1:name>海外</ns1:name>
              <ns1:fullName>ニュース/海外</ns1:fullName>
            </ns1:child>
          </ns1:category>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:category>
            <ns1:name>ソーシャルサービス</ns1:name>
            <ns1:child>
              <ns1:code>TC-SC-20110110100100</ns1:code>
              <ns1:name>Q&A</ns1:name>
              <ns1:fullName>ソーシャルサービス/Q&A</ns1:fullName>
            </ns1:child>
            <ns1:child>
              <ns1:code>TC-SC-20110120100100</ns1:code>
              <ns1:name>ブログ</ns1:name>
              <ns1:fullName>ソーシャルサービス/ブログ</ns1:fullName>
            </ns1:child>
          </ns1:category>
        </ns1:values>
      </ns1:rval>
    </ns1:getSiteCategoryResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getColorSet
### リクエスト
カラーセットの一覧を取得します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [ColorSetSelector](../data/ColorSetSelector.md)|広告レイアウトのテーマ設定を取得します。 | 

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
        <ns1:getColorSet>
          <ns1:selector>
            <ns1:lang>JA</ns1:lang>
          </ns1:selector>
        </ns1:getColorSet>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [ColorSetPage](../data/ColorSetPage.md) | 操作結果を含むコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>DictionaryService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getColorSetResponse>
      <ns1:rval>
        <ns1:totalNumEntries>2</ns1:totalNumEntries>
        <ns1:Page.Type>ColorSetPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:colorSetId>10000000</ns1:colorSetId>
          <ns1:name>カラーセット１</ns1:name>
          <ns1:colorSet>
             <ns1:element>BACKGROUND1_FROM</ns1:element>
             <ns1:color>000080</ns1:color>
          </ns1:colorSet>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:colorSetId>10000000</ns1:colorSetId>
          <ns1:name>カラーセット２</ns1:name>
          <ns1:colorSet>
             <ns1:element>BORDER</ns1:element>
             <ns1:color>87CEEB</ns1:color>
          </ns1:colorSet>
        </ns1:values>
      </ns1:rval>
    </ns1:getColorSetResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getOsVersion
### リクエスト
OSのバージョンを取得します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | - | [OsVersionSelector](../data/OsVersionSelector.md) | getOsVersionメソッドの検索条件（実行パラメータ）を保持します。 | 

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
        <ns1:getOsVersion>
          <ns1:selector>
            <ns1:osType>ANDROID</ns1:osType>
          </ns1:selector>
        </ns1:getOsVersion>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [OsVersionPage](../data/OsVersionPage.md) | getOsVersionメソッドの実行結果（全Entityのリスト）を保持します。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>DictionaryService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getOsVersionResponse>
      <ns1:rval>
        <ns1:totalNumEntries>2</ns1:totalNumEntries>
        <ns1:Page.Type>OsVersionPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:osVersion>
             <ns1:osType>ANDROID</ns1:osType>
             <ns1:version>7.1</ns1:version>
          </ns1:osVersion>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:osVersion>
             <ns1:osType>IOS</ns1:osType>
             <ns1:version>10.3.2</ns1:version>
          </ns1:osVersion>
        </ns1:values>
      </ns1:rval>
    </ns1:getOsVersionResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getMediaAdFormat
### リクエスト
入稿可能な画像の形式(MediaAdFormat)を照会します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| - | - | - | なし | 

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
        <ns1:getMediaAdFormat />
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [MediaAdFormatPage](../data/MediaAdFormatPage.md) | getMediaAdFormatメソッドの実行結果（全Entityのリスト）を保持します。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>DictionaryService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getMediaAdFormatResponse>
      <ns1:rval>
        <ns1:totalNumEntries>2</ns1:totalNumEntries>
        <ns1:Page.Type>OsVersionPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:mediaAdFormat>
             <ns1:id>1</ns1:id>
             <ns1:width>728</ns1:width>
             <ns1:height>90</ns1:height>
             <ns1:size>153600</ns1:size>
             <ns1:transparent>false</ns1:transparent>
             <ns1:animation>false</ns1:animation>
             <ns1:logo>false</ns1:logo>
             <ns1:thumbnail>false</ns1:thumbnail>
             <ns1:adFormat>ICON</ns1:adFormat>
          </ns1:mediaAdFormat>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:mediaAdFormat>
             <ns1:id>2</ns1:id>
             <ns1:width>320</ns1:width>
             <ns1:height>50</ns1:height>
             <ns1:size>153600</ns1:size>
             <ns1:transparent>false</ns1:transparent>
             <ns1:animation>true</ns1:animation>
             <ns1:logo>false</ns1:logo>
             <ns1:thumbnail>false</ns1:thumbnail>
             <ns1:adFormat>SQUARE_57</ns1:adFormat>
          </ns1:mediaAdFormat>
        </ns1:values>
      </ns1:rval>
    </ns1:getMediaAdFormatResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

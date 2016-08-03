# DictionaryService
DictionaryService retrieves the list of rejected reasons, geo targeting, interest category, site category.

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/Vx.x/DictionaryService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/Vx.x/DictionaryService?wsdl|
#### Namespace
http://im.yahooapis.jp/V5
#### Service Overview
Use this service to retrieve each information.
#### Operation
Explains operations provided by DictionaryService.
## getDisapprovalReason
### Request
Reterieve the list of reponse from recommendation with EditorialReason.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| operations | required | [DisapprovalReasonSelector](../data/DisapprovalReasonSelector.md) | Designate the language of EditorialReason list to be retrieved. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
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

##### Request Sample (On-Behalf-Of Account) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      <ns1:accountId>1000000001</ns1:accountId>
      <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
      <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
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

### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [DisapprovalReasonPage](../data/DisapprovalReasonPage.md) | A container that stores results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
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
            <ns1:desapprovalReasonCode>2</ns1:disapprovalReasonCode>
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
### Request
Retrieves the information list of geo targeting.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| operations | required | [GeographicLocationSelector](../data/GeographicLocationSelector.md) | Retrieves the list of geo targeting information. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxx</ns1:apiAccountId>
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

##### Request Sample (On-Behalf-Of Account) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>1234567890</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getGeographicLocation>
          <ns1:selector>
            <ns1:lang>EN</ns1:lang>
          </ns1:selector>
        </ns1:getGeographicLocation>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [GeographicLocationPage](../data/GeographicLocationPage.md) | A container that stores results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
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
### Request
Retrieves the list of interest category.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| operations |  | [CategorySelector](../data/CategorySelector.md) | Retrieves interest category list. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxx</ns1:apiAccountId>
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

##### Request Sample (On-Behalf-Of Account) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
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

### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [CategoryPage](../data/CategoryPage.md) | A container that stores results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
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
### Request
Retrieves the list of site category.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| operations |  | [CategorySelector](../data/CategorySelector.md) | Retrieves interest category list. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxx</ns1:apiAccountId>
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

##### Request Sample (On-Behalf-Of Account) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getSiteCategory>
          <ns1:selector>
            <ns1:lang>EN</ns1:lang>
          </ns1:selector>
        </ns1:getSiteCategory>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [CategoryPage](../data/CategoryPage.md) | A container that stores results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
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
### Request
Retrieves the list of color set.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| operations |  | [ColorSetSelector](../data/ColorSetSelector.md) | Obtain the setting of ad layout. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
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

##### Request Sample (On-Behalf-Of Account) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getColorSet>
          <ns1:selector>
            <ns1:lang>EN</ns1:lang>
          </ns1:selector>
        </ns1:getColorSet>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [ColorSetPage](../data/ColorSetPage.md) | A container that stores results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
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
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

# DictionaryService

DictionaryService retrieves the list of rejected reasons, geo targeting, interest category, site category.

#### WSDL

| environment |                                      url                                      |
| ----------- | ----------------------------------------------------------------------------- |
| production  | https://location.im.yahooapis.jp/services/V201907/DictionaryService?wsdl |
| sandbox     | https://sandbox.im.yahooapis.jp/services/V201907/DictionaryService?wsdl  |

#### Namespace

http://im.yahooapis.jp/V201907/Dictionary

#### Service Overview

Use this service to retrieve each information.

#### Operation

Explains operations provided by DictionaryService.

+ [getDisapprovalReason](#getdisapprovalreason)
+ [getGeographicLocation](#getgeographiclocation)
+ [getInterestCategory](#getinterestcategory)
+ [getSiteCategory](#getsitecategory)
+ [getColorSet](#getcolorset)
+ [getOsVersion](#getosversion)
+ [getMediaAdFormat](#getmediaadformat)

## getDisapprovalReason

### Request

Retrieves the list of response from recommendation with EditorialReason.

| Parameter | Required | Data Type |
| --------- | -------- | --------- |
| selector | Yes | [DisapprovalReasonSelector](../data/Dictionary/DisapprovalReasonSelector.md) |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/Dictionary" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getDisapprovalReason xmlns="http://im.yahooapis.jp/V201907/Dictionary">
      <selector>
        <lang>EN</lang>
      </selector>
    </getDisapprovalReason>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

Reterieve the list of reponse from recommendation with EditorialReason.

| Parameter | Data Type |
| -------- | ------- |
| rval | [DisapprovalReasonPage](../data/Dictionary/DisapprovalReasonPage.md) |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/Dictionary" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>Dictionary</ns2:service>
      <ns2:requestTime>1563874060124</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getDisapprovalReasonResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/Dictionary">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>DictionaryPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:disapprovalReason>
            <ns2:disapprovalReasonCode>7584</ns2:disapprovalReasonCode>
            <ns2:lang>EN</ns2:lang>
            <ns2:title>Use of comparative advertising, expressions guaranteeing safety, etc.</ns2:title>
            <ns2:description>The image you provided appear to contain comparative advertising, expressions guaranteeing safety, etc.</ns2:description>
            <ns2:recommendation>Please modify the prohibited expressions and request a new editorial review.</ns2:recommendation>
          </ns2:disapprovalReason>
        </ns2:values>
      </ns2:rval>
    </ns2:getDisapprovalReasonResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getGeographicLocation

### Request

Retrieves the information list of geo targeting.

| Parameter | Required | Data Type |
| --------- | -------- | --------- |
| selector | Yes | [GeographicLocationSelector](../data/Dictionary/GeographicLocationSelector.md) |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/Dictionary" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getGeographicLocation xmlns="http://im.yahooapis.jp/V201907/Dictionary">
      <selector>
        <lang>EN</lang>
      </selector>
    </getGeographicLocation>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

Retrieves the information list of geo targeting.

| Parameter | Data Type |
| -------- | ------- |
| rval | [GeographicLocationPage](../data/Dictionary/GeographicLocationPage.md) |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/Dictionary" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>Dictionary</ns2:service>
      <ns2:requestTime>1563874060170</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getGeographicLocationResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/Dictionary">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>DictionaryPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:geographicLocation>
            <ns2:code>TC-CI-00000100</ns2:code>
            <ns2:order>01000000</ns2:order>
            <ns2:name>hokkaido_pref</ns2:name>
            <ns2:fullName>hokkaido_pref</ns2:fullName>
            <ns2:child>
              <ns2:code>TC-CI-00000217</ns2:code>
              <ns2:parent>TC-CI-00000100</ns2:parent>
              <ns2:order>01000100</ns2:order>
              <ns2:name>akabirashi</ns2:name>
              <ns2:fullName>hokkaido_pref akabirashi</ns2:fullName>
            </ns2:child>
          </ns2:geographicLocation>
        </ns2:values>
      </ns2:rval>
    </ns2:getGeographicLocationResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getInterestCategory

### Request

Retrieves the list of interest category.

| Parameter | Required | Data Type |
| --------- | -------- | --------- |
| selector | Yes | [CategorySelector](../data/Dictionary/CategorySelector.md) |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/Dictionary" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getInterestCategory xmlns="http://im.yahooapis.jp/V201907/Dictionary">
      <selector>
        <lang>EN</lang>
      </selector>
    </getInterestCategory>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

Retrieves the list of interest category.

| Parameter | Data Type |
| -------- | ------- |
| rval | [CategoryPage](../data/Dictionary/CategoryPage.md) |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/Dictionary" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>Dictionary</ns2:service>
      <ns2:requestTime>1563874060197</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getInterestCategoryResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/Dictionary">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>DictionaryPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:category>
            <ns2:name>Autos</ns2:name>
            <ns2:child>
              <ns2:code>TC-IC-50110110100</ns2:code>
              <ns2:name>Automotive</ns2:name>
              <ns2:fullName>Automotive</ns2:fullName>
              <ns2:reachDesktop>1</ns2:reachDesktop>
              <ns2:reachSmartphone>2</ns2:reachSmartphone>
              <ns2:reachTablet>3</ns2:reachTablet>
            </ns2:child>
          </ns2:category>
        </ns2:values>
      </ns2:rval>
    </ns2:getInterestCategoryResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getSiteCategory

### Request

Retrieves the list of site category.

| Parameter | Required | Data Type |
| --------- | -------- | --------- |
| selector | Yes | [CategorySelector](../data/Dictionary/CategorySelector.md) |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/Dictionary" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getSiteCategory xmlns="http://im.yahooapis.jp/V201907/Dictionary">
      <selector>
        <lang>EN</lang>
      </selector>
    </getSiteCategory>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

Retrieves the list of site category.

| Parameter | Data Type |
| -------- | ------- |
| rval | [CategoryPage](../data/Dictionary/CategoryPage.md) |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/Dictionary" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>Dictionary</ns2:service>
      <ns2:requestTime>1563874060241</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getSiteCategoryResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/Dictionary">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>DictionaryPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:category>
            <ns2:name>News, Information</ns2:name>
            <ns2:child>
              <ns2:code>TC-SC-10110100100100</ns2:code>
              <ns2:name>News</ns2:name>
              <ns2:fullName>News</ns2:fullName>
              <ns2:reachDesktop>1</ns2:reachDesktop>
              <ns2:reachSmartphone>2</ns2:reachSmartphone>
              <ns2:reachTablet>3</ns2:reachTablet>
            </ns2:child>
          </ns2:category>
        </ns2:values>
      </ns2:rval>
    </ns2:getSiteCategoryResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getColorSet

### Request

Retrieves the list of color set.

| Parameter | Required | Data Type |
| --------- | -------- | --------- |
| selector | Yes | [ColorSetSelector](../data/Dictionary/ColorSetSelector.md) |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/Dictionary" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getColorSet xmlns="http://im.yahooapis.jp/V201907/Dictionary">
      <selector>
        <lang>EN</lang>
      </selector>
    </getColorSet>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

Retrieves the list of color set.

| Parameter | Data Type |
| -------- | ------- |
| rval | [ColorSetPage](../data/Dictionary/ColorSetPage.md) |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/Dictionary" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>Dictionary</ns2:service>
      <ns2:requestTime>1563874060147</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getColorSetResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/Dictionary">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>DictionaryPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:colorSetId>1000000001</ns2:colorSetId>
          <ns2:name>White</ns2:name>
          <ns2:colorSet>
            <ns2:element>BACKGROUND1_FROM</ns2:element>
            <ns2:color>#FCFCFC</ns2:color>
          </ns2:colorSet>
        </ns2:values>
      </ns2:rval>
    </ns2:getColorSetResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getOsVersion

### Request

Retrieves the version of OS.

| Parameter | Required | Data Type |
| --------- | -------- | --------- |
| selector | Yes | [OsVersionSelector](../data/Dictionary/OsVersionSelector.md) |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/Dictionary" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getOsVersion xmlns="http://im.yahooapis.jp/V201907/Dictionary">
      <selector>
        <osType>ANDROID</osType>
      </selector>
    </getOsVersion>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

Retrieves the version of OS.

| Parameter | Data Type |
| -------- | ------- |
| rval | [OsVersionPage](../data/Dictionary/OsVersionPage.md) |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/Dictionary" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>Dictionary</ns2:service>
      <ns2:requestTime>1563874060220</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getOsVersionResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/Dictionary">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>DictionaryPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:osVersion>
            <ns2:osType>ANDROID</ns2:osType>
            <ns2:version>8.0</ns2:version>
          </ns2:osVersion>
        </ns2:values>
      </ns2:rval>
    </ns2:getOsVersionResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getMediaAdFormat

### Request

Queries acceptable format (MediaAdFormat) of ad creatives.

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/Dictionary" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getMediaAdFormat xmlns="http://im.yahooapis.jp/V201907/Dictionary"/>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

Queries acceptable format (MediaAdFormat) of ad creatives.

| Parameter | Data Type |
| -------- | ------- |
| rval | [MediaAdFormatPage](../data/Dictionary/MediaAdFormatPage.md) |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/Dictionary" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>Dictionary</ns2:service>
      <ns2:requestTime>1563874060099</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getMediaAdFormatResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/Dictionary">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>DictionaryPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:mediaAdFormat>
            <ns2:adFormat>IAB_UAP_LEADER_BOARD</ns2:adFormat>
            <ns2:width>728</ns2:width>
            <ns2:height>90</ns2:height>
            <ns2:size>153600</ns2:size>
            <ns2:transparent>false</ns2:transparent>
            <ns2:logo>false</ns2:logo>
            <ns2:thumbnail>false</ns2:thumbnail>
            <ns2:sizeTo>13000</ns2:sizeTo>
            <ns2:maxWidth>600</ns2:maxWidth>
            <ns2:maxHeight>300</ns2:maxHeight>
            <ns2:aspectWidth>600</ns2:aspectWidth>
            <ns2:aspectHeight>300</ns2:aspectHeight>
            <ns2:staticImage>true</ns2:staticImage>
            <ns2:aspect>true</ns2:aspect>
          </ns2:mediaAdFormat>
        </ns2:values>
      </ns2:rval>
    </ns2:getMediaAdFormatResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

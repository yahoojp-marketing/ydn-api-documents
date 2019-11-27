# FeedDataService

FeedDataServiceでは、商品情報(TSV or ZIPファイル形式)をアップロードするURLの発行、処理状況の照会を行ないます。

#### WSDL

| environment |                                      url                                      |
| ----------- | ----------------------------------------------------------------------------- |
| production  | https://location.im.yahooapis.jp/services/V201911/FeedDataService?wsdl |
| sandbox     | https://sandbox.im.yahooapis.jp/services/V201911/FeedDataService?wsdl  |

#### Namespace

http://im.yahooapis.jp/V201911/FeedData

#### Service Overview

商品情報(TSV or ZIPファイル形式)をアップロードするURLの発行、処理状況の照会を行ないます。

#### Operation

FeedDataServiceで提供される操作を説明します。

+ [getUploadUrl](#getuploadurl)
+ [getUploadStatus](#getuploadstatus)

## getUploadUrl

### リクエスト

商品情報をアップロードするURLを発行します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| accountId | Yes | long |
| itemListUploadType | Yes | [ItemListUploadType](../data/FeedData/ItemListUploadType.md) |
| feedHolderId | Yes | long |
| isDebug | No | boolean |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/FeedData" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getUploadUrl xmlns="http://im.yahooapis.jp/V201911/FeedData">
      <accountId>1111</accountId>
      <itemListUploadType>UPDATE_ALL</itemListUploadType>
      <feedHolderId>222</feedHolderId>
    </getUploadUrl>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス

商品情報をアップロードするURLを発行します。

| パラメータ | データ型 |
| -------- | ------- |
| rval | [UploadUrlValue](../data/FeedData/UploadUrlValue.md) |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/FeedData" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>FeedData</ns2:service>
      <ns2:requestTime>1574409732924</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getUploadUrlResponse xmlns="http://im.yahooapis.jp/V201911/FeedData" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <rval>
        <accountId>1111</accountId>
        <itemListUploadType>UPDATE_ALL</itemListUploadType>
        <feedHolderId>2222</feedHolderId>
        <uploadUrl>https://location.im.yahooapis.jp/feedUpload/V201911/upload/KSwRXZuvEOH06e29wJuflTf9ZqYb.wn6ftbC_7stbaa6eF0TYw5HTZW8bwmNkway59_Nw62ExfIIFj2XPjXwNoDhtCRLjEVrbvtxIgxjxTpBmNqe0vItGSU-</uploadUrl>
      </rval>
    </getUploadUrlResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getUploadStatus

### リクエスト

アップロードした商品情報の処理状況を照会します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| selector | Yes | [FeedDataSelector](../data/FeedData/FeedDataSelector.md) |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/FeedData" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getUploadStatus xmlns="http://im.yahooapis.jp/V201911/FeedData" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <selector>
        <accountId>1111</accountId>
        <feedHolderIds>222</feedHolderIds>
        <feedHolderIds>333</feedHolderIds>
        <feedHolderIds>444</feedHolderIds>
        <feedHolderIds>555</feedHolderIds>
        <feedHolderIds>666</feedHolderIds>
        <itemListUploadIds>777</itemListUploadIds>
        <uploadStatuses>COMPLETED</uploadStatuses>
        <uploadStatuses>SYSTEM_ERROR</uploadStatuses>
        <uploadStatuses>FILE_FORMAT_ERROR</uploadStatuses>
        <uploadStatuses>UPLOADED</uploadStatuses>
        <dateRange>
          <startDate>20160101</startDate>
          <endDate>20170101</endDate>
        </dateRange>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>10</ns2:numberResults>
        </paging>
      </selector>
    </getUploadStatus>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス

アップロードした商品情報の処理状況を照会します。

| パラメータ | データ型 |
| -------- | ------- |
| rval | [FeedDataPage](../data/FeedData/FeedDataPage.md) |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/FeedData" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>FeedData</ns2:service>
      <ns2:requestTime>1574409732862</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getUploadStatusResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/FeedData">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>FeedDataPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedData>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:feedHolderId>2222</ns2:feedHolderId>
            <ns2:itemListUploadId>777</ns2:itemListUploadId>
            <ns2:itemListUploadType>UPDATE_ALL</ns2:itemListUploadType>
            <ns2:itemListUploadStatus>UPLOADED</ns2:itemListUploadStatus>
            <ns2:uploadDate>20180313143813</ns2:uploadDate>
            <ns2:completeDate>20180313143813</ns2:completeDate>
            <ns2:errorCount>2</ns2:errorCount>
            <ns2:errorRate>10.0</ns2:errorRate>
            <ns2:errorListDownloadUrl>https://location.im.yahooapis.jp/feedUpload/V201911/downloadErrorFile/gaChTAqlEOFLfOACISiRi2A1Cq_K3zZUXT95bA2X08mrAkckbvq4e79qoNiyq34QaHNTG_0dfevjoURTzf6dGnqGXQkEPgQp4gGsl59Z</ns2:errorListDownloadUrl>
            <ns2:itemListUploadSrc>API</ns2:itemListUploadSrc>
            <ns2:isDebug>false</ns2:isDebug>
          </ns2:feedData>
        </ns2:values>
      </ns2:rval>
    </ns2:getUploadStatusResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

# FeedDataService
FeedDataServiceでは、商品情報(TSVファイル形式)をアップロードするURLの発行、処理状況の照会を行ないます。

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201812/FeedDataService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201812/FeedDataService?wsdl |

#### Namespace
http://im.yahooapis.jp/V201812/FeedData

#### サービス概要
商品情報(TSVファイル形式)をアップロードするURLの発行、処理状況の照会を行ないます。

#### 操作
提供される操作を説明します。

+ [getUploadUrl](#getuploadurl)
+ [getUploadStatus](#getuploadstatus)

#### オブジェクト
[FeedData](../data/FeedData)

## getUploadUrl
商品情報をアップロードするURLを発行します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| accountId | ○ | xsd:long | アカウントID |
| itemListUploadType | ○ |  [ItemListUploadType](../data/FeedData/ItemListUploadType.md)| 処理種別 |
| feedHolderId | ○ |  xsd:long| FeedHolderId |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201812/FeedData" xmlns:ns2="http://im.yahooapis.jp/V201812">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getUploadUrl xmlns="http://im.yahooapis.jp/V201812/FeedData">
      <accountId>1111</accountId>
      <itemListUploadType>UPDATE_ALL</itemListUploadType>
      <feedHolderId>222</feedHolderId>
    </getUploadUrl>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [UploadUrlValue](../data/FeedData/UploadUrlValue.md) | アップロード一時URL |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201812/FeedData" xmlns:ns2="http://im.yahooapis.jp/V201812">
      <ns2:service>FeedData</ns2:service>
      <ns2:requestTime>1531887805443</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getUploadUrlResponse xmlns="http://im.yahooapis.jp/V201812/FeedData" xmlns:ns2="http://im.yahooapis.jp/V201812">
      <rval>
        <accountId>1111</accountId>
        <itemListUploadType>UPDATE_ALL</itemListUploadType>
        <feedHolderId>2222</feedHolderId>
        <uploadUrl>https://colo01.im.yahooapis.jp/feedUpload/V201812/upload/KSwRXZuvEOH06e29wJuflTf9ZqYb.wn6ftbC_7stbaa6eF0TYw5HTZW8bwmNkway59_Nw62ExfIIFj2XPjXwNoDhtCRLjEVrbvtxIgxjxTpBmNqe0vItGSU-</uploadUrl>
      </rval>
    </getUploadUrlResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getUploadStatus
アップロードした商品情報の処理状況を照会します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [FeedDataSelector](../data/FeedData/FeedDataSelector.md) | 取得条件 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201812/FeedData" xmlns:ns2="http://im.yahooapis.jp/V201812">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getUploadStatus xmlns="http://im.yahooapis.jp/V201812/FeedData" xmlns:ns2="http://im.yahooapis.jp/V201812">
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

#### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [FeedDataPage](../data/FeedData/FeedDataPage.md) | 登録結果 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201812/FeedData" xmlns:ns2="http://im.yahooapis.jp/V201812">
      <ns2:service>FeedData</ns2:service>
      <ns2:requestTime>1531887804443</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getUploadStatusResponse xmlns="http://im.yahooapis.jp/V201812" xmlns:ns2="http://im.yahooapis.jp/V201812/FeedData">
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
            <ns2:errorCount>2</ns2:errorCount>
            <ns2:errorListDownloadUrl>https://colo01.im.yahooapis.jp/feedUpload/V201812/downloadErrorFile/gaChTAqlEOFLfOACISiRi2A1Cq_K3zZUXT95bA2X08mrAkckbvq4e79qoNiyq34QaHNTG_0dfevjoURTzf6dGnqGXQkEPgQp4gGsl59Z</ns2:errorListDownloadUrl>
          </ns2:feedData>
        </ns2:values>
      </ns2:rval>
    </ns2:getUploadStatusResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

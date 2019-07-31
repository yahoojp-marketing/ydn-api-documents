

# FeedDataService

FeedDataServiceでは、商品情報(TSV or ZIPファイル形式)をアップロードするURLの発行、処理状況の照会を行ないます。

#### WSDL

| environment |                                      url                                      |
| ----------- | ----------------------------------------------------------------------------- |
| production  | https://location.im.yahooapis.jp/services/V201907/FeedDataService?wsdl |
| sandbox     | https://sandbox.im.yahooapis.jp/services/V201907/FeedDataService?wsdl  |

#### Namespace

http://im.yahooapis.jp/V201907/FeedData

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

### レスポンス

商品情報をアップロードするURLを発行します。

| パラメータ | データ型 |
| -------- | ------- |
| rval | [UploadUrlValue](../data/FeedData/UploadUrlValue.md) |

## getUploadStatus

### リクエスト

アップロードした商品情報の処理状況を照会します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| selector | Yes | [FeedDataSelector](../data/FeedData/FeedDataSelector.md) |

### レスポンス

アップロードした商品情報の処理状況を照会します。

| パラメータ | データ型 |
| -------- | ------- |
| rval | [FeedDataPage](../data/FeedData/FeedDataPage.md) |




# DictionaryService

DictionaryServiceは、審査否認理由、地域情報、インタレストカテゴリー、サイトカテゴリーの一覧を提供します。

#### WSDL

| environment |                                      url                                      |
| ----------- | ----------------------------------------------------------------------------- |
| production  | https://location.im.yahooapis.jp/services/V201907/DictionaryService?wsdl |
| sandbox     | https://sandbox.im.yahooapis.jp/services/V201907/DictionaryService?wsdl  |

#### Namespace

http://im.yahooapis.jp/V201907/Dictionary

#### Service Overview

各種情報の一覧を取得します。

#### Operation

DictionaryServiceで提供される操作を説明します。

+ [getDisapprovalReason](#getdisapprovalreason)
+ [getGeographicLocation](#getgeographiclocation)
+ [getInterestCategory](#getinterestcategory)
+ [getSiteCategory](#getsitecategory)
+ [getColorSet](#getcolorset)
+ [getOsVersion](#getosversion)
+ [getMediaAdFormat](#getmediaadformat)


## getDisapprovalReason

### リクエスト

EditorialReasonと推奨する対応方法の一覧を取得します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| selector | Yes | [DisapprovalReasonSelector](../data/Dictionary/DisapprovalReasonSelector.md) |

### レスポンス

EditorialReasonと推奨する対応方法の一覧を取得します。

| パラメータ | データ型 |
| -------- | ------- |
| rval | [DisapprovalReasonPage](../data/Dictionary/DisapprovalReasonPage.md) |

## getGeographicLocation

### リクエスト

地域情報の一覧を取得します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| selector | Yes | [GeographicLocationSelector](../data/Dictionary/GeographicLocationSelector.md) |

### レスポンス

地域情報の一覧を取得します。

| パラメータ | データ型 |
| -------- | ------- |
| rval | [GeographicLocationPage](../data/Dictionary/GeographicLocationPage.md) |

## getInterestCategory

### リクエスト

インタレストカテゴリーリストを取得します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| selector | Yes | [CategorySelector](../data/Dictionary/CategorySelector.md) |

### レスポンス

インタレストカテゴリーリストを取得します。

| パラメータ | データ型 |
| -------- | ------- |
| rval | [CategoryPage](../data/Dictionary/CategoryPage.md) |

## getSiteCategory

### リクエスト

サイトトカテゴリーリストを取得します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| selector | Yes | [CategorySelector](../data/Dictionary/CategorySelector.md) |

### レスポンス

サイトトカテゴリーリストを取得します。

| パラメータ | データ型 |
| -------- | ------- |
| rval | [CategoryPage](../data/Dictionary/CategoryPage.md) |

## getColorSet

### リクエスト

カラーセットの一覧を取得します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| selector | Yes | [ColorSetSelector](../data/Dictionary/ColorSetSelector.md) |

### レスポンス

カラーセットの一覧を取得します。

| パラメータ | データ型 |
| -------- | ------- |
| rval | [ColorSetPage](../data/Dictionary/ColorSetPage.md) |

## getOsVersion

### リクエスト

OSのバージョンを取得します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| selector | Yes | [OsVersionSelector](../data/Dictionary/OsVersionSelector.md) |

### レスポンス

OSのバージョンを取得します。

| パラメータ | データ型 |
| -------- | ------- |
| rval | [OsVersionPage](../data/Dictionary/OsVersionPage.md) |

## getMediaAdFormat

### リクエスト

入稿可能な画像の形式(MediaAdFormat)を照会します。


### レスポンス

入稿可能な画像の形式(MediaAdFormat)を照会します。

| パラメータ | データ型 |
| -------- | ------- |
| rval | [MediaAdFormatPage](../data/Dictionary/MediaAdFormatPage.md) |


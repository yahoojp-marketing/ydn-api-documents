

# AdGroupAdService

AdGroupAdServiceは広告の操作を提供します。

#### WSDL

| environment |                                      url                                      |
| ----------- | ----------------------------------------------------------------------------- |
| production  | https://location.im.yahooapis.jp/services/V201907/AdGroupAdService?wsdl |
| sandbox     | https://sandbox.im.yahooapis.jp/services/V201907/AdGroupAdService?wsdl  |

#### Namespace

http://im.yahooapis.jp/V201907/AdGroupAd

#### Service Overview

広告の取得と更新を行います。

#### Operation

AdGroupAdServiceで提供される操作を説明します。

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)


## get

### リクエスト

広告の情報を取得します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| selector | Yes | [AdGroupAdSelector](../data/AdGroupAd/AdGroupAdSelector.md) |

### レスポンス

広告の情報を取得します。

| パラメータ | データ型 |
| -------- | ------- |
| rval | [AdGroupAdPage](../data/AdGroupAd/AdGroupAdPage.md) |

## mutate(ADD)

### リクエスト

広告を追加します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| operations | Yes | [AdGroupAdOperation](../data/AdGroupAd/AdGroupAdOperation.md) |

### レスポンス

広告を追加します。

| パラメータ | データ型 |
| -------- | ------- |
| rval | [AdGroupAdReturnValue](../data/AdGroupAd/AdGroupAdReturnValue.md) |

## mutate(SET)

### リクエスト

広告を変更します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| operations | Yes | [AdGroupAdOperation](../data/AdGroupAd/AdGroupAdOperation.md) |

### レスポンス

広告を変更します。

| パラメータ | データ型 |
| -------- | ------- |
| rval | [AdGroupAdReturnValue](../data/AdGroupAd/AdGroupAdReturnValue.md) |

## mutate(REMOVE)

### リクエスト

広告を削除します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| operations | Yes | [AdGroupAdOperation](../data/AdGroupAd/AdGroupAdOperation.md) |

### レスポンス

広告を削除します。

| パラメータ | データ型 |
| -------- | ------- |
| rval | [AdGroupAdReturnValue](../data/AdGroupAd/AdGroupAdReturnValue.md) |


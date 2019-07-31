

# StatsService

StatsServiceは、キャンペーン、広告グループ、広告、画像、動画の単位で統計情報の取得を行います。

#### WSDL

| environment |                                      url                                      |
| ----------- | ----------------------------------------------------------------------------- |
| production  | https://location.im.yahooapis.jp/services/V201907/StatsService?wsdl |
| sandbox     | https://sandbox.im.yahooapis.jp/services/V201907/StatsService?wsdl  |

#### Namespace

http://im.yahooapis.jp/V201907/Stats

#### Service Overview

キャンペーン、広告グループ、広告、画像、動画の単位で統計情報の取得を行います。

#### Operation

StatsServiceで提供される操作を説明します。

+ [get](#get)


## get

### リクエスト

キャンペーン、広告グループ、広告、画像、動画の単位で統計情報の取得を行います。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| selector | Yes | [StatsSelector](../data/Stats/StatsSelector.md) |

### レスポンス

キャンペーン、広告グループ、広告、画像、動画の単位で統計情報の取得を行います。

| パラメータ | データ型 |
| -------- | ------- |
| rval | [StatsPage](../data/Stats/StatsPage.md) |


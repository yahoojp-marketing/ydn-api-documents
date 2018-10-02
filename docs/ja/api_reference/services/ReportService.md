# ReportService
ReportServiceでは、レポートの取得および作成・削除を行います。<br>
またレポートのダウンロードURLを取得する操作が提供されます。

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201809/ReportService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201809/ReportService?wsdl |

#### Namespace
http://im.yahooapis.jp/V201809/Report

#### サービス概要
以下の操作が実行可能です。
- レポートの取得
- レポートの登録
- レポートの削除
- レポート集計完了日付の取得

【レポートダウンロードジョブの登録上限数】
- レポートダウンロードジョブは、標準認証と代行認証それぞれで最大60件まで登録できます(ReportJobStatus：COMPLETED又はFAILEDは除く)。<br>
※登録上限数に達した状態から新たにダウンロードジョブを登録する場合は、登録済みのダウンロードジョブを削除する必要があります。<br>

【注意事項】
- レポートのダウンロードは、getメソッドで取得したURLから行います。<br>URLが有効な期間は、ステータスがCOMPLETEDになってから5分間です。
- すべてのレポートタイプにおいて配信実績のないデータは出力されません。
- レポートダウンロードジョブは、リクエストしてから1週間（7日間）で自動的に削除されます。

#### 操作
ReportServiceで提供される操作を説明します。

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(REMOVE)](#mutateremove)
+ [getClosedDate](#getcloseddate)

#### オブジェクト
[Report](../data/Report)

## get

### リクエスト
レポートに関する情報を取得します。レポートのダウンロードURLもgetメソッドで取得します。

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [ReportSelector](../data/Report/ReportSelector.md) | 操作の対象とするレポートです。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201809/Report" xmlns:ns2="http://im.yahooapis.jp/V201809">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201809/Report" xmlns:ns2="http://im.yahooapis.jp/V201809">
      <selector>
        <accountId>12345</accountId>
        <reportIds>1</reportIds>
        <reportIds>2</reportIds>
        <reportJobIds>100</reportJobIds>
        <reportJobIds>1000</reportJobIds>
        <reportJobStatuses>ACCEPTED</reportJobStatuses>
        <reportJobStatuses>COMPLETED</reportJobStatuses>
        <paging>
          <ns2:startIndex>10</ns2:startIndex>
          <ns2:numberResults>1340</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 |
|---|---|---|
| rval | [ReportPage](../data/Report/ReportPage.md) | 取得されるレポート定義のコンテナです。 | error | [Error](../data/Report/Error.md) | エラーです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201809/Report" xmlns:ns2="http://im.yahooapis.jp/V201809">
      <ns2:service>Report</ns2:service>
      <ns2:requestTime>1536568327660</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201809" xmlns:ns2="http://im.yahooapis.jp/V201809/Report">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>ReportPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportRecord>
            <ns2:accountId>12345</ns2:accountId>
            <ns2:reportJobId>100</ns2:reportJobId>
            <ns2:reportId>1</ns2:reportId>
            <ns2:reportName>sample Report</ns2:reportName>
            <ns2:status>COMPLETED</ns2:status>
            <ns2:reportDownloadUrl>https://colo01.im.yahooapis.jp/ReportService/V201809/XXXXXXXX</ns2:reportDownloadUrl>
          </ns2:reportRecord>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)

### リクエスト
レポートを作成します。

| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [ReportJobOperation](../data/Report/ReportJobOperation.md) | 操作の対象となるレポートおよび操作の内容を表します。 |


### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [ReportReturnValue](../data/Report/ReportReturnValue.md) | 操作結果を含むレポートのコンテナです。 | error | [Error](../data/Report/Error.md) | エラーです。 |

##### レスポンスサンプル


## mutate(REMOVE)

### リクエスト
レポートを削除します。

| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [ReportJobOperation](../data/Report/ReportJobOperation.md) | 操作の対象となるレポートおよび操作の内容を表します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201809/Report" xmlns:ns2="http://im.yahooapis.jp/V201809">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201809/Report">
      <operations>
        <operator>REMOVE</operator>
        <accountId>11111</accountId>
        <operand>
          <accountId>1111</accountId>
          <reportId>2222</reportId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [ReportReturnValue](../data/Report/ReportReturnValue.md) | 操作結果を含むレポートのコンテナです。 | error | [Error](../data/Report/Error.md) | エラーです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201809/Report" xmlns:ns2="http://im.yahooapis.jp/V201809">
      <ns2:service>Report</ns2:service>
      <ns2:requestTime>1536568327691</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201809" xmlns:ns2="http://im.yahooapis.jp/V201809/Report">
      <ns2:rval>
        <ListReturnValue.Type>ReportReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportRecord>
            <ns2:accountId>12345</ns2:accountId>
            <ns2:reportJobId>100</ns2:reportJobId>
            <ns2:reportId>1</ns2:reportId>
            <ns2:reportName>sample Report</ns2:reportName>
            <ns2:status>COMPLETED</ns2:status>
            <ns2:reportDownloadUrl>https://colo01.im.yahooapis.jp/ReportService/V201809/XXXXXXXX</ns2:reportDownloadUrl>
          </ns2:reportRecord>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getClosedDate

### リクエスト
レポート集計完了日付取得を実行します。

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [ReportClosedDateSelector](../data/Report/ReportClosedDateSelector.md) | 操作の対象とするレポートを指定します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201809/Report" xmlns:ns2="http://im.yahooapis.jp/V201809">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getClosedDate xmlns="http://im.yahooapis.jp/V201809/Report">
      <selector>
        <accountId>12345</accountId>
      </selector>
    </getClosedDate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 |
|---|---|---|
| rval | [ReportClosedDateValue](../data/Report/ReportClosedDateValue.md) | 取得される情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201809/Report" xmlns:ns2="http://im.yahooapis.jp/V201809">
      <ns2:service>Report</ns2:service>
      <ns2:requestTime>1536568327711</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getClosedDateResponse xmlns="http://im.yahooapis.jp/V201809" xmlns:ns2="http://im.yahooapis.jp/V201809/Report">
      <ns2:rval>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:key>FREQ_REPORT_CLOSED_DATE</ns2:key>
          <ns2:closedDate>20180101</ns2:closedDate>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:key>REPORT_CLOSED_DATE</ns2:key>
          <ns2:closedDate>20180101</ns2:closedDate>
        </ns2:values>
      </ns2:rval>
    </ns2:getClosedDateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

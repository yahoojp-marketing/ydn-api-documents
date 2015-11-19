# ReportService
ReportServiceでは、レポートの取得および作成・削除を行います。<br>
またレポートのダウンロードURLを取得する操作が提供されます。
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V5.2/ReportService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/V5.2/ReportService?wsdl|
#### Namespace
http://im.yahooapis.jp/V5
#### サービス概要
レポートの取得および作成・削除、レポート集計完了日付取得を行います。<br>
またレポートのダウンロードURLを取得する操作が提供されます。<br>
<br>
【注意事項】<br>
・レポートのダウンロードは、getDownloadUrlで作成したURLから行います。<br>
　URLの有効期限は5分です。<br>
　URLを作成したIPのみリクエスト可能です。<br>
・1アカウントにつき同時に登録できるレポートのダウンロードジョブの上限は、30件までです。<br>
　30件を超えた場合、下記のエラーが発生します。<br>
　不要なダウンロードジョブを削除した後、改めてダウンロードジョブを追加してください。<br>
　『240001：Over limit of uncompleted report download job.』<br>
・また、完了済みを含め、１アカウントにつき最大2万件までレポートのダウンロードジョブは登録可能です。<br>
　2万件を超えた場合は、下記のエラーが発生します。<br>
　不要なダウンロードジョブを削除した後、改めてダウンロードジョブを追加してください。<br>
　『240002：Over limit of report download job.』<br>
・なお、レポートのダウンロードジョブは1週間で自動的に削除されます。<br>

#### 操作
ReportServiceで提供される操作を説明します。
## get
### リクエスト
レポートに関する情報を取得します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [ReportSelector](../data/ReportSelector.md) | 操作の対象とするレポートです。 | 

##### ＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:reportIds>9000000001</ns1:reportIds>
                <ns1:reportIds>9000000002</ns1:reportIds>
                <ns1:reportIds>9000000003</ns1:reportIds>
                <ns1:reportJobIds>8000000001</ns1:reportJobIds>
                <ns1:reportJobIds>8000000002</ns1:reportJobIds>
                <ns1:reportJobIds>8000000003</ns1:reportJobIds>
                <ns1:reportJobStatuses>COMPLETED</ns1:reportJobStatuses>
                <ns1:reportJobStatuses>FAILED</ns1:reportJobStatuses>
                <ns1:paging>
                    <ns1:startIndex>1</ns1:startIndex>
                    <ns1:numberResults>20</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### ＜リクエストサンプル＞（代行認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:reportIds>9000000001</ns1:reportIds>
                <ns1:reportIds>9000000002</ns1:reportIds>
                <ns1:reportIds>9000000003</ns1:reportIds>
                <ns1:reportJobIds>8000000001</ns1:reportJobIds>
                <ns1:reportJobIds>8000000002</ns1:reportJobIds>
                <ns1:reportJobIds>8000000003</ns1:reportJobIds>
                <ns1:reportJobStatuses>COMPLETED</ns1:reportJobStatuses>
                <ns1:reportJobStatuses>FAILED</ns1:reportJobStatuses>
                <ns1:paging>
                    <ns1:startIndex>1</ns1:startIndex>
                    <ns1:numberResults>20</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [ReportPage](../data/ReportPage.md) | 取得されるレポート定義のコンテナです。 | error | [Error](../data/Error.md) | エラーです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>ReportService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:rval>
                <ns1:totalNumEntries>3</ns1:totalNumEntries>
                <ns1:Page.Type>ReportPage</ns1:Page.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportRecord>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:reportJobId>8000000001</ns1:reportJobId>
                        <ns1:reportId>9000000001</ns1:reportId>
                        <ns1:reportName>SandboxAccountReport_csv</ns1:reportName>
                        <ns1:requestTime>20120403175909</ns1:requestTime>
                        <ns1:completeTime>20120403175910</ns1:completeTime>
                        <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
                        <ns1:dateRange>
                            <ns1:startDate>20120303</ns1:startDate>
                            <ns1:endDate>20120402</ns1:endDate>
                        </ns1:dateRange>
                        <ns1:status>COMPLETED</ns1:status>
                    </ns1:reportRecord>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportRecord>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:reportJobId>8000000002</ns1:reportJobId>
                        <ns1:reportId>9000000002</ns1:reportId>
                        <ns1:reportName>SandboxCampaignReport_csv</ns1:reportName>
                        <ns1:requestTime>20120403175908</ns1:requestTime>
                        <ns1:completeTime>20120403175909</ns1:completeTime>
                        <ns1:dateRangeType>YESTERDAY</ns1:dateRangeType>
                        <ns1:status>COMPLETED</ns1:status>
                     </ns1:reportRecord>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportRecord>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:reportJobId>8000000003</ns1:reportJobId>
                        <ns1:reportId>9000000003</ns1:reportId>
                        <ns1:reportName>SandboxAdgroupReport_csv</ns1:reportName>
                        <ns1:requestTime>20120403175911</ns1:requestTime>
                        <ns1:completeTime>20120403175912</ns1:completeTime>
                        <ns1:dateRangeType>YESTERDAY</ns1:dateRangeType>
                        <ns1:status>FAILED</ns1:status>
                        <ns1:jobErrorDetail>Over limit of file size.</ns1:jobErrorDetail>
                    </ns1:reportRecord>
                </ns1:values>
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
### リクエスト
レポートを作成します。

| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [ReportOperation](../data/ReportOperation.md) | 操作の対象となるレポートおよび操作の内容を表します。 | 

##### ＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"> 
    <SOAP-ENV:Header> 
        <ns1:RequestHeader> 
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license> 
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId> 
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword> 
        </ns1:RequestHeader> 
    </SOAP-ENV:Header> 
    <SOAP-ENV:Body> 
        <ns1:mutate> 
            <ns1:operations> 
                <ns1:operator>ADD</ns1:operator> 
                <ns1:accountId>1000000001</ns1:accountId> 
                <ns1:operand> 
                    <ns1:reportId>9000000001</ns1:reportId> 
                </ns1:operand> 
                <ns1:operand> 
                    <ns1:reportId>9000000002</ns1:reportId> 
                </ns1:operand> 
            </ns1:operations> 
         </ns1:mutate> 
    </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```

##### ＜リクエストサンプル＞（代行認証）
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"> 
    <SOAP-ENV:Header> 
        <ns1:RequestHeader> 
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license> 
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId> 
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword> 
            <ns1:accountId>100000001</ns1:accountId> 
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxxx</ns1:onBehalfOfAccountId> 
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword> 
        </ns1:RequestHeader> 
    </SOAP-ENV:Header> 
    <SOAP-ENV:Body> 
        <ns1:mutate> 
            <ns1:operations> 
                <ns1:operator>ADD</ns1:operator> 
                <ns1:accountId>1000000001</ns1:accountId> 
                <ns1:operand> 
                    <ns1:reportId>9000000001</ns1:reportId> 
                </ns1:operand> 
                <ns1:operand> 
                    <ns1:reportId>9000000002</ns1:reportId> 
                </ns1:operand> 
            </ns1:operations> 
         </ns1:mutate> 
    </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [ReportReturnValue](../data/ReportReturnValue.md) | 操作結果を含むレポートのコンテナです。 | error | [Error](../data/Error.md) | エラーです。 | 

##### レスポンスサンプル
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"> 
    <SOAP-ENV:Header> 
        <ns1:ResponseHeader> 
            <ns1:service>ReportService</ns1:service> 
            <ns1:remainingQuota>100</ns1:remainingQuota> 
            <ns1:quotaUsedForThisRequest>2</ns1:quotaUsedForThisRequest> 
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis> 
        </ns1:ResponseHeader> 
    </SOAP-ENV:Header> 
    <SOAP-ENV:Body> 
        <ns1:mutateResponse> 
            <ns1:rval> 
                <ns1:ListReturnValue.Type>ReportReturnValue</ns1:ListReturnValue.Type> 
                <ns1:Operation.Type>ADD</ns1:Operation.Type> 
                <ns1:values> 
                    <ns1:operationSucceeded>true</ns1:operationSucceeded> 
                    <ns1:reportRecord> 
                        <ns1:accountId>1000000001</ns1:accountId> 
                        <ns1:reportJobId>8000000001</ns1:reportJobId> 
                        <ns1:reportId>9000000001</ns1:reportId> 
                        <ns1:reportName>SandboxAccountReport_csv</ns1:reportName> 
                        <ns1:requestTime>20120403175909</ns1:requestTime> 
                        <ns1:completeTime /> 
                        <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType> 
                        <ns1:dateRange> 
                            <ns1:startDate>20120303</ns1:startDate> 
                            <ns1:endDate>20120402</ns1:endDate> 
                        </ns1:dateRange> 
                        <ns1:status>IN_PROGRESS</ns1:status> 
                     </ns1:reportRecord> 
                     <ns1:reportRecord> 
                         <ns1:accountId>1000000001</ns1:accountId> 
                         <ns1:reportJobId>8000000002</ns1:reportJobId> 
                         <ns1:reportId>9000000002</ns1:reportId> 
                         <ns1:reportName>SandboxCampaignReport_csv</ns1:reportName> 
                         <ns1:requestTime>20120403175908</ns1:requestTime> 
                         <ns1:completeTime /> 
                         <ns1:dateRangeType>YESTERDAY</ns1:dateRangeType> 
                         <ns1:status>IN_PROGRESS</ns1:status> 
                    </ns1:reportRecord> 
                </ns1:values> 
            </ns1:rval> 
        </ns1:mutateResponse> 
    </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
### リクエスト
レポートを削除します。

| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [ReportOperation](../data/ReportOperation.md) | 操作の対象となるレポートおよび操作の内容を表します。 | 

##### ＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
xmlns:ns1="http://im.yahooapis.jp/V5"> 
    <SOAP-ENV:Header> 
        <ns1:RequestHeader> 
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license> 
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId> 
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword> 
        </ns1:RequestHeader> 
    </SOAP-ENV:Header> 
    <SOAP-ENV:Body> 
        <ns1:mutate> 
            <ns1:operations> 
                <ns1:operator>REMOVE</ns1:operator> 
                <ns1:accountId>1000000001</ns1:accountId>                
                <ns1:operand> 
                    <ns1:reportJobId>8000000001</ns1:reportJobId>                     
                </ns1:operand> 
                <ns1:operand> 
                    <ns1:reportJobId>8000000002</ns1:reportJobId>                     
                </ns1:operand> 
            </ns1:operations> 
        </ns1:mutate> 
    </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```

##### ＜リクエストサンプル＞（代行認証）
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
xmlns:ns1="http://im.yahooapis.jp/V5"> 
    <SOAP-ENV:Header> 
        <ns1:RequestHeader> 
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license> 
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId> 
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword> 
            <ns1:accountId>100000001</ns1:accountId> 
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxxx</ns1:onBehalfOfAccountId> 
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword> 
        </ns1:RequestHeader> 
    </SOAP-ENV:Header> 
    <SOAP-ENV:Body> 
        <ns1:mutate> 
            <ns1:operations> 
                <ns1:operator>REMOVE</ns1:operator> 
                <ns1:accountId>1000000001</ns1:accountId>                
                <ns1:operand> 
                    <ns1:reportJobId>8000000001</ns1:reportJobId>                     
                </ns1:operand> 
                <ns1:operand> 
                    <ns1:reportJobId>8000000002</ns1:reportJobId>                     
                </ns1:operand> 
            </ns1:operations> 
        </ns1:mutate> 
    </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [ReportReturnValue](../data/ReportReturnValue.md) | 操作結果を含むレポートのコンテナです。 | error | [Error](../data/Error.md) | エラーです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"> 
    <SOAP-ENV:Header> 
        <ns1:ResponseHeader> 
            <ns1:service>ReportService</ns1:service> 
            <ns1:remainingQuota>100</ns1:remainingQuota> 
            <ns1:quotaUsedForThisRequest>2</ns1:quotaUsedForThisRequest> 
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis> 
        </ns1:ResponseHeader> 
    </SOAP-ENV:Header> 
    <SOAP-ENV:Body> 
        <ns1:mutateResponse> 
            <ns1:rval> 
                <ns1:ListReturnValue.Type>ReportReturnValue</ns1:ListReturnValue.Type> 
                <ns1:Operation.Type>REMOVE</ns1:Operation.Type> 
                <ns1:values> 
                    <ns1:operationSucceeded>true</ns1:operationSucceeded> 
                    <ns1:reportRecord> 
                        <ns1:reportJobId>8000000001</ns1:reportJobId> 
                    </ns1:reportRecord> 
                </ns1:values> 
                <ns1:values> 
                    <ns1:operationSucceeded>true</ns1:operationSucceeded> 
                    <ns1:reportRecord> 
                        <ns1:reportJobId>8000000002</ns1:reportJobId> 
                    </ns1:reportRecord> 
                </ns1:values> 
            </ns1:rval> 
        </ns1:mutateResponse> 
    </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```

## getDownloadUrl
### リクエスト
レポートをダウンロードするためのURLを取得します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [ReportDownloadUrlSelector](../data/ReportDownloadUrlSelector.md) | 取得されるダウンロードURLのエントリーです。 | 

##### ＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"> 
    <SOAP-ENV:Header> 
        <ns1:RequestHeader> 
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license> 
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId> 
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword> 
        </ns1:RequestHeader> 
    </SOAP-ENV:Header> 
    <SOAP-ENV:Body> 
        <ns1:getDownloadUrl> 
            <ns1:selector> 
                <ns1:accountId>1000000001</ns1:accountId>    
                <ns1:reportJobIds>8000000001</ns1:reportJobIds> 
                <ns1:reportJobIds>8000000002</ns1:reportJobIds>  
                <ns1:paging> 
                    <ns1:startIndex>1</ns1:startIndex> 
                    <ns1:numberResults>20</ns1:numberResults> 
                </ns1:paging>                
            </ns1:selector> 
        </ns1:getDownloadUrl> 
    </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```

##### ＜リクエストサンプル＞（代行認証）
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"> 
    <SOAP-ENV:Header> 
        <ns1:RequestHeader> 
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license> 
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId> 
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword> 
            <ns1:accountId>100000001</ns1:accountId> 
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxxx</ns1:onBehalfOfAccountId> 
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword> 
        </ns1:RequestHeader> 
    </SOAP-ENV:Header> 
    <SOAP-ENV:Body> 
        <ns1:getDownloadUrl> 
            <ns1:selector> 
                <ns1:accountId>1000000001</ns1:accountId>    
                <ns1:reportJobIds>8000000001</ns1:reportJobIds> 
                <ns1:reportJobIds>8000000002</ns1:reportJobIds> 
                <ns1:paging> 
                    <ns1:startIndex>1</ns1:startIndex> 
                    <ns1:numberResults>20</ns1:numberResults> 
                </ns1:paging>  
            </ns1:selector> 
        </ns1:getDownloadUrl> 
    </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [ReportDownloadUrlPage](../data/ReportDownloadUrlPage.md) | 取得されるダウンロードURLのエントリーです。 | error | [Error](../data/Error.md) | エラーです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"> 
    <SOAP-ENV:Header> 
        <ns1:ResponseHeader> 
            <ns1:service>ReportService</ns1:service> 
            <ns1:remainingQuota>100</ns1:remainingQuota> 
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest> 
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis> 
        </ns1:ResponseHeader> 
    </SOAP-ENV:Header> 
    <SOAP-ENV:Body> 
        <ns1:getDownloadUrlResponse> 
            <ns1:rval> 
                <ns1:totalNumEntries>2</ns1:totalNumEntries> 
                <ns1:Page.Type>ReportPage</ns1:Page.Type> 
                <ns1:values> 
                    <ns1:operationSucceeded>true</ns1:operationSucceeded> 
                    <ns1:reportDownloadUrl> 
                        <ns1:accountId>1000000001</ns1:accountId> 
                        <ns1:reportJobId>8000000001</ns1:reportJobId> 
                        <ns1:reportId>9000000001</ns1:reportId> 
                        <ns1:reportName>SandboxAccountReport_csv</ns1:reportName> 
                        <ns1:requestTime>20120403164910</ns1:requestTime> 
                        <ns1:completeTime>20120403165126</ns1:completeTime> 
                        <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType> 
                        <ns1:dateRange> 
                            <ns1:startDate>20120303</ns1:startDate> 
                            <ns1:endDate>20120402</ns1:endDate> 
                        </ns1:dateRange> 
                        <ns1:status>COMPLETED</ns1:status> 
                        <ns1:downloadUrl>https://sample.api.yahooapis.jp/report/V5/download/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX</ns1:downloadUrl> 
                    </ns1:reportDownloadUrl> 
                </ns1:values> 
                <ns1:values> 
                    <ns1:operationSucceeded>true</ns1:operationSucceeded> 
                    <ns1:reportDownloadUrl> 
                    <ns1:accountId>1000000001</ns1:accountId> 
                    <ns1:reportJobId>8000000002</ns1:reportJobId> 
                    <ns1:reportId>9000000002</ns1:reportId> 
                    <ns1:reportName>SandboxCampaignReport_csv</ns1:reportName> 
                    <ns1:requestTime>20120403175908</ns1:requestTime> 
                    <ns1:completeTime>20120403175952</ns1:completeTime> 
                    <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType> 
                    <ns1:dateRange> 
                    <ns1:startDate>20120303</ns1:startDate> 
                    <ns1:endDate>20120402</ns1:endDate> 
                    </ns1:dateRange> 
                    <ns1:status>COMPLETED</ns1:status> 
                    <ns1:downloadUrl>https://sample.api.yahooapis.jp/report/V5/download/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX</ns1:downloadUrl> 
                    </ns1:reportDownloadUrl> 
                </ns1:values> 
            </ns1:rval> 
        </ns1:getDownloadUrlResponse> 
    </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```

## getClosedDate
### リクエスト
レポート集計完了日付取得を実行します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [ReportClosedDateSelector](../data/ReportClosedDateSelector.md) | 操作の対象とするレポートを指定します。 | 

##### ＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"> 
    <SOAP-ENV:Header> 
        <ns1:RequestHeader> 
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license> 
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId> 
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword> 
        </ns1:RequestHeader> 
    </SOAP-ENV:Header> 
    <SOAP-ENV:Body> 
        <ns1:getClosedDate> 
            <ns1:selector> 
                <ns1:accountId>1000000001</ns1:accountId> 
            </ns1:selector> 
        </ns1:getClosedDate> 
    </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```

##### ＜リクエストサンプル＞（代行認証）
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"> 
    <SOAP-ENV:Header> 
        <ns1:RequestHeader> 
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license> 
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId> 
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword> 
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxxx</ns1:onBehalfOfAccountId> 
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword> 
        </ns1:RequestHeader> 
    </SOAP-ENV:Header> 
    <SOAP-ENV:Body> 
        <ns1:getClosedDate> 
            <ns1:selector> 
                <ns1:accountId>1000000001</ns1:accountId> 
            </ns1:selector> 
        </ns1:getClosedDate> 
    </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [ReportClosedDateValue](../data/ReportClosedDateValue.md) | 取得される情報のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>ReportService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getClosedDateResponse>
            <ns1:rval>
                <ns1:operationSucceeded>true</ns1:operationSucceeded>
                <ns1:closedDate>20120303</ns1:closedDate>
            </ns1:rval>
        </ns1:getClosedDateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

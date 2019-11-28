# CampaignMigrationService

CampaignMigrationServiceは目的なしのキャンペーンを一括で目的ありのキャンペーンにマイグレーションする機能を提供します。

#### WSDL

| environment |                                      url                                      |
| ----------- | ----------------------------------------------------------------------------- |
| production  | https://location.im.yahooapis.jp/services/V201911/CampaignMigrationService?wsdl |
| sandbox     | https://sandbox.im.yahooapis.jp/services/V201911/CampaignMigrationService?wsdl  |

#### Namespace

http://im.yahooapis.jp/V201911/CampaignMigration

#### Service Overview

目的なしのキャンペーンを一括で目的ありのキャンペーンにマイグレーションする機能を提供します。

#### マイグレーションの流れ

1. getCampaignDownloadUrlでマイグレーション用csvファイルをダウンロードするURLを取得します。
1. レスポンス内に含まれるdownloadUrlからマイグレーション用csvファイルを取得します。
1. csvファイルを編集してマイグレーションの内容を定義します。
   1. csvファイルの編集方法については[ヘルプ](https://ads-help.yahoo.co.jp/yahooads/display/articledetail?lan=ja&aid=51680)をご参照ください。
1. getUploadUrlでマイグレーション用csvファイルのアップロード先URLをリクエストします。
1. レスポンス内に含まれるuploadUrlに対してマイグレーション用csvファイルのアップロード処理を実施します。
   1. アップロード処理が完了すると、HTTPのレスポンス内に含まれる、migrationJobId（以下マイグレーションジョブID）を取得します。
1. migrationJobIdをもとに、getMigrationStatusでマイグレーションのステータスを取得します。
1. ステータス（migrationJobStatus）が"IN_PROGRESS"ならば、マイグレーション処理の実行中です。
   1. ステータスの確認を完了になるまで実施してください。
1. ステータスが"COMPLETED"ならば、アップロード処理が正常に終了しました。
   1. succeededCountで正常に処理された件数を確認できます。
   1. failedCountが1以上の場合は、downloadErrorFileUrlからエラーの詳細をダウンロードできます。

#### 認証方式とマイグレーション可能なキャンペーンの範囲

| 認証方式           | AccountIdの指定    | マイグレーション可能なキャンペーンの範囲    |
| --- | --- | ---                          |
| 通常認証           | 指定あり           | 指定AccountIdに紐づくキャンペーン           |
| 通常認証           | 指定なし           | 全AccountIdに紐づくキャンペーン             |
| 代行認証           | 指定あり           | 指定AccountIdに紐づくキャンペーン           |
| 代行認証           | 指定なし           | なし（代行認証の場合はAccountIdの指定必須） |

    

#### Operation

CampaignMigrationServiceで提供される操作を説明します。

+ [getCampaignDownloadUrl](#getcampaigndownloadurl)
+ [getMigrationStatus](#getmigrationstatus)
+ [getUploadUrl](#getuploadurl)

## getCampaignDownloadUrl

### リクエスト

マイグレーション対象のキャンペーン一覧をダウンロードするURLを取得します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| selector | Yes | [CampaignDownloadSelector](../data/CampaignMigration/CampaignDownloadSelector.md) |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/CampaignMigration" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getCampaignDownloadUrl xmlns="http://im.yahooapis.jp/V201911/CampaignMigration">
      <selector>
        <accountId>1234567890</accountId>
        <lang>EN</lang>
      </selector>
    </getCampaignDownloadUrl>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス

| パラメータ | データ型 |
| -------- | ------- |
| rval | [CampaignDownloadUrlValue](../data/CampaignMigration/CampaignDownloadUrlValue.md) |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/CampaignMigration" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>CampaignMigration</ns2:service>
      <ns2:requestTime>1574393669515</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getCampaignDownloadUrlResponse xmlns="http://im.yahooapis.jp/V201911/CampaignMigration" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <rval>
        <accountId>1234567890</accountId>
        <downloadScope>SINGLE_ACCOUNT</downloadScope>
        <lang>EN</lang>
        <downloadUrl>https://im.yahooapis.jp/campaignMigration/V201911/download/v3jykJFQLHx_eUBbBsAOXLmdPXL31xSVzYDfnMhFWLVmLkx1foXUtpJED6nnmIjxLXvOHsyY_-LUp0mlxk9cK9JU4bJ5mpL3YyoUt_A8i_XbJmt3LeBCcSubmakCo2EK2NYPXbWkaOuY07puedr5xFKMcrMNB12rK__FY7S7RSdv41Ymd7OzYFxGIWl1Cpc7PLCw9Epcl2mPPRW8GOUY3gq3U7Gn1Iu3DUWvL4o0FVcZ6sUAEK4yoZvbcucqjy0f</downloadUrl>
      </rval>
    </getCampaignDownloadUrlResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getMigrationStatus

### リクエスト

マイグレーション状況を取得します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| selector | Yes | [MigrationStatusSelector](../data/CampaignMigration/MigrationStatusSelector.md) |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/CampaignMigration" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getMigrationStatus xmlns="http://im.yahooapis.jp/V201911/CampaignMigration">
      <selector>
        <migrationJobIds>11111</migrationJobIds>
        <accountId>1234567890</accountId>
      </selector>
    </getMigrationStatus>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス

| パラメータ | データ型 |
| -------- | ------- |
| rval | [MigrationStatusPage](../data/CampaignMigration/MigrationStatusPage.md) |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/CampaignMigration" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>CampaignMigration</ns2:service>
      <ns2:requestTime>1574393669582</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getMigrationStatusResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/CampaignMigration">
      <ns2:rval>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:migrationJob>
            <ns2:migrationJobId>11111</ns2:migrationJobId>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:migrationScope>SINGLE_ACCOUNT</ns2:migrationScope>
            <ns2:migrationJobStatus>COMPLETED</ns2:migrationJobStatus>
            <ns2:migrationJobSubmitDate>20191106170328</ns2:migrationJobSubmitDate>
            <ns2:totalCount>10</ns2:totalCount>
            <ns2:inProgressCount>0</ns2:inProgressCount>
            <ns2:succeededCount>5</ns2:succeededCount>
            <ns2:failedCount>5</ns2:failedCount>
            <ns2:downloadOriginalFileUrl>https://im.yahooapis.jp//campaignMigration/V201911/downloadFile/v3jykJFQLHx_eUBbBsAOXLmdPXL31xSVzYDfnMhFWLUdNVMWSiLzOKWkYCMzQgWsQy-Bv__bQqDcztfcAh3FDtG8Xw2iHxqTISfOo8bYlV87f5ey5-HzLl5bSEUxTd2wuKRSkJgz_2yZZXimqRJ90z1TgKEwH2rtzLFTzqDZIHfpeR8vRoqz_KmfmNx-W8ChTM1JM6PdlYdYw7D0ra51pwIPBh3Q_vgWtR0C1BqL1yaIJeStfAC03q4mnucQrWwrxeQSLMhXg0znkiQ_WvMgMWg5Mhqsl38mvA9d-kdgk6SBUMnbVTPpSA19kyyc9oqKMdrkTng25yC_DVBOfD6624hI6GtVJRIGQ9AYLXDaihBy54c9shu4S4CyzTTs_ySjTgcZEYWeDQ7m2zSmxVznN-5h5OdwN_gGvF8_rmcLyyRL72jOepdtBjM8cTQL0TqdldbDAS9rI9TOCyFfsR9ByQ==</ns2:downloadOriginalFileUrl>
            <ns2:downloadErrorFileUrl>https://im.yahooapis.jp/campaignMigration/V201911/downloadErrorFile/v3jykJFQLHx_eUBbBsAOXLmdPXL31xSVzYDfnMhFWLUdNVMWSiLzOKWkYCMzQgWsTqfg2rYlwdst1K5hRJjlgkSqnTCDNgiP9drWvlBBQQWKqVZqERFsi1p-cdVkU2QtOrcEY97MG3d2uqsBQTv_T2LlTeyHCJFZwRSEAf_Jn4qRpsFCqg8yx8vzWePvlWlLrRW6NvVjUP5kcO6cT-QEdkAg-H3je4BZIakvBFkFlygSic_VSoEWl80FYbcycS5KWW9wMpW1zjSZh1y_uun1oolEl9P2XCSxyod9X8aEAtC6hB6rUnagn7C1mLFLkr0a-JoZ_jOn6ivQaq8yC-7fUJDg6olal68ia1k9u1Rwd5d7pOjnsHJjAy02KeNK79dzA1-zADkjLEeLeBUnkDyrzb6n_70bTTFjoYl6UZO028IfpvnXidOq0H1QFIOmt8-A</ns2:downloadErrorFileUrl>
          </ns2:migrationJob>
        </ns2:values>
      </ns2:rval>
    </ns2:getMigrationStatusResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getUploadUrl

### リクエスト

マイグレーション用のcsvファイルをアップロードするためのURLを取得します。<br>accountIdは、単一アカウントのキャンペーンのcsvアップロード時のみ指定可能です。<br>アカウントIDを指定することで、getMigrationStatusでアカウントIDでのジョブの絞り込みが可能になります。<br>※代行認証の場合はアカウントID指定必須です。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| selector | Yes | [CampaignUploadSelector](../data/CampaignMigration/CampaignUploadSelector.md) |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/CampaignMigration" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getUploadUrl xmlns="http://im.yahooapis.jp/V201911/CampaignMigration">
      <selector>
        <accountId>1234567890</accountId>
      </selector>
    </getUploadUrl>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス

| パラメータ | データ型 |
| -------- | ------- |
| rval | [UploadUrlValue](../data/CampaignMigration/UploadUrlValue.md) |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/CampaignMigration" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>CampaignMigration</ns2:service>
      <ns2:requestTime>1574393669561</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getUploadUrlResponse xmlns="http://im.yahooapis.jp/V201911/CampaignMigration" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <rval>
        <accountId>1234567890</accountId>
        <uploadUrl>https://im.yahooapis.jp/campaignMigration/V201911/upload/v3jykJFQLHx_eUBbBsAOXG1xrwwoDYyjft_ix3aQ2CgrcxlwlkOfisELabxEORbJkrQ-VAf24wvy_XygtLutx7hsvmqkMXDqJyduISxUAme2gK2KMf3LlTyAoFxbEYTsObGZLRdRB6S6P2dShqEfa57R6Ga0j7Ofl_VM61c3luY=</uploadUrl>
      </rval>
    </getUploadUrlResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

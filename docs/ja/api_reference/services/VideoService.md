# VideoService
VideoServiceでは、動画入稿に関する機能を提供します。

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/Vx.x/VideoService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/Vx.x/VideoService?wsdl|

#### Namespace
http://im.yahooapis.jp/V6

#### サービス概要
動画入稿に関する情報の取得、および動画のアップロード、ダウンロード、変更、削除を行います。

#### 操作
VideoServiceで提供される操作を説明します。
## get
### リクエスト
入稿済の動画の情報を取得します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [VideoSelector](../data/VideoSelector.md) | 動画の情報を取得します。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
 
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/ns1">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>1111-1111-1111-1111</ns1:license>
         <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
   </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:get>
         <ns1:selector>
            <ns1:accountId>1001314325</ns1:accountId>
            <ns1:mediaIds>434979</ns1:mediaIds>
            <ns1:mediaIds>436221</ns1:mediaIds>
            <ns1:userStatuses>PAUSED</ns1:userStatuses>
           <ns1:approvalStatuses>APPROVED</ns1:approvalStatuses>
           <ns1:processStatuses>PROCESSING</ns1:processStatuses>
            <ns1:paging>
               <ns1:startIndex>1</ns1:startIndex>
               <ns1:numberResults>20</ns1:numberResults>
            </ns1:paging>
         </ns1:selector>
      </ns1:get>
   </soapenv:Body>
</soapenv:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [VideoPage](../data/VideoPage.md) | 操作結果を表示します。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
 
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/ns1">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>VideoService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>2.7187</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:getResponse>
         <ns1:rval>
            <ns1:totalNumEntries>2</ns1:totalNumEntries>
            <ns1:Page.Type>VideoPage</ns1:Page.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:video>
                  <ns1:accountId>1001314325</ns1:accountId>
                  <ns1:mediaId>436221</ns1:mediaId>
                  <ns1:videoName>videoName01</ns1:videoName>
                  <ns1:videoTitle>videotitle01</ns1:videoTitle>
                  <ns1:userStatus>PAUSED</ns1:userStatus>
                  <ns1:creationTime>20170412130438</ns1:creationTime>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:disapprovalReasonCodes>0</ns1:disapprovalReasonCodes>
                  <ns1:processStatus>FINISHED</ns1:processStatus>
                  <ns1:videoSetting>
                     <ns1:videoFileType>MP4</ns1:videoFileType>
                     <ns1:videoAdFormat>YJ_640_360</ns1:videoAdFormat>
                     <ns1:fileSize>8602848</ns1:fileSize>
                     <ns1:width>640</ns1:width>
                     <ns1:height>360</ns1:height>
                     <ns1:playbackTime>15</ns1:playbackTime>
                     <ns1:downloadOriginalUrl>https://sample.api.yahooapis.jp/video/ns1.0/download/N8J7MNxGXbbRxUUUvD8BJZG5t95Iz25Jmv.1gMA3OSc_.Pt9YhuwyL7IXkOO2BMSrfrnVoXgO11rX8r1rWt6bkXGtkJtZr1KE82fr80MnlMVPZuyfL.UqnCXnOIroBVIB1XECNFUk_U64V.xgFQw0dZqBL2ppKQjCB1b9HnW06k5F5Gl4kpZjYr3E5h3eznwF4748MqP8VqFgoU.orrz.nnH4K5fFGO1yjAJLqXuiR8BzB7QGVvP5Mb35PKHxCHa7pLA4Z3cRcqvLlQ1nAgkzm.vpU0hY887anr0R4dYM7XZ0rvs4AB2mJDbXCoJ4oIQmyIdrxMcb2iecBc7lJF2GOpb7KQwdyqkqIzPdFyBntT.u60VFGE-</ns1:downloadOriginalUrl>
                     <ns1:downloadHighBitrateUrl>https://sample.api.yahooapis.jp/video/ns1.0/download/ymll661GXbZacvfxNgBcatut.X0KR8bdDkIeaQNp_ydLc7h6YPQ3hQMm4LCGeCURCGdoFihoKorrNLI.Z60_gdTQEX8rwDx35wAa_8JKMIRQaoLG68qoCAeFKYkbWVX.lVQkyYNRAFyAcT1eob0R8ohxFKt1qZ0U1qX_etx78CpYWceUrh.3ftv8Xhs_PNK7sgKyb_LTRGNYKowuuY_6SspdSNnzecpitLhIhZ5qnpMAEU_iUlpiA2NOdCvX3TmiB0LFXI2zyFrdt5.vK4CepYWdAfLaHlfRUDQsmsGK.1JDDa4k7nhSyr2uXfGlFqVRkSVYikWADsrJby_uABDVL6H7v96yDX9UzltFtSt9qYQSWi7O.vaLBA--</ns1:downloadHighBitrateUrl>
                     <ns1:downloadMiddleBitrateUrl>https://sample.api.yahooapis.jp/video/ns1.0/download/4p1ikXJGXbbpBx2qgyWgBVb4gNAW_nKlqtS.V2IBTPhLGfC_7JJkVEueghk0hOPsnOpjNpY5EDETEdWunPUAYMPniwHqWo_B4HvKj1GFO3cKTCKK0.clOgsOkVA5z9ImGcMz794pPz6LG6UDomMaOReAMQp9vHbdFThdDRO1GAkVqvs7b2PSMQHNHBatQ0LwwihL0T7PLbmTIP85.D.io9fQKjTMe7JdtHpiX_wpS_d5lU_zQXp_A74fC.z_h7Hc1k_0OixXRGfZbhHRpIHyj7KOeE8.sHmwnNY4YtuqMw35M.Up4VtU.LuBez0okI3F1w1yZQZ1uu1kGo4kx07OZ00lMmmt4YXeanBGskD6ffIYsPxSvb8RBu0u</ns1:downloadMiddleBitrateUrl>
                     <ns1:downloadLowBitrateUrl>https://sample.api.yahooapis.jp/video/ns1.0/download/WglC5OlGXbZOMgsPkixlruUyiVlUBZGotP9qARK.Www2Ie_cF.W8rkxGYLhTt.34lXpGKfOErxH_zR0udUFHoxXzrWKycXTB1_mMCjPDt4rJwBticbJODCzuped7HUvEE_VYoDymrxDENQTsYe_oqPYsIpwwzkKem9.fTwii3_nDik4eghRPl3qeAG5TQkFrBanCas.xXL.5Ro2fQrcH4frUhws6Wq5yNHLKIHNEKtfE5is5vJlARgGsN2mLaJQkSAI4AG6qpEKAhk2iARo4Tchjc7vlsAFoKEXvbAEl1MFIwoR0q2ac9M1FP2q_t3rwEa_Me5ogzkv4mhJnpvlEMbDyyOMHIs4enoqeMAIXv8xbEOWTRW9y_w--</ns1:downloadLowBitrateUrl>
                  </ns1:videoSetting>
               </ns1:video>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:video>
                  <ns1:accountId>1001314325</ns1:accountId>
                  <ns1:mediaId>433595</ns1:mediaId>
                  <ns1:videoName>videoName02</ns1:videoName>
                  <ns1:videoTitle>videotitle02</ns1:videoTitle>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:creationTime>20161114110440</ns1:creationTime>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:disapprovalReasonCodes>0</ns1:disapprovalReasonCodes>
                  <ns1:processStatus>FINISHED</ns1:processStatus>
                  <ns1:videoSetting>
                     <ns1:videoFileType>MP4</ns1:videoFileType>
                     <ns1:videoAdFormat>YJ_640_360</ns1:videoAdFormat>
                     <ns1:fileSize>1679282</ns1:fileSize>
                     <ns1:width>640</ns1:width>
                     <ns1:height>360</ns1:height>
                     <ns1:playbackTime>55</ns1:playbackTime>
                     <ns1:downloadOriginalUrl>https://sample.api.yahooapis.jp/video/V6.0/download/VQsB3pdtXLZ4r4Spyvawk8.tdYY06Lqqj5JNf1scLVY.pyOhZHux_p7uHf0R6TMcGmrW4p2p3ePrEWFSvT8B.WkSSXHIS4ZAIbAcXmN84U22y7GvYh4NkYEGbQP0B5llvPCnmWGrO6j07jrs4kCUA992wo80_nrugz2QZ0CXHOLa62RtcqatMG4e1lO01fEa8KxrjhgpVyHP675qRB1NOCK2b.MGr0vLkA7C1x4aqDjy_di5N9GCXVCgME3zRrl5QM1_eWcI76UgpclvI_AdDenECjiC8ikul581FjDKCH9D1HGqaAzCouupshUKCWtWWKc67xZxFNtVdzTsQJP2f_K2pp7sj7cG51.XKlPdmHd78CuVYkVr2w--</ns1:downloadOriginalUrl>
                     <ns1:downloadHighBitrateUrl>https://sample.api.yahooapis.jp/video/V6.0/download/dW5YlTRtXLZ.05R6mZ6pZdx6TOcI2IRhv3_zjJCyD46C2DjUIIpZwn2gCkf8V6YQBKyqvbZPd4Lf2dgNPtYKH7GcHSZkt6L0O5oqICDrpnbiN8irXTWguDp1Y3z2bFZv876agw2jjm69VI4L1_2wnRqI86sQtdo2nrCmU5EZZQ4pIE13R8Xw28sERLqru5W25fhlUh0PXOas98HmIO457_QJJ0xoFPlQh96ys9jvJT7A7PzvJiMZgBbXWDIR6w_X3f8pDRW7VK_3aO3Hce_VZgZVZQG_fcGAdjGlX_APJPpgX3pPSeIbhUisqX2uDLc7S_QQVqFNzS8jW7a2Fk2xABXP5f_3gKxBzX5rs86JyOhinC_SrMk-</ns1:downloadHighBitrateUrl>
                     <ns1:downloadMiddleBitrateUrl>https://sample.api.yahooapis.jp/video/V6.0/download/LY26lvVtXLZJAjxeqsBvGaJuGqaA.RCsCh36oBloPROMY29jAZ1rhZq0PYdvxspNmegS3Y6aDUXnTG.sWV2h5NutRjXjoqRKUNYv97X1vemWmZQ0pWOygIwZHh6K_spNl3euBAXpPjtLCQS2GwT9S99HR7ZY_9O9JLNuNenewbDjzavjOmx8vuv28GtDs5On9fFT7K2jC7oytWJDYYmT4P9cKX2m2k9a6iwIcbhqOr_YQ9rWsLBmOjAuJa6HoYyFI87yLOVTana1S1.K9zPa4vyc0r3JFhJli37uhHQxm.1L8iL9a42DypQ2DFCmZgxQDYQZtPlkbE5_rCIK0VqUWaSE7shSYXTe6lR3LvvVPScNLOVPmgjBBw--</ns1:downloadMiddleBitrateUrl>
                     <ns1:downloadLowBitrateUrl>https://sample.api.yahooapis.jp/video/V6.0/download/LY26lvVtXLZJAjxeqsBvGaJuGqaA.RCsCh36oBloPROMY29jAZ1rhZq0PYdvxspNmegS3Y6aDUXnTG.sWV2h5NutRjXjoqRKUNYv97X1vemWmZQ0pWOygIwZHh6K_spNl3euBAXpPjtLCQS2GwT9S99HR7ZY_9O9JLNuNenewbDjzavjOmx8vuv28GtDs5On9fFT7K2jC7oytWJDYYmT4P9cKX2m2k9a6iwIcbhqOr_YQ9rWsLBmOjAuJa6HoYyFI87yLOVTana1S1.K9zPa4vyc0r3JFhJli37uhHQxm.1L8iL9a42DypQ2DFCmZgxQDYQZtPlkbE5_rCIK0VqUWaSE7shSYXTe6lR3LvvVPScNLOVPmgjBBw--</ns1:downloadLowBitrateUrl>
                  </ns1:videoSetting>
               </ns1:video>
            </ns1:values>
         </ns1:rval>
      </ns1:getResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## GetUploadUrl
動画アップロード用URLを取得します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| accountId | ○ | long | アカウントIDです。 | 
| uploadVideo | ○ | [UploadVideo](../data/UploadVideo.md) | アップロードする動画の情報です。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/ns1">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>1111-1111-1111-1111</ns1:license>
         <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:getUploadUrl>
         <ns1:accountId>1111111111</ns1:accountId>
         <ns1:uploadVideo>
            <ns1:videoName>videoname01</ns1:videoName>
            <ns1:videoTitle>videotitle01</ns1:videoTitle>
            <ns1:userStatus>ACTIVE</ns1:userStatus>
         </ns1:uploadVideo>
      </ns1:getUploadUrl>
   </soapenv:Body>
</soapenv:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [UploadUrlPage](../data/UploadUrlPage.md) | getUploadUrlメソッドの操作結果（全Entityのリスト）を表示します。| 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V6">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>VideoService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0142</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:getUploadUrlResponse>
         <ns1:rval>
            <ns1:totalNumEntries>1</ns1:totalNumEntries>
            <ns1:Page.Type>VideoPage</ns1:Page.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:uploadUrlValue>
                  <ns1:accountId>1111111111</ns1:accountId>
                  <ns1:acceptableUploadStatus>true</ns1:acceptableUploadStatus>
                  <ns1:uploadUrl>https://sample.api.yahooapis.jp/videoUpload/V6.0/upload/uO6hmEkPQrZJ30Q9RF5bXuDkD7yitoPRTl6L_VvTFdnXsnBA_IFzJY3ptwCMoyF5j.UV5PvEbaxPmhmQaUrvUHx53HsIXelF.t3VyTfKo6Y6BghMug--</ns1:uploadUrl>
               </ns1:uploadUrlValue>
            </ns1:values>
         </ns1:rval>
      </ns1:getUploadUrlResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## Upload
### リクエスト
getUploadUrlで戻されたURLに対して、動画ファイルのアップロード処理を実施します。

### レスポンス

##### ＜レスポンスサンプル＞
```xml
// SUCCESS
// HTTP Status: 200
// Content-Type: application/json
{
    "ResultSet": {
        "Result": [{
            "uploadVideoData": {
                "accountId": 1000001,
                "mediaId": 1000000,
                "videoName": "VideoName",
                "videoTitle": "VideoTitle",
                "userStatus": "ACTIVE"
            }
        }]
    }
}
 
  
// ERROR
// HTTP Status: 400
// Content-Type: application/json
{
    "ResultSet": {
        "Error": [{
            "code": "10300",
            "message": "OVER_LIMIT"
        }]
    }
}
```

## mutate(SET)
### リクエスト
入稿済の動画の情報（動画名、配信状況）を変更します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [VideoOperation](../data/VideoOperation.md) | 動画の情報を操作（変更）します。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/ns1">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>1111-1111-1111-1111</ns1:license>
         <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>SET</ns1:operator>
            <ns1:accountId>1111111111</ns1:accountId>
            <ns1:operand>
               <ns1:accountId>1111111111</ns1:accountId>
               <ns1:mediaId>111111</ns1:mediaId>
               <ns1:videoTitle>videotitle01</ns1:videoTitle>
               <ns1:userStatus>PAUSED</ns1:userStatus>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>1111111111</ns1:accountId>
               <ns1:mediaId>222222</ns1:mediaId>
               <ns1:videoTitle>videotitle02</ns1:videoTitle>
               <ns1:userStatus>ACTIVE</ns1:userStatus>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [VideoReturnValue](../data/VideoReturnValue.md) | mutateメソッドの操作結果を表示します。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
 
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V6">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>VideoService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.9673</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>VideoReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>SET</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:video>
                  <ns1:accountId>1111111111</ns1:accountId>
                  <ns1:mediaId>111111</ns1:mediaId>
                  <ns1:videoName>videoname01</ns1:videoName>
                  <ns1:videoTitle>videotitle01</ns1:videoTitle>
                  <ns1:userStatus>PAUSED</ns1:userStatus>
                  <ns1:creationTime>20170412130438</ns1:creationTime>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:disapprovalReasonCodes>0</ns1:disapprovalReasonCodes>
                  <ns1:processStatus>FINISHED</ns1:processStatus>
                  <ns1:videoSetting>
                     <ns1:videoFileType>MP4</ns1:videoFileType>
                     <ns1:videoAdFormat>YJ_640_360</ns1:videoAdFormat>
                     <ns1:fileSize>8602848</ns1:fileSize>
                     <ns1:width>640</ns1:width>
                     <ns1:height>360</ns1:height>
                     <ns1:playbackTime>15</ns1:playbackTime>
                  </ns1:videoSetting>
               </ns1:video>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:video>
                  <ns1:accountId>1111111111</ns1:accountId>
                  <ns1:mediaId>222222</ns1:mediaId>
                  <ns1:videoName>videoname02</ns1:videoName>
                  <ns1:videoTitle>videotitle02</ns1:videoTitle>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:creationTime>20170412130438</ns1:creationTime>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:disapprovalReasonCodes>0</ns1:disapprovalReasonCodes>
                  <ns1:processStatus>FINISHED</ns1:processStatus>
                  <ns1:videoSetting>
                     <ns1:videoFileType>MP4</ns1:videoFileType>
                     <ns1:videoAdFormat>YJ_640_360</ns1:videoAdFormat>
                     <ns1:fileSize>8602848</ns1:fileSize>
                     <ns1:width>640</ns1:width>
                     <ns1:height>360</ns1:height>
                     <ns1:playbackTime>15</ns1:playbackTime>
                  </ns1:videoSetting>
               </ns1:video>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
### リクエスト
入稿済みの動画を削除します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [VideoOperation](../data/VideoOperation.md) | 動画を操作（削除）します。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
              <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>111111111</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:VideoId>5555555</ns1:VideoId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:VideoId>7777777</ns1:VideoId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:VideoId>9999999</ns1:VideoId>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### ＜リクエストサンプル＞（代行認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/ns1">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>1111-1111-1111-1111</ns1:license>
         <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>SET</ns1:operator>
            <ns1:accountId>1111111111</ns1:accountId>
            <ns1:operand>
               <ns1:accountId>1111111111</ns1:accountId>
               <ns1:mediaId>111111</ns1:mediaId>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>1111111111</ns1:accountId>
               <ns1:mediaId>222222</ns1:mediaId>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [VideoReturnValue](../data/VideoReturnValue.md) | mutateメソッドの操作結果を表示します。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V6">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>VideoService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.9673</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>VideoReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>SET</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:video>
                  <ns1:accountId>1111111111</ns1:accountId>
                  <ns1:mediaId>111111</ns1:mediaId>
                  <ns1:videoName>videoname01</ns1:videoName>
                  <ns1:videoTitle>videotitle01</ns1:videoTitle>
                  <ns1:userStatus>PAUSED</ns1:userStatus>
                  <ns1:creationTime>20170412130438</ns1:creationTime>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:disapprovalReasonCodes>0</ns1:disapprovalReasonCodes>
                  <ns1:processStatus>FINISHED</ns1:processStatus>
                  <ns1:videoSetting>
                     <ns1:videoFileType>MP4</ns1:videoFileType>
                     <ns1:videoAdFormat>YJ_640_360</ns1:videoAdFormat>
                     <ns1:fileSize>8602848</ns1:fileSize>
                     <ns1:width>640</ns1:width>
                     <ns1:height>360</ns1:height>
                     <ns1:playbackTime>15</ns1:playbackTime>
                  </ns1:videoSetting>
               </ns1:video>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:video>
                  <ns1:accountId>1111111111</ns1:accountId>
                  <ns1:mediaId>222222</ns1:mediaId>
                  <ns1:videoName>videoname02</ns1:videoName>
                  <ns1:videoTitle>videotitle02</ns1:videoTitle>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:creationTime>20170412130438</ns1:creationTime>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:disapprovalReasonCodes>0</ns1:disapprovalReasonCodes>
                  <ns1:processStatus>FINISHED</ns1:processStatus>
                  <ns1:videoSetting>
                     <ns1:videoFileType>MP4</ns1:videoFileType>
                     <ns1:videoAdFormat>YJ_640_360</ns1:videoAdFormat>
                     <ns1:fileSize>8602848</ns1:fileSize>
                     <ns1:width>640</ns1:width>
                     <ns1:height>360</ns1:height>
                     <ns1:playbackTime>15</ns1:playbackTime>
                  </ns1:videoSetting>
               </ns1:video>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

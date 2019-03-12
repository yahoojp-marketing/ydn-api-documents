# MediaService
MediaService retrieves, adds, updates, and deletes the media submission.
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201903/MediaService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201903/MediaService?wsdl |
#### Namespace
http://im.yahooapis.jp/V201903/Media
#### Service Overview
Use this service to retrieves, adds, updates, and deletes the media submission.<br>

[Notes]
- Image files are downloaded using URLs obtained with get or mutate method. <br>
URLs are valid for 15 minutes.

#### Operation
Describes operations provided by MediaService.

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)

#### オブジェクト
[Media](../data/Media)

## get

### Request
Retrieves the list of submitted media from specified condition.

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| selector | required | [MediaSelector](../data/Media/MediaSelector.md) | Retrieve media information. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/Media" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201903/Media" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <selector>
        <accountId>11111</accountId>
        <mediaIds>22222</mediaIds>
        <userStatuses>ACTIVE</userStatuses>
        <userStatuses>PAUSED</userStatuses>
        <approvalStatuses>APPROVED</approvalStatuses>
        <approvalStatuses>PRE_DISAPPROVED</approvalStatuses>
        <approvalStatuses>POST_DISAPPROVED</approvalStatuses>
        <approvalStatuses>REVIEW</approvalStatuses>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>10</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [MediaPage](../data/Media/MediaPage.md) | Container holding the operation result. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/Media" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>Media</ns2:service>
      <ns2:requestTime>1551686136934</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/Media">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>MediaPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:mediaRecord>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:mediaId>22222</ns2:mediaId>
            <ns2:mediaName>test.jpg</ns2:mediaName>
            <ns2:mediaTitle>test title</ns2:mediaTitle>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:logoFlg>FALSE</ns2:logoFlg>
            <ns2:thumbnailFlg>TRUE</ns2:thumbnailFlg>
            <ns2:creationTime>20170521182939</ns2:creationTime>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:disapprovalReasonCodes>0</ns2:disapprovalReasonCodes>
            <ns2:media xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ImageMedia">
              <ns2:mediaType>IMAGE</ns2:mediaType>
              <ns2:mediaFileType>JPEG</ns2:mediaFileType>
              <ns2:mediaAdFormat>YJ_640_360</ns2:mediaAdFormat>
              <ns2:fileSize>115851</ns2:fileSize>
              <ns2:width>640</ns2:width>
              <ns2:height>360</ns2:height>
              <ns2:downloadUrl>https://colo01.im.yahooapis.jp/media/V201903/download/W06g4Vlh1faqsvO8Sb4r_nWyjTKvYc0mD2gya6jJGxfbjJ1AmmqxJ.IUg7gQxBhnhvQ4cLX06QknWqZu3y9f7oXGiOa6vQHk3oZdMH0wVfNmxxavB_qrNhQNk3B2Qc96lRZ4DE1zccgf3lqMPFgjsZMFcb.38LSCARxIZu.vTZEGdt5ftDstcDfShmeepuBpNV1gysGLDlfn._rddlReV5LkAfUqF5niaW5b8KL_IytTCm8lwK9DpRjZi94FnYIWApN6URkWffsLG.TuRtWBQlMdVXNeTIcwFC7iZPR8PXgX9blkj_oDo22gUNeWoomlxrWjSFqenpXDe5W7dXtjRQXt5I6t1mATiNUt2VuMu3TNCM_ewMy_B1zBZ3am0RQ-</ns2:downloadUrl>
            </ns2:media>
          </ns2:mediaRecord>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)

### Request
Uploads the media.

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| operations | required | [MediaOperation](../data/Media/MediaOperation.md) | Add media. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/Media" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201903/Media">
      <operations>
        <operator>ADD</operator>
        <accountId>11111</accountId>
        <operand>
          <accountId>11111</accountId>
          <mediaName>sample2.png</mediaName>
          <mediaTitle>MEDIA_TITLE_1</mediaTitle>
          <userStatus>ACTIVE</userStatus>
          <logoFlg>FALSE</logoFlg>
          <thumbnailFlg>FALSE</thumbnailFlg>
          <media xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ImageMedia">
            <mediaType>IMAGE</mediaType>
            <data>AAAAAAAAAAAAAAAAAAAAAA==</data>
          </media>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [MediaReturnValue](../data/Media/MediaReturnValue.md) | Container holding the operation result. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/Media" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>Media</ns2:service>
      <ns2:requestTime>1551686136970</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/Media">
      <ns2:rval>
        <ListReturnValue.Type>MediaReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:mediaRecord>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:mediaId>22222</ns2:mediaId>
            <ns2:mediaName>test.jpg</ns2:mediaName>
            <ns2:mediaTitle>test title</ns2:mediaTitle>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:logoFlg>FALSE</ns2:logoFlg>
            <ns2:thumbnailFlg>TRUE</ns2:thumbnailFlg>
            <ns2:creationTime>20170521182939</ns2:creationTime>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:disapprovalReasonCodes>0</ns2:disapprovalReasonCodes>
            <ns2:media xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ImageMedia">
              <ns2:mediaType>IMAGE</ns2:mediaType>
              <ns2:mediaFileType>JPEG</ns2:mediaFileType>
              <ns2:mediaAdFormat>YJ_640_360</ns2:mediaAdFormat>
              <ns2:fileSize>115851</ns2:fileSize>
              <ns2:width>640</ns2:width>
              <ns2:height>360</ns2:height>
              <ns2:downloadUrl>https://colo01.im.yahooapis.jp/media/V201903/download/W06g4Vlh1faqsvO8Sb4r_nWyjTKvYc0mD2gya6jJGxfbjJ1AmmqxJ.IUg7gQxBhnhvQ4cLX06QknWqZu3y9f7oXGiOa6vQHk3oZdMH0wVfNmxxavB_qrNhQNk3B2Qc96lRZ4DE1zccgf3lqMPFgjsZMFcb.38LSCARxIZu.vTZEGdt5ftDstcDfShmeepuBpNV1gysGLDlfn._rddlReV5LkAfUqF5niaW5b8KL_IytTCm8lwK9DpRjZi94FnYIWApN6URkWffsLG.TuRtWBQlMdVXNeTIcwFC7iZPR8PXgX9blkj_oDo22gUNeWoomlxrWjSFqenpXDe5W7dXtjRQXt5I6t1mATiNUt2VuMu3TNCM_ewMy_B1zBZ3am0RQ-</ns2:downloadUrl>
            </ns2:media>
          </ns2:mediaRecord>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)

### Request
Change the status (delivery settings) of the submitted media.

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| operations | required | [MediaOperation](../data/Media/MediaOperation.md) | Change media. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/Media" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201903/Media">
      <operations>
        <operator>SET</operator>
        <accountId>11111</accountId>
        <operand>
          <accountId>11111</accountId>
          <mediaTitle>MEDIA_TITLE_1</mediaTitle>
          <userStatus>ACTIVE</userStatus>
          <logoFlg>FALSE</logoFlg>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [MediaReturnValue](../data/Media/MediaReturnValue.md) | Container holding the operation result. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/Media" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>Media</ns2:service>
      <ns2:requestTime>1551686137001</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/Media">
      <ns2:rval>
        <ListReturnValue.Type>MediaReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:mediaRecord>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:mediaId>22222</ns2:mediaId>
            <ns2:mediaName>test.jpg</ns2:mediaName>
            <ns2:mediaTitle>test title</ns2:mediaTitle>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:logoFlg>FALSE</ns2:logoFlg>
            <ns2:thumbnailFlg>TRUE</ns2:thumbnailFlg>
            <ns2:creationTime>20170521182939</ns2:creationTime>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:disapprovalReasonCodes>0</ns2:disapprovalReasonCodes>
            <ns2:media xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ImageMedia">
              <ns2:mediaType>IMAGE</ns2:mediaType>
              <ns2:mediaFileType>JPEG</ns2:mediaFileType>
              <ns2:mediaAdFormat>YJ_640_360</ns2:mediaAdFormat>
              <ns2:fileSize>115851</ns2:fileSize>
              <ns2:width>640</ns2:width>
              <ns2:height>360</ns2:height>
              <ns2:downloadUrl>https://colo01.im.yahooapis.jp/media/V201903/download/W06g4Vlh1faqsvO8Sb4r_nWyjTKvYc0mD2gya6jJGxfbjJ1AmmqxJ.IUg7gQxBhnhvQ4cLX06QknWqZu3y9f7oXGiOa6vQHk3oZdMH0wVfNmxxavB_qrNhQNk3B2Qc96lRZ4DE1zccgf3lqMPFgjsZMFcb.38LSCARxIZu.vTZEGdt5ftDstcDfShmeepuBpNV1gysGLDlfn._rddlReV5LkAfUqF5niaW5b8KL_IytTCm8lwK9DpRjZi94FnYIWApN6URkWffsLG.TuRtWBQlMdVXNeTIcwFC7iZPR8PXgX9blkj_oDo22gUNeWoomlxrWjSFqenpXDe5W7dXtjRQXt5I6t1mATiNUt2VuMu3TNCM_ewMy_B1zBZ3am0RQ-</ns2:downloadUrl>
            </ns2:media>
          </ns2:mediaRecord>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)

### Request
Delete the submitted media.

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| operations | required | [MediaOperation](../data/Media/MediaOperation.md) | Delete media. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/Media" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201903/Media">
      <operations>
        <operator>REMOVE</operator>
        <accountId>11111</accountId>
        <operand>
          <accountId>11111</accountId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [MediaReturnValue](../data/Media/MediaReturnValue.md) | Container holding the operation result. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/Media" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>Media</ns2:service>
      <ns2:requestTime>1551686137034</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/Media">
      <ns2:rval>
        <ListReturnValue.Type>MediaReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:mediaRecord>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:mediaId>22222</ns2:mediaId>
            <ns2:mediaName>test.jpg</ns2:mediaName>
            <ns2:mediaTitle>test title</ns2:mediaTitle>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:logoFlg>FALSE</ns2:logoFlg>
            <ns2:thumbnailFlg>TRUE</ns2:thumbnailFlg>
            <ns2:creationTime>20170521182939</ns2:creationTime>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:disapprovalReasonCodes>0</ns2:disapprovalReasonCodes>
            <ns2:media xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ImageMedia">
              <ns2:mediaType>IMAGE</ns2:mediaType>
              <ns2:mediaFileType>JPEG</ns2:mediaFileType>
              <ns2:mediaAdFormat>YJ_640_360</ns2:mediaAdFormat>
              <ns2:fileSize>115851</ns2:fileSize>
              <ns2:width>640</ns2:width>
              <ns2:height>360</ns2:height>
              <ns2:downloadUrl>https://colo01.im.yahooapis.jp/media/V201903/download/W06g4Vlh1faqsvO8Sb4r_nWyjTKvYc0mD2gya6jJGxfbjJ1AmmqxJ.IUg7gQxBhnhvQ4cLX06QknWqZu3y9f7oXGiOa6vQHk3oZdMH0wVfNmxxavB_qrNhQNk3B2Qc96lRZ4DE1zccgf3lqMPFgjsZMFcb.38LSCARxIZu.vTZEGdt5ftDstcDfShmeepuBpNV1gysGLDlfn._rddlReV5LkAfUqF5niaW5b8KL_IytTCm8lwK9DpRjZi94FnYIWApN6URkWffsLG.TuRtWBQlMdVXNeTIcwFC7iZPR8PXgX9blkj_oDo22gUNeWoomlxrWjSFqenpXDe5W7dXtjRQXt5I6t1mATiNUt2VuMu3TNCM_ewMy_B1zBZ3am0RQ-</ns2:downloadUrl>
            </ns2:media>
          </ns2:mediaRecord>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

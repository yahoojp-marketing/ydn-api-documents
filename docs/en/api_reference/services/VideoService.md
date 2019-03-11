# VideoService
Use this service for creating Video Ads.

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201812/VideoService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201812/VideoService?wsdl |

#### Namespace
http://im.yahooapis.jp/V201812/Video

#### Service Overview
Use this service to retrieve the Video Ads information, and to upload/download/update/delete video files.

[Notes]
- Download of video using URLs obtained with get method.<br>
URLs are valid for 15 minutes.
- Upload of video using URLs obtained with getUploadUrl.<br>
URLs are valid for 15 minutes.

#### Operation
Explains the operations provided by VideoService.

+ [get](#get)
+ [getUploadUrl](#getuploadurl)
+ [upload](#upload)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)

#### Object
[Video](../data/Video)

## get

### Request
Retrieves the added video information.

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| selector | required | [VideoSelector](../data/Video/VideoSelector.md) | Retrieves the added video information. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/Video" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201903/Video" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <selector>
        <accountId>1111</accountId>
        <mediaIds>2222</mediaIds>
        <mediaIds>3333</mediaIds>
        <userStatuses>ACTIVE</userStatuses>
        <userStatuses>PAUSED</userStatuses>
        <approvalStatuses>APPROVED</approvalStatuses>
        <approvalStatuses>REVIEW</approvalStatuses>
        <approvalStatuses>PRE_DISAPPROVED</approvalStatuses>
        <approvalStatuses>POST_DISAPPROVED</approvalStatuses>
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
| rval | [VideoPage](../data/Video/VideoPage.md) | Container including operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/Video" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>Video</ns2:service>
      <ns2:requestTime>1551686144268</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/Video">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>VideoPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:video>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:mediaId>2222</ns2:mediaId>
            <ns2:videoName>tes</ns2:videoName>
            <ns2:videoTitle>tes2</ns2:videoTitle>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:creationTime>20171024175716</ns2:creationTime>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:processStatus>FINISHED</ns2:processStatus>
            <ns2:videoSetting>
              <ns2:videoFileType>MP4</ns2:videoFileType>
              <ns2:videoAdFormat>YJ_640_360</ns2:videoAdFormat>
              <ns2:fileSize>29672732</ns2:fileSize>
              <ns2:width>640</ns2:width>
              <ns2:height>360</ns2:height>
              <ns2:playbackTime>60</ns2:playbackTime>
              <ns2:downloadOriginalUrl>https://colo01.im.yahooapis.jp/video/V201903/download/viZdXh.JqONCS1dU.dwWmnpIy_ITbPW2ahEb6ze_pZ4FID.XPbYHQc4zOEioYE7jhuJbrwX5QIcVv9H0cqQVszlNOzOY9aTuS1XYe7GUZhSasUj0tl2s1TWgbgxWmB004XRVt9FizVW_HXQgyYwgRjYJPQPqw4lcvbF1Vcf_UE8uLwhWwfbGjkkwwNIzbsDdLIceGTFbx7IiowQ9a73hWWArnvCbFWmBD.FN7HYd2FTGLoXKzcYZSDbMRMIs7HPkn4UvKqi_xLqKg_.33Ri0BmwfqhCnB7W2poxqddU8l15tMltkShxGURZ7zcdB.fwL1Q1KBmiltHhl6.0094X_HM.VLZjKAIhs4qiKLt9NMkpvL0bCygZHETuWkoIQZsg-</ns2:downloadOriginalUrl>
              <ns2:downloadHighBitrateUrl>https://colo01.im.yahooapis.jp/video/V201903/download/rwEr8wyJqOOhXYR9yKYWF3oViR5FAeebem9bEE72WgNqkhrVY4Bwfv6_1Yb6FrxOJcb9yXskjrcRwCEqHzqxOG_.8J4quw37bE0rleZHzh84Q1bAGwKUck3p70sWjOPopu1rcOJurCoo3.jhaHZVRQOGNFO7_HPJAeHEyN19IKjbBnIYFkZMatpHWTr20scfbJDt6AD0sE658RHSoNRSSj7XKxcawCw4seE9wsEQgGNwpNM2Y_ARzu3qURQOXya0J3LInGw0Cy_Jrg.ibPsf20ITAOhwX6tl8OyhcbSI1tHjUVIFxupeOImlJxtq8lDlYCPnleIHfGcNmrGXb7Our2rpT4POwzMXlc3YF4MrSI4XySxZpys3ZJe6Q6QEDFpz_Q--</ns2:downloadHighBitrateUrl>
              <ns2:downloadMiddleBitrateUrl>https://colo01.im.yahooapis.jp/video/V201903/download/vQRhca.JqOOhBifcqXbbRZlJOt1X9.v_2rNkYgSO71R03bXBDyBU5QoEm.O83ugEK9KTvFtFs6KU9bxBhqBwD8yzbNcP2euqi7wIkEfNY3OaQmYIVYFBi0dWq6aVUJwZPLepILE0vEJbNBpEuYCAq1r2Lk.wsG_QRgXZ3JTmuay58jYSjhc.v67VSBGvIHEZqYwdlr34Fuh7JwmBk0onAKVJL4bbghxXYlJH4x6C7Z9gBMlUkaVAEg9NEjoBwHOWbRLxC9SZ6acAc1Jv8z71OJ2dLu.NTIj2VPeGK35e4ogX8qI_HRFIjfZW_tT3Z3u..BpWQ6f0vc.NS1paxaoMU0BX8Dq.qIUFtRhuHEs9N0R3lQeswgbfQGz_qtr5</ns2:downloadMiddleBitrateUrl>
              <ns2:downloadLowBitrateUrl>video/V201903/download/vk88mJeJqON_XBRyO53kY9OWNrTQzPGAPZV2tklh5eqPV2nmecFPiOUoVl50VmnLSf8a2vCCp6TRX1iRRfFbfn8zQcYHwPu.clnL.ZFa1goVi9HnaNW9gi14xHfGUJV3WjRkhza8eBmL0_1.sN4P0odwRV2oRQCfGhuFL9jUK5oPNfNlmYV3F2gNEvDD.Lps8pDIuqIKSGVqH7.0kXrR.bU0Stvp_rkYBXTRLjDgi6YGgL96H0dlCF5aHEDnM.f6vKIq0qFxwRAWAWcz166YhTO8jYV9._QF_5z1e0nzMpeuQVZCXTf5UAU8eZDqhMXIvs7ztUfd1L5_6YJeTBm2Z34lF.m1WGrTlFmBHBFco5_2USOWKoz2cE4gGtVOA5c-</ns2:downloadLowBitrateUrl>
            </ns2:videoSetting>
          </ns2:video>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## GetUploadUrl
Retrieves the URL for uploading video files.

### Request
| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| accountId | required | long | Account ID |
| uploadVideo | required | [UploadVideo](../data/Video/UploadVideo.md) | Information of video to be uploaded.|

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/Video" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getUploadUrl xmlns="http://im.yahooapis.jp/V201903/Video">
      <accountId>1111</accountId>
      <uploadVideo>
        <videoName>TestUploadName</videoName>
        <videoTitle>TestVideoTitle</videoTitle>
        <userStatus>ACTIVE</userStatus>
      </uploadVideo>
    </getUploadUrl>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [UploadUrlPage](../data/Video/UploadUrlPage.md) | Container including operation results (list of all entities) of getUploadUrl method.|

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/Video" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>Video</ns2:service>
      <ns2:requestTime>1551686144285</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getUploadUrlResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/Video">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>VideoPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:uploadUrlValue>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:acceptableUploadStatus>true</ns2:acceptableUploadStatus>
            <ns2:uploadUrl>https://colo01.im.yahooapis.jp/video/V201903/upload/Jzaaaebm9xhmuP5vZGnXkIHZ3FS8whNxwxiLMUjiqL4NLEc9gPf1uM58Ges40r0.chBFiNyw.z2I5Huw2TajPnlwRMIOo23Kv.oZGk1PTECEVSB_NNdoVhDDdImQKpsdbuG9rATPU5pPHyllotOhtkg8eEqlw--</ns2:uploadUrl>
          </ns2:uploadUrlValue>
        </ns2:values>
      </ns2:rval>
    </ns2:getUploadUrlResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## Upload

### Request
Upload process of video files can be operated through the URL from getUploadUrl.


### Response


## mutate(SET)

### Request
Updates information (Video Name and Display Status) of added videos.

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| operations | required | [VideoOperation](../data/Video/VideoOperation.md) | Operate (update) the video information. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/Video" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201903/Video">
      <operations>
        <operator>SET</operator>
        <accountId>11111</accountId>
        <operand>
          <accountId>1111</accountId>
          <mediaId>2222</mediaId>
          <videoTitle>Change Title</videoTitle>
          <userStatus>ACTIVE</userStatus>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [VideoReturnValue](../data/Video/VideoReturnValue.md) | Container stores the operation result of mutate method. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/Video" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>Video</ns2:service>
      <ns2:requestTime>1551686144298</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/Video">
      <ns2:rval>
        <ListReturnValue.Type>VideoReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:video>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:mediaId>2222</ns2:mediaId>
            <ns2:videoName>tes</ns2:videoName>
            <ns2:videoTitle>tes2</ns2:videoTitle>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:creationTime>20171024175716</ns2:creationTime>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:processStatus>FINISHED</ns2:processStatus>
            <ns2:videoSetting>
              <ns2:videoFileType>MP4</ns2:videoFileType>
              <ns2:videoAdFormat>YJ_640_360</ns2:videoAdFormat>
              <ns2:fileSize>29672732</ns2:fileSize>
              <ns2:width>640</ns2:width>
              <ns2:height>360</ns2:height>
              <ns2:playbackTime>60</ns2:playbackTime>
              <ns2:downloadOriginalUrl>https://colo01.im.yahooapis.jp/video/V201903/download/viZdXh.JqONCS1dU.dwWmnpIy_ITbPW2ahEb6ze_pZ4FID.XPbYHQc4zOEioYE7jhuJbrwX5QIcVv9H0cqQVszlNOzOY9aTuS1XYe7GUZhSasUj0tl2s1TWgbgxWmB004XRVt9FizVW_HXQgyYwgRjYJPQPqw4lcvbF1Vcf_UE8uLwhWwfbGjkkwwNIzbsDdLIceGTFbx7IiowQ9a73hWWArnvCbFWmBD.FN7HYd2FTGLoXKzcYZSDbMRMIs7HPkn4UvKqi_xLqKg_.33Ri0BmwfqhCnB7W2poxqddU8l15tMltkShxGURZ7zcdB.fwL1Q1KBmiltHhl6.0094X_HM.VLZjKAIhs4qiKLt9NMkpvL0bCygZHETuWkoIQZsg-</ns2:downloadOriginalUrl>
              <ns2:downloadHighBitrateUrl>https://colo01.im.yahooapis.jp/video/V201903/download/rwEr8wyJqOOhXYR9yKYWF3oViR5FAeebem9bEE72WgNqkhrVY4Bwfv6_1Yb6FrxOJcb9yXskjrcRwCEqHzqxOG_.8J4quw37bE0rleZHzh84Q1bAGwKUck3p70sWjOPopu1rcOJurCoo3.jhaHZVRQOGNFO7_HPJAeHEyN19IKjbBnIYFkZMatpHWTr20scfbJDt6AD0sE658RHSoNRSSj7XKxcawCw4seE9wsEQgGNwpNM2Y_ARzu3qURQOXya0J3LInGw0Cy_Jrg.ibPsf20ITAOhwX6tl8OyhcbSI1tHjUVIFxupeOImlJxtq8lDlYCPnleIHfGcNmrGXb7Our2rpT4POwzMXlc3YF4MrSI4XySxZpys3ZJe6Q6QEDFpz_Q--</ns2:downloadHighBitrateUrl>
              <ns2:downloadMiddleBitrateUrl>https://colo01.im.yahooapis.jp/video/V201903/download/vQRhca.JqOOhBifcqXbbRZlJOt1X9.v_2rNkYgSO71R03bXBDyBU5QoEm.O83ugEK9KTvFtFs6KU9bxBhqBwD8yzbNcP2euqi7wIkEfNY3OaQmYIVYFBi0dWq6aVUJwZPLepILE0vEJbNBpEuYCAq1r2Lk.wsG_QRgXZ3JTmuay58jYSjhc.v67VSBGvIHEZqYwdlr34Fuh7JwmBk0onAKVJL4bbghxXYlJH4x6C7Z9gBMlUkaVAEg9NEjoBwHOWbRLxC9SZ6acAc1Jv8z71OJ2dLu.NTIj2VPeGK35e4ogX8qI_HRFIjfZW_tT3Z3u..BpWQ6f0vc.NS1paxaoMU0BX8Dq.qIUFtRhuHEs9N0R3lQeswgbfQGz_qtr5</ns2:downloadMiddleBitrateUrl>
              <ns2:downloadLowBitrateUrl>video/V201903/download/vk88mJeJqON_XBRyO53kY9OWNrTQzPGAPZV2tklh5eqPV2nmecFPiOUoVl50VmnLSf8a2vCCp6TRX1iRRfFbfn8zQcYHwPu.clnL.ZFa1goVi9HnaNW9gi14xHfGUJV3WjRkhza8eBmL0_1.sN4P0odwRV2oRQCfGhuFL9jUK5oPNfNlmYV3F2gNEvDD.Lps8pDIuqIKSGVqH7.0kXrR.bU0Stvp_rkYBXTRLjDgi6YGgL96H0dlCF5aHEDnM.f6vKIq0qFxwRAWAWcz166YhTO8jYV9._QF_5z1e0nzMpeuQVZCXTf5UAU8eZDqhMXIvs7ztUfd1L5_6YJeTBm2Z34lF.m1WGrTlFmBHBFco5_2USOWKoz2cE4gGtVOA5c-</ns2:downloadLowBitrateUrl>
            </ns2:videoSetting>
          </ns2:video>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)

### Request
Removes the added videos.

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| operations | required | [VideoOperation](../data/Video/VideoOperation.md) | Removes video files. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/Video" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201903/Video">
      <operations>
        <operator>REMOVE</operator>
        <accountId>11111</accountId>
        <operand>
          <accountId>1111</accountId>
          <mediaId>2222</mediaId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [VideoReturnValue](../data/Video/VideoReturnValue.md) | Container stores the operation result of mutate method. |

##### Response

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/Video" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>Video</ns2:service>
      <ns2:requestTime>1551686144317</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/Video">
      <ns2:rval>
        <ListReturnValue.Type>VideoReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:video>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:mediaId>2222</ns2:mediaId>
            <ns2:videoName>tes</ns2:videoName>
            <ns2:videoTitle>tes2</ns2:videoTitle>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:creationTime>20171024175716</ns2:creationTime>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:processStatus>FINISHED</ns2:processStatus>
            <ns2:videoSetting>
              <ns2:videoFileType>MP4</ns2:videoFileType>
              <ns2:videoAdFormat>YJ_640_360</ns2:videoAdFormat>
              <ns2:fileSize>29672732</ns2:fileSize>
              <ns2:width>640</ns2:width>
              <ns2:height>360</ns2:height>
              <ns2:playbackTime>60</ns2:playbackTime>
              <ns2:downloadOriginalUrl>https://colo01.im.yahooapis.jp/video/V201903/download/viZdXh.JqONCS1dU.dwWmnpIy_ITbPW2ahEb6ze_pZ4FID.XPbYHQc4zOEioYE7jhuJbrwX5QIcVv9H0cqQVszlNOzOY9aTuS1XYe7GUZhSasUj0tl2s1TWgbgxWmB004XRVt9FizVW_HXQgyYwgRjYJPQPqw4lcvbF1Vcf_UE8uLwhWwfbGjkkwwNIzbsDdLIceGTFbx7IiowQ9a73hWWArnvCbFWmBD.FN7HYd2FTGLoXKzcYZSDbMRMIs7HPkn4UvKqi_xLqKg_.33Ri0BmwfqhCnB7W2poxqddU8l15tMltkShxGURZ7zcdB.fwL1Q1KBmiltHhl6.0094X_HM.VLZjKAIhs4qiKLt9NMkpvL0bCygZHETuWkoIQZsg-</ns2:downloadOriginalUrl>
              <ns2:downloadHighBitrateUrl>https://colo01.im.yahooapis.jp/video/V201903/download/rwEr8wyJqOOhXYR9yKYWF3oViR5FAeebem9bEE72WgNqkhrVY4Bwfv6_1Yb6FrxOJcb9yXskjrcRwCEqHzqxOG_.8J4quw37bE0rleZHzh84Q1bAGwKUck3p70sWjOPopu1rcOJurCoo3.jhaHZVRQOGNFO7_HPJAeHEyN19IKjbBnIYFkZMatpHWTr20scfbJDt6AD0sE658RHSoNRSSj7XKxcawCw4seE9wsEQgGNwpNM2Y_ARzu3qURQOXya0J3LInGw0Cy_Jrg.ibPsf20ITAOhwX6tl8OyhcbSI1tHjUVIFxupeOImlJxtq8lDlYCPnleIHfGcNmrGXb7Our2rpT4POwzMXlc3YF4MrSI4XySxZpys3ZJe6Q6QEDFpz_Q--</ns2:downloadHighBitrateUrl>
              <ns2:downloadMiddleBitrateUrl>https://colo01.im.yahooapis.jp/video/V201903/download/vQRhca.JqOOhBifcqXbbRZlJOt1X9.v_2rNkYgSO71R03bXBDyBU5QoEm.O83ugEK9KTvFtFs6KU9bxBhqBwD8yzbNcP2euqi7wIkEfNY3OaQmYIVYFBi0dWq6aVUJwZPLepILE0vEJbNBpEuYCAq1r2Lk.wsG_QRgXZ3JTmuay58jYSjhc.v67VSBGvIHEZqYwdlr34Fuh7JwmBk0onAKVJL4bbghxXYlJH4x6C7Z9gBMlUkaVAEg9NEjoBwHOWbRLxC9SZ6acAc1Jv8z71OJ2dLu.NTIj2VPeGK35e4ogX8qI_HRFIjfZW_tT3Z3u..BpWQ6f0vc.NS1paxaoMU0BX8Dq.qIUFtRhuHEs9N0R3lQeswgbfQGz_qtr5</ns2:downloadMiddleBitrateUrl>
              <ns2:downloadLowBitrateUrl>video/V201903/download/vk88mJeJqON_XBRyO53kY9OWNrTQzPGAPZV2tklh5eqPV2nmecFPiOUoVl50VmnLSf8a2vCCp6TRX1iRRfFbfn8zQcYHwPu.clnL.ZFa1goVi9HnaNW9gi14xHfGUJV3WjRkhza8eBmL0_1.sN4P0odwRV2oRQCfGhuFL9jUK5oPNfNlmYV3F2gNEvDD.Lps8pDIuqIKSGVqH7.0kXrR.bU0Stvp_rkYBXTRLjDgi6YGgL96H0dlCF5aHEDnM.f6vKIq0qFxwRAWAWcz166YhTO8jYV9._QF_5z1e0nzMpeuQVZCXTf5UAU8eZDqhMXIvs7ztUfd1L5_6YJeTBm2Z34lF.m1WGrTlFmBHBFco5_2USOWKoz2cE4gGtVOA5c-</ns2:downloadLowBitrateUrl>
            </ns2:videoSetting>
          </ns2:video>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

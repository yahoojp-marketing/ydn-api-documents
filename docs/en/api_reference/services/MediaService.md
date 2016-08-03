# MediaService
MediaService retrieves, adds, updates, and deletes the media submission.
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/Vx.x/MediaService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/Vx.x/MediaService?wsdl|
#### Namespace
http://im.yahooapis.jp/V5
#### Service Overview
Use this service to retrieves, adds, updates, and deletes the media submission.<br>

#### Operation
Describes operations provided by MasterDataService.
## get
### Request
Retrieves the list of submitted media from specified condition.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| selector | ○ | [MediaSelector](../data/MediaSelector.md) | Retrieve media information. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>111111111</ns1:accountId>
                <ns1:mediaIds>5555555</ns1:mediaIds>
                <ns1:mediaIds>7777777</ns1:mediaIds>
                <ns1:userStatuses>PAUSED</ns1:userStatuses>
                <ns1:approvalStatuses>REVIEW</ns1:approvalStatuses>
                <ns1:paging>
                  <ns1:startIndex>1</ns1:startIndex>
                  <ns1:numberResults>20</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>111111111</ns1:accountId>
                <ns1:mediaIds>5555555</ns1:mediaIds>
                <ns1:mediaIds>7777777</ns1:mediaIds>
                <ns1:userStatuses>PAUSED</ns1:userStatuses>
                <ns1:approvalStatuses>REVIEW</ns1:approvalStatuses>
                <ns1:paging>
                  <ns1:startIndex>1</ns1:startIndex>
                  <ns1:numberResults>20</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [MediaPage](../data/MediaPage.md) | Container holding the operation result. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"> 
    <SOAP-ENV:Header> 
        <ns1:ResponseHeader> 
            <ns1:service>MediaService</ns1:service> 
            <ns1:remainingQuota>100</ns1:remainingQuota> 
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest> 
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis> 
        </ns1:ResponseHeader> 
    </SOAP-ENV:Header> 
    <SOAP-ENV:Body> 
        <ns1:getResponse> 
            <ns1:rval> 
                <ns1:Page.Type>MediaPage</ns1:Page.Type> 
                <ns1:totalNumEntries>2</ns1:totalNumEntries> 
                <ns1:values> 
                    <ns1:operationSucceeded>true</ns1:operationSucceeded> 
                    <ns1:mediaRecord> 
                        <ns1:accountId>1111111111</ns1:accountId> 
                        <ns1:mediaId>5555555</ns1:mediaId> 
                        <ns1:mediaName>ad_sample001.jpeg</ns1:mediaName> 
                        <ns1:mediaTitle>画像広告００１</ns1:mediaTitle> 
                        <ns1:userStatus>PAUSED</ns1:userStatus> 
                        <ns1:creationTime>2147483647</ns1:creationTime> 
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus> 
                        <ns1:disapprovalReasonCodes></ns1:disapprovalReasonCodes> 
                        <ns1:media xsi:type="ns1:ImageMedia"> 
                            <ns1:mediaType>IMAGE</ns1:mediaType> 
                            <ns1:mediaFileType>JPEG</ns1:mediaFileType> 
                            <ns1:mediaAdFormat>IAB_UAP_LEADER_BOARD</ns1:mediaAdFormat> 
                            <ns1:fileSize>12345</ns1:fileSize> 
                            <ns1:width>728</ns1:width> 
                            <ns1:height>90</ns1:height> 
                            <ns1:downloadUrl>https://sample.api.yahooapis.jp/media/V5/download/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX</ns1:downloadUrl> 
                        </ns1:media> 
                    </ns1:mediaRecord> 
                </ns1:values> 
                <ns1:values> 
                    <ns1:operationSucceeded>true</ns1:operationSucceeded> 
                    <ns1:mediaRecord> 
                        <ns1:accountId>1111111111</ns1:accountId> 
                        <ns1:mediaId>7777777</ns1:mediaId> 
                        <ns1:mediaName>ad_sample002.jpeg</ns1:mediaName> 
                        <ns1:mediaTitle>画像広告００２</ns1:mediaTitle> 
                        <ns1:userStatus>PAUSED</ns1:userStatus> 
                        <ns1:creationTime>2147483647</ns1:creationTime> 
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus> 
                        <ns1:disapprovalReasonCodes></ns1:disapprovalReasonCodes> 
                        <ns1:media xsi:type="ns1:ImageMedia"> 
                            <ns1:mediaType>IMAGE</ns1:mediaType> 
                            <ns1:mediaFileType>JPEG</ns1:mediaFileType> 
                            <ns1:mediaAdFormat>IAB_STANDARD_BANNER</ns1:mediaAdFormat> 
                            <ns1:fileSize>12345</ns1:fileSize> 
                            <ns1:width>320</ns1:width> 
                            <ns1:height>50</ns1:height> 
                            <ns1:downloadUrl>https://sample.api.yahooapis.jp/media/V5/download/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX</ns1:downloadUrl> 
                        </ns1:media> 
                    </ns1:mediaRecord> 
                </ns1:values> 
            </ns1:rval> 
        </ns1:getResponse> 
    </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```

## mutate(ADD)
### Request
Uploads the media.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| operations | ○ | [MediaOperation](../data/MediaOperation.md) | Add media. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
             <ns1:operator>ADD</ns1:operator>
               <ns1:accountId>111111111</ns1:accountId>
               <ns1:operand>
                 <ns1:accountId>1111111111</ns1:accountId>
                 <ns1:mediaName>ad_sample001.jpeg</ns1:mediaName>
                 <ns1:mediaTitle>画像００１</ns1:mediaTitle>
                 <ns1:userStatus>ACTIVE</ns1:userStatus>
                 <ns1:media xsi:type="ns1:ImageMedia">
                   <ns1:data>XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX (*Insert the image file in base64 encode.)
</ns1:data>
                 </ns1:media>
               </ns1:operand>
               <ns1:operand>
                 <ns1:accountId>1111111111</ns1:accountId>
                 <ns1:mediaName>ad_sample002.jpeg</ns1:mediaName>
                 <ns1:mediaTitle>画像００２</ns1:mediaTitle>
                 <ns1:userStatus>ACTIVE</ns1:userStatus>
                 <ns1:media xsi:type="ns1:ImageMedia">
                   <ns1:data>XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX (*Insert the image file in base64 encode.)
</ns1:data>
                 </ns1:media>
               </ns1:operand>
               <ns1:operand>
                 <ns1:accountId>1111111111</ns1:accountId>
                 <ns1:mediaName>ad_sample003.jpeg</ns1:mediaName>
                 <ns1:mediaTitle>画像００３</ns1:mediaTitle>
                 <ns1:userStatus>ACTIVE</ns1:userStatus>
                 <ns1:media xsi:type="ns1:ImageMedia">
                   <ns1:data>XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX (*Insert the image file in base64 encode.)
</ns1:data>
                 </ns1:media>
               </ns1:operand>
           </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) 
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"> 
    <SOAP-ENV:Header> 
        <ns1:RequestHeader> 
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license> 
            <ns1:apiAccountId>2xxxxxxxxxxxxxxx</ns1:apiAccountId> 
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword> 
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxxx</ns1:onBehalfOfAccountId> 
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword> 
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
           <ns1:operations>
             <ns1:operator>ADD</ns1:operator>
               <ns1:accountId>111111111</ns1:accountId>
               <ns1:operand>
                 <ns1:accountId>1111111111</ns1:accountId>
                 <ns1:mediaName>ad_sample001.jpeg</ns1:mediaName>
                 <ns1:mediaTitle>画像００１</ns1:mediaTitle>
                 <ns1:userStatus>ACTIVE</ns1:userStatus>
                 <ns1:media xsi:type="ns1:ImageMedia">
                   <ns1:data>XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX (*Insert the image file in base64 encode.)
</ns1:data>
                 </ns1:media>
               </ns1:operand>
               <ns1:operand>
                 <ns1:accountId>1111111111</ns1:accountId>
                 <ns1:mediaName>ad_sample002.jpeg</ns1:mediaName>
                 <ns1:mediaTitle>画像００２</ns1:mediaTitle>
                 <ns1:userStatus>ACTIVE</ns1:userStatus>
                 <ns1:media xsi:type="ns1:ImageMedia">
                   <ns1:data>XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX (*Insert the image file in base64 encode.)
</ns1:data>
                 </ns1:media>
               </ns1:operand>
               <ns1:operand>
                 <ns1:accountId>1111111111</ns1:accountId>
                 <ns1:mediaName>ad_sample003.jpeg</ns1:mediaName>
                 <ns1:mediaTitle>画像００３</ns1:mediaTitle>
                 <ns1:userStatus>ACTIVE</ns1:userStatus>
                 <ns1:media xsi:type="ns1:ImageMedia">
                   <ns1:data>XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX (*Insert the image file in base64 encode.)
</ns1:data>
                 </ns1:media>
               </ns1:operand>
           </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [MediaReturnValue](../data/MediaReturnValue.md) | Container holding the operation result. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>MediaService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>MediaReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>ADD</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:mediaRecord>
                        <ns1:accountId>1111111111</ns1:accountId>
                        <ns1:mediaId>5555555</ns1:mediaId>
                        <ns1:mediaName>ad_sample001.jpeg</ns1:mediaName>
                        <ns1:mediaTitle>画像広告００１</ns1:mediaTitle>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:creationTime>2147483647</ns1:creationTime>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:disapprovalReasonCodes></ns1:disapprovalReasonCodes>
                        <ns1:media xsi:type="ns1:ImageMedia">
                            <ns1:mediaType>IMAGE</ns1:mediaType>
                            <ns1:mediaFileType>JPEG</ns1:mediaFileType>
                            <ns1:mediaAdFormat>IAB_UAP_LEADER_BOARD</ns1:mediaAdFormat>
                            <ns1:fileSize>12345</ns1:fileSize>
                            <ns1:width>728</ns1:width>
                            <ns1:height>90</ns1:height>
                            <ns1:downloadUrl>https://sample.api.yahooapis.jp/media/V5/download/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX</ns1:downloadUrl>
                        </ns1:media>
                    </ns1:mediaRecord>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:mediaRecord>
                        <ns1:accountId>1111111111</ns1:accountId>
                        <ns1:mediaId>7777777</ns1:mediaId>
                        <ns1:mediaName>ad_sample002.jpeg</ns1:mediaName>
                        <ns1:mediaTitle>画像広告００２</ns1:mediaTitle>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:creationTime>2147483647</ns1:creationTime>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:disapprovalReasonCodes></ns1:disapprovalReasonCodes>
                        <ns1:media xsi:type="ns1:ImageMedia">
                            <ns1:mediaType>IMAGE</ns1:mediaType>
                            <ns1:mediaFileType>JPEG</ns1:mediaFileType>
                            <ns1:mediaAdFormat>IAB_STANDARD_BANNER</ns1:mediaAdFormat>
                            <ns1:fileSize>12345</ns1:fileSize>
                            <ns1:width>320</ns1:width>
                            <ns1:height>50</ns1:height>
                            <ns1:downloadUrl>https://sample.api.yahooapis.jp/media/V5/download/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX</ns1:downloadUrl>
                        </ns1:media>
                    </ns1:mediaRecord>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>false</ns1:operationSucceeded>
                    <ns1:error>
                        <ns1:code>2012</ns1:code>
                        <ns1:message>This is Sample Error</ns1:message>
                        <ns1:detail/>
                    </ns1:error>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
### Request
Change the status (delivery settings) of the submitted media.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| operations | ○ | [MediaOperation](../data/MediaOperation.md) | Change media. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
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
              <ns1:operator>SET</ns1:operator>
                <ns1:accountId>111111111</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:mediaId>5555555</ns1:mediaId>
                    <ns1:mediaTitle>画像広告００１</ns1:mediaTitle>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:mediaId>7777777</ns1:mediaId>
                    <ns1:mediaTitle>画像広告００２</ns1:mediaTitle>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:mediaId>9999999</ns1:mediaId>
                    <ns1:mediaTitle>画像広告００３</ns1:mediaTitle>
                    <ns1:userStatus>PAUSED</ns1:userStatus>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
              <ns1:operator>SET</ns1:operator>
                <ns1:accountId>111111111</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:mediaId>5555555</ns1:mediaId>
                    <ns1:mediaTitle>画像広告００１</ns1:mediaTitle>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:mediaId>7777777</ns1:mediaId>
                    <ns1:mediaTitle>画像広告００２</ns1:mediaTitle>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:mediaId>9999999</ns1:mediaId>
                    <ns1:mediaTitle>画像広告００３</ns1:mediaTitle>
                    <ns1:userStatus>PAUSED</ns1:userStatus>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [MediaReturnValue](../data/MediaReturnValue.md) | Container holding the operation result. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>MediaService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>MediaReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:mediaRecord>
                        <ns1:accountId>1111111111</ns1:accountId>
                        <ns1:mediaId>5555555</ns1:mediaId>
                        <ns1:mediaName>ad_sample001.jpeg</ns1:mediaName>
                        <ns1:mediaTitle>画像広告００１</ns1:mediaTitle>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:creationTime>2147483647</ns1:creationTime>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:disapprovalReasonCodes></ns1:disapprovalReasonCodes>
                        <ns1:media xsi:type="ns1:ImageMedia">
                            <ns1:mediaType>IMAGE</ns1:mediaType>
                            <ns1:mediaFileType>JPEG</ns1:mediaFileType>
                            <ns1:mediaAdFormat>IAB_UAP_LEADER_BOARD</ns1:mediaAdFormat>
                            <ns1:fileSize>12345</ns1:fileSize>
                            <ns1:width>728</ns1:width>
                            <ns1:height>90</ns1:height>
                        </ns1:media>
                    </ns1:mediaRecord>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:mediaRecord>
                        <ns1:accountId>1111111111</ns1:accountId>
                        <ns1:mediaId>7777777</ns1:mediaId>
                        <ns1:mediaName>ad_sample002.jpeg</ns1:mediaName>
                        <ns1:mediaTitle>画像広告００２</ns1:mediaTitle>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:creationTime>2147483647</ns1:creationTime>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:disapprovalReasonCodes></ns1:disapprovalReasonCodes>
                        <ns1:media xsi:type="ns1:ImageMedia">
                            <ns1:mediaType>IMAGE</ns1:mediaType>
                            <ns1:mediaFileType>JPEG</ns1:mediaFileType>
                            <ns1:mediaAdFormat>IAB_STANDARD_BANNER</ns1:mediaAdFormat>
                            <ns1:fileSize>12345</ns1:fileSize>
                            <ns1:width>320</ns1:width>
                            <ns1:height>50</ns1:height>
                        </ns1:media>
                    </ns1:mediaRecord>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>false</ns1:operationSucceeded>
                    <ns1:error>
                        <ns1:code>2012</ns1:code>
                        <ns1:message>This is Sample Error</ns1:message>
                        <ns1:detail/>
                    </ns1:error>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
### Request
Delete the submitted media.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| operations | ○ | [MediaOperation](../data/MediaOperation.md) | Delete media. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
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
                    <ns1:mediaId>5555555</ns1:mediaId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:mediaId>7777777</ns1:mediaId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:mediaId>9999999</ns1:mediaId>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
              <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>111111111</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:mediaId>5555555</ns1:mediaId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:mediaId>7777777</ns1:mediaId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:mediaId>9999999</ns1:mediaId>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [MediaReturnValue](../data/MediaReturnValue.md) | Container holding the operation result. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>MediaService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>MediaReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:mediaRecord>
                        <ns1:accountId>1111111111</ns1:accountId>
                        <ns1:mediaId>5555555</ns1:mediaId>
                        <ns1:mediaName>ad_sample001.jpeg</ns1:mediaName>
                        <ns1:mediaTitle>画像広告００１</ns1:mediaTitle>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:creationTime>2147483647</ns1:creationTime>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:disapprovalReasonCodes></ns1:disapprovalReasonCodes>
                        <ns1:media xsi:type="ns1:ImageMedia">
                            <ns1:mediaType>IMAGE</ns1:mediaType>
                            <ns1:mediaFileType>JPEG</ns1:mediaFileType>
                            <ns1:mediaAdFormat>IAB_UAP_LEADER_BOARD</ns1:mediaAdFormat>
                            <ns1:fileSize>12345</ns1:fileSize>
                            <ns1:width>728</ns1:width>
                            <ns1:height>90</ns1:height>
                        </ns1:media>
                    </ns1:mediaRecord>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:mediaRecord>
                        <ns1:accountId>1111111111</ns1:accountId>
                        <ns1:mediaId>7777777</ns1:mediaId>
                        <ns1:mediaName>ad_sample002.jpeg</ns1:mediaName>
                        <ns1:mediaTitle>画像広告００２</ns1:mediaTitle>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:creationTime>2147483647</ns1:creationTime>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:disapprovalReasonCodes></ns1:disapprovalReasonCodes>
                        <ns1:media xsi:type="ns1:ImageMedia">
                            <ns1:mediaType>IMAGE</ns1:mediaType>
                            <ns1:mediaFileType>JPEG</ns1:mediaFileType>
                            <ns1:mediaAdFormat>IAB_STANDARD_BANNER</ns1:mediaAdFormat>
                            <ns1:fileSize>12345</ns1:fileSize>
                            <ns1:width>320</ns1:width>
                            <ns1:height>50</ns1:height>
                        </ns1:media>
                    </ns1:mediaRecord>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>false</ns1:operationSucceeded>
                    <ns1:error>
                        <ns1:code>2012</ns1:code>
                        <ns1:message>This is Sample Error</ns1:message>
                        <ns1:detail/>
                    </ns1:error>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

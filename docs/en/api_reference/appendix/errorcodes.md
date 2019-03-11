# SOAP Error Codes
### Error Process Outline
When a SOAP request is successful, YDN API sends back the "HTTP 200 OK" response code, along with a SOAP response. <br>If an error occurs while a SOAP request is being processed, YDN API sends back a message with an error code. <br>
For details, please refer to [Error](/docs/en/api_reference/data/Common/Error.md) and/or [ErrorDetail](/docs/en/api_reference/data/Common/ErrorDetail.md).<br>

### Sample Error Response

There are 3 types of SOAP error response, SAPFault, Full error and Part error. See the following description about each response.

#### SOAPFault

SOAPFault response returns for WSDL violation, SOAP syntax violation, system error and authentication error.<br>
The returned SOAPFault is in the any of following forms depending on the service.

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Body>
    <SOAP-ENV:Fault>
      <faultcode>110006</faultcode>
      <faultstring>Can not login.</faultstring>
      <faultactor/>
      <detail>
        <requestKey>apiAccountId</requestKey>
        <requestValue>xxxx-xxxx-xxxx-xxxx</requestValue>
      </detail>
    </SOAP-ENV:Fault>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header/>
  <SOAP-ENV:Body>
    <SOAP-ENV:Fault>
      <faultcode>SOAP-ENV:Client</faultcode>
      <faultstring xml:lang="en">110006:Can not login.</faultstring>
      <detail>
        <ApiExceptionFault xmlns="http://im.yahooapis.jp/V201812/Account">{"details":[{"key":"license","value":["xxxx-xxxx-xxxx-xxxx"]},{"key":"apiAccountId","value":["xxxx-xxxx-xxxx-xxxx"]}]}</ApiExceptionFault>
      </detail>
    </SOAP-ENV:Fault>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Full Error

Full Error is returned for the fail of entire request caused by request constraints, etc. It is different from SOAPFault.<br>
Part Error is returned for the request fail caused by constraints in each ‘<operand>’ of SOAP request.

The following response is an example of Full Error in the case of invalid ‘numberResults’ value of `Paging` in [AccountService](/docs/ja/api_reference/services/AccountService.md).

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header xmlns:ns1="http://im.yahooapis.jp/V201812/Account" xmlns:ns2="http://im.yahooapis.jp/V201812">
    <ns1:ResponseHeader>
      <ns2:service>Account</ns2:service>
      <ns1:timeTakenSeconds>0.1234</ns1:timeTakenSeconds>
      <ns1:requestTime>1234567890</ns1:requestTime>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getResponse xmlns="http://im.yahooapis.jp/V201812/Account" xmlns:ns1="http://im.yahooapis.jp/V201812">
      <error>
        <ns1:code>F0001</ns1:code>
        <ns1:message>Invalid format.</ns1:message>
        <ns1:detail>
          <ns1:requestKey>selector/paging/numberResults</ns1:requestKey>
          <ns1:requestValue>1000000</ns1:requestValue>
        </ns1:detail>
      </error>
    </getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Part Error

Part Error is returned in the error case caused by constraints of each element in ‘<operand>’.<br>
Part Error is returned for each ‘<operand>’, whether an error occurred or not.<br>
The error response may contain both of ‘true’ and ‘false’ on ‘<values>’ of ‘<operationSucceeded>’ when you send a single SOAP request which includes multiple operation requests with multiple ‘<operand>’.

The following response is an example of Part Error in the case of specifying a ‘reportId’ which does not exist in [ReportService](/docs/ja/api_reference/services/ReportService.md).

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header xmlns:ns1="http://im.yahooapis.jp/V201812/Report" xmlns:ns2="http://im.yahooapis.jp/V201812">
    <ns1:ResponseHeader>
      <ns2:service>Report</ns2:service>
      <ns2:timeTakenSeconds>0.1234</ns2:timeTakenSeconds>
      <ns2:requestTime>1234567890</ns2:requestTime>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns3:mutateResponse xmlns:ns2="http://im.yahooapis.jp/V201812" xmlns:ns3="http://im.yahooapis.jp/V201812/Report">
      <ns3:rval>
        <ns2:ListReturnValue.Type>ReportReturnValue</ns2:ListReturnValue.Type>
        <ns2:Operation.Type>ADD</ns2:Operation.Type>
        <ns3:values>
          <ns2:operationSucceeded>false</ns2:operationSucceeded>
          <ns2:error>
            <ns2:code>I0001</ns2:code>
            <ns2:message>Deactivated Id.</ns2:message>
            <ns2:detail>
              <ns2:requestKey>reportId</ns2:requestKey>
              <ns2:requestValue>1234567890</ns2:requestValue>
            </ns2:detail>
          </ns2:error>
        </ns3:values>
      </ns3:rval>
    </ns3:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Error Code
The following list provides SOAP error codes and error content displayed when an error or problem occurs.  

#### General Errors
##### Service
Same for all services:

Code           | Message                     | Description                
-------------- | --------------------------- | ---------------------------
110001 | Invalid Request.  | Invalid Request.  
110002 | Frequency limit exceeded. Please try your request again later.  | Frequency limit exceeded. Please try your request again later.  
110003 | Invalid location.  | Invalid location.  
110005 | Not a valid id.  | Not a valid id.  
110006 | Can not login. | Cannot login.  
110007 | Invalid method.  | Invalid method.  
110008 | Invalid selector.  | Invalid selector.  
110009 | Invalid operations.  | Invalid operations.  
110010 | Invalid operator.  | Invalid operator.  
118888 | Out of service.  | Out of service.
119999 | An internal error has occurred.  | An internal error has occurred.  
120020 | Can not set value.  | Value cannot be set.  
120026 | Invalid account. | Invalid account.
F0001  | Invalid format.   | The value format is invalid.
F0002  |	Invalid file format. | The upload file format is invalid.
R0001 | Require. | It is missing required parameter.
V0001 | Invalid value. | The value is invalid.
V0002 | Empty file. | The upload file is 0 byte.
V0003 | Over limit of the file. | The upload file size exceeds the limit.
L0001 | Lower list size. | The number of elements in the array is below the lower limit.
L0002 | Over list size. | The number of elements in the array exceeds the upper limit.
U0001 | Url has expired. | The upload URL or download URL has expired.
U0002 | Invalid url. | The upload URL or download URL is invalid.
S0001 | Invalid Status. | The status is invalid.
I0001 | Deactivated Id. | The ID is Deactivated.
D0001 | Duplicate. | The unique value is duplicated.
RL001 | Invalid relation. | The relation of the request is contradictory.<br> For example, you are specifying the date of start > end.
LT001 | Over limit. | The upper limit value that can be registered is exceeded.

#### Submission-related Errors
##### Service
[RetargetingListService](/docs/en/api_reference/services/RetargetingListService.md),<br>
[AdGroupTargetService](/docs/en/api_reference/services/AdGroupTargetService.md),<br>
[BulkService](/docs/en/api_reference/services/BulkService.md),<br>
[CampaignService](/docs/en/api_reference/services/CampaignService.md),<br>
[AdGroupAdService](/docs/en/api_reference/services/AdGroupAdService.md),<br>
[AdGroupService](/docs/en/api_reference/services/AdGroupService.md),<br>
[MediaService](/docs/en/api_reference/services/MediaService.md),<br>
[VideoService](/docs/en/api_reference/services/VideoService.md)


Code           | Message                     | Description                
-------------- | --------------------------- | ---------------------------
210001 | Selected value is not approved to update.  | The selected elements is not approved to use for the updates of target list.
210002 | Cannot update from the dependency.  | Due to the dependency relations, updateis not possible.
210003 | A function is not permitted this account.| Custom audience is not available for this account. 
220007 | Unavailable the adProductType.  | adProductType specified is not available.
220009 | Ad type you chose does not support the specified adProductType.  | Ad type you chose does not support the specified adProductType.
220010 | Can not specify APP and OS for the device type.  | APP and OS you specified does not support for the device type.
220014 | Budget is lower than bidding price.  | The bidding price has been set higher than the budget.
220015 | Bidding price is higher than campaign budget.  | The bidding price has been set higher than the campaign budget.
220016 | Advance setting was made to the product or targeting that is not available.  | The advance setting is only available for the specified product.
220018 | This Target settings is unavailable.  | The type of campaign is not available for the target settings.
220019 | Another job is in progress.  | It is running another job.
220103 | Unsupported filename extension.  | The image file is not GIF/JPEG.
220104 | Only GIF89a is supported.  | GIF file is not in GIF89a.
220105 | Animated GIF pixel size does not fit.  | The following file could not be registered, because the file size did not fit the pixel size of the animated GIF format.
220106 | Only RGB is supported.  | Color space of image file is not in the RGB.
220107 | Invalid aspect ratio of an image.  | Image file of the ads is not in supportive size.
220113 | Unsupported ad product type.  | Delivery method of campaign (AdproductType) cannot relate to media.
220115 | Unavailable aspect ratio of an image. | The pixel size is not available to use for the specific image.
220117 | Inifinite loop setting is not allowed for Animated GIF.  | Inifinate loop has been set for animated GIF ads.
220118 | Animated GIF movie time is too long (Max 15 seconds).  | Animation has been set longer than 15 seconds.
220119 | Submitted file is transparent GIF.  | Image file is transparent GIF.
220121 | Frequency setting was made to the product that is not available.  | You can not set frequency ads instruments designated.
220122 | Unavailable combination of frequency settings.  | Combination of frequency setting is invalid.
220123 | Unavailable conversion optimizer.  | Conversion optimization setting is not possible due to the non-eligible Ad distribution.
220124 | Disable conversion optimizer.  | Target CPA cannot be set, due to the unusable conversion optimization.
220125 | Unavailable the dynamicImageExtensions.  | Cannot set Dynamic Image Extensions, due to the non-eligible Ad distribution.
220129 | Invalid combination in user status and logo flag. | Unavailable setting between the status flag and logo flag.
220130 | Invalid combination in logo flag and media format. | Unavailable setting between the logo flag and image format.
220131 | Field value is not updatable. | Update has been attempted to the field that cannot be updated.
220132 | Cannot set the carrier type. | Selected device is not available to select the carrier type.
220133 | Not allowed to set impression beacon url. | Impression beacon URL is not available since the external link to analyzing tool providers is not allowed.
220135 | Invalid relation in thumbnail flag and media format. | Unavailable setting between the thumbnail flag and image format.
220141 | Can not set bidMultiplier. | The bid adjustment rate is not available for the targeting.
220207 | Invalid aspect ratio of an video. | Wrong pixel size for video file.
220209 | Video play time is too long (Max 60 seconds). | Play time of the specified video is longer than 60 seconds.
220210 | Video play time is too short (Min 5 seconds). | Play time of the specified video is shorter than 5 seconds.
220211 | Invalid video codec. | Video codec of the specified video file is invalid.
220212 | Invalid audio codec. | Audio codec of the specified video file is invalid.
220213 | Invalid major brand. | Major brand of the video file is invalid.
220214 | Invalid video index. | 'moov atom' has to place on top of the video file.
220215 | Over limit of frame rate. | Frame rate of the video file exceeds the max value.
220216 | Over limit of audio volume. | Audio volume of the video file exceeds the max value.
220301 | Over limit to delivered ad. | Number of ads set to be distributed exceeded the limit. 
220302 | Over limit to ad under account. | Number of ads under an account exceeded the limit. 
220310 | Over limit to ad group under account. | Number of ad groups under an account exceeded the limit. 
220322 | Invalid tracking parameter. | Invalid string (such as invalid Tracking Parameter, etc.) was found.
220323 | Tracking parameter is not available for this type of ad distribution. | There is a Tracking Parameter which is not available for the ad product.
220324 | Entered tracking parameter cannot be used. | There is a Tracking Parameter which is not available for the YDN-unaligned tracking tool, or a discontinued Tracking Parameter.
220325 | Invalid relation of video and thumbnail format. | Invalid relation of video and thumbnail format.
220326 | Not allowed to set video beacon url. | Not allowed to set video beacon url.

### Report Process-related Errors
##### Service
[ReportService](/docs/ja/api_reference/services/ReportService.md),<br>
[ReportDefinitionService](/docs/ja/api_reference/services/ReportDefinitionService.md)

Code           | Message                     | Description                
-------------- | --------------------------- | ---------------------------
240001 | Over limit of uncompleted report download job.  | The registration limit of uncompleted report download jobs has been exceeded.
240003 | Invalid division specified.  | Invalid division specified.
240004 | Invalid segment match pattern.  | Invalid segment match pattern.
240005 | Invalid field item.  | Invalid field item.
240006 | Invalid sort item.  | Invalid sort item.
240010 | Over limit of report template number.  | The number of registeration template is over the limit number.
250001 | Invalid combination in Template settings. | Cannot select "custom date" for the period when template flag is set.
250002 | Invalid field settings. | Incorrect combination in report fields is set.
250003 | Invalid combination in report date settings. | Cannot specify a certain date for the timing (interval type) to create a report you specified.
250004 | Invalid combination in date range type. | Cannot select "custom date" for the period you specified.
250005 | Invalid filter`s field. | Specifing the field which cannot be set to the filter.

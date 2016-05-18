# Release Notes
## Release version　　
5.3 (WSDL version: 5.3.0)

## Type of Version up　　
Minor version up 

## Main Contents of this Release
#### 1. Addition of Aggregate Analytics data function
The feature of aggregating Analytics data by each unit of campaign, ad group, ad and media (images) will be available.
 <br>

* Target Web Service  
 * [StatsService](/docs/en/api_reference/services/StatsService.md)

* Target Data Object  
 * Please confirm from Data Objects page for more details.
  
* Target Enumerations  
 * Please confirm from Data Objects page for more details.
 
#### 2. Addition of Download Operation History data function  
Downloading the data of user operation history will be available.<br>

* Target Web Service  
 * [AuditLogService](/docs/en/api_reference/services/AuditLogService.md)
  
* Target Data Object  
 * Please confirm from Data Objects page for more details.
  
* Target Enumerations  
 * Please confirm from Data Objects page for more details.

#### 3. Addition of Rule type of Site Retargeting function
Added following rule types <br>
   - Page type
   - Item ID
   - Item category ID

* Target Web Service  
 * [RetargetingListService](/docs/en/api_reference/services/RetargetingListService.md)
  
* Target Data Object  
 * Please confirm from Data Objects page for more details.
  
* Target Enumerations  
 * [RuleType(enum)](/docs/en/api_reference/data/RuleType.md)

## Impacts on each Version from the change of Services 
<table class="standard">
  <tbody><tr>
    <th valign="top"><p>Service</p></th>
    <th valign="top"><p>Ver.5.2 and before</p></th>
    <th valign="top"><p>Ver.5.3</p></th>
  </tr>
  <tr>
    <td valign="top"><p>StatsService</p></td>
    <td valign="top"><p>- New Release</p></td>
    <td valign="top"><p>- 'medialds'(for Media ID) is supported on the Analytics data.</p></td>
  </tr>
  <tr>
    <td valign="top"><p>AuditLogService</p></td>
    <td valign="top"><p>- Not supported.<br></p></td>
    <td valign="top"><p>- New Service.</p></td>
  </tr>
  <tr>
    <td valign="top"><p>RetargetingListService</p></td>
    <td valign="top"><p>- No change.<br></p></td>
    <td valign="top"><p>- Added following items on RuleType Enum value.<br>
    -- PAGE_TYPE (page type)<br>
    -- ITEM_ID (Item ID)<br>
    -- ITEM_CATEGORY_ID (Item category ID)
    </p></td>
  </tr></tbody>
</table>

## Sunset Date of YDN API Ver.5.1
YDN API Ver.5.1 is plan to sunset in September 2016 (JST).

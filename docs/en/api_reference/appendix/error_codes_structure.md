# Reorganize error codes structure

## Overview
To improve error codes structure, following reorganization has been made.

### 1．Issues of current error codes
#### Issue1: Redundant error codes and messages
* Same error message, but error code differentiate in upper/lower cases.
*Same error message, but differentiate in services.
* Unused error message, after specification update.
#### Issue2: Hard to follow errors for API users
Too specialized to use error codes properly.
* example: For invalid format, three codes exist,  ‘INVALID STRING FORMAT’,  ‘INVALID NUMBER FORMAT’ and ‘INVALID DATE FORMAT’.
### 2. Revise error codes structure
Categorized common error items  in service and merged error codes.
<table class="standard">
<tbody>
<tr>
<th>Pattern</th>
<th>Category</th>
<th>Code</th>
<th>Message</th>
<th>Description</th>
</tr>
<tr>
 <td valign="top" rowspan=2>1</td>
 <td valign="top" rowspan=2>Invalid format</td>
 <td valign="top">F0001</td>
 <td valign="top">Invalid format.</td>
 <td valign="top">Invalid format of date, number, string.</td>
</tr>
<tr>
 <td valign="top">F0002</td>
 <td valign="top">Invalid file format.</td>
 <td valign="top">The format of uploading file is invalid.</td>
</tr>
<tr>
 <td valign="top">2</td>
 <td valign="top">Required</td>
 <td valign="top">R0001</td>
 <td valign="top">Require.</td>
 <td valign="top">Missing entry on required items.</td>
</tr>
<tr>
 <td valign="top" rowspan=3>3</td>
 <td valign="top" rowspan=3>Invalid value</td>
 <td valign="top">V0001</td>
 <td valign="top">Invalid value.</td>
 <td valign="top">The value with unacceptable character, date, number ENUM.</td>
</tr>
<tr>
 <td valign="top">V0002</td>
 <td valign="top">Empty file</td>
 <td valign="top">The size of uploading file is zero byte.</td>
</tr>
<tr>
 <td valign="top">V0003</td>
 <td valign="top">Over limit of the file</td>
 <td valign="top">The size of uploading file exceeds the maximum limit.</td>
</tr>
<tr>
 <td valign="top" rowspan=2>4</td>
 <td valign="top" rowspan=2>Invalid array</td>
 <td valign="top">L0001</td>
 <td valign="top">Lower list size.</td>
 <td valign="top">The number of elements of array is lower than the minumum value.</td>
</tr>
<tr>
 <td valign="top">L0002</td>
 <td valign="top">Over list size.</td>
 <td valign="top">The number of elements of array exceeds the mazimum value.</td>
</tr>
<tr>
 <td valign="top" rowspan=2>5</td>
 <td valign="top" rowspan=2>URL</td>
 <td valign="top">L0001</td>
 <td valign="top">Url has expired.</td>
 <td valign="top">The validity period of URL for upload/download is expired.</td>
</tr>
<tr>
 <td valign="top">U0002</td>
 <td valign="top">Invalid url.</td>
 <td valign="top">Unavailable URL for upload/download. <br> (altered URL, etc.)</td>
</tr>
<tr>
 <td valign="top">6</td>
 <td valign="top">Invalid status</td>
 <td valign="top">S0001</td>
 <td valign="top">Invalid Status.</td>
 <td valign="top">Invalid status. It cannot be edited or removed.</td>
</tr>
<tr>
 <td valign="top">7</td>
 <td valign="top">Deactivated ID</td>
 <td valign="top">I0001</td>
 <td valign="top">Deactivated Id.</td>
 <td valign="top">Specifying ID for an entity already removed or does not exist.</td>
</tr>
<tr>
 <td valign="top">8</td>
 <td valign="top">Duplicated</td>
 <td valign="top">D0001</td>
 <td valign="top">Duplicate.</td>
 <td valign="top">・Duplicating an item to uniquely identify entity.<br>
・Duplicating name, the name has been already registered.<br>
・Duplicating name, the name has been already used in the operand specified by request.</td>
</tr>
<tr>
 <td valign="top">9</td>
 <td valign="top">Invalid relation</td>
 <td valign="top">RL001</td>
 <td valign="top">Invalid relation.</td>
 <td valign="top">Relation of items specified on request is contradictory.<br> (For example, relation between start date and end date, etc.)</td>
</tr>
<tr>
 <td valign="top">10</td>
 <td valign="top">Over limit</td>
 <td valign="top">LT001</td>
 <td valign="top">Over limit.</td>
 <td valign="top">Exceeding the maximum number of available entities.</td>
</tr>
</table>

*	Error codes by service were merged based on the error message as follows.
<table class="standard">
<tbody>
<tr>
<th>Code</th>
<th>Message</th>
<th>Deleted</th>
<th>Merged to</th>
</tr>
<tr>
 <td valign="top">210003</td>
 <td valign="top">A function is not permitted this account.</td>
 <td valign="top"></td>
 <td valign="top"></td>
</tr>
<tr>
 <td valign="top">220108</td>
 <td valign="top">function is not permitted this account.</td>
 <td valign="top">v</td>
 <td valign="top">210003</td>
</tr>
<tr>
 <td valign="top">119999</td>
 <td valign="top">An internal error has occurred.</td>
 <td valign="top"></td>
 <td valign="top"></td>
</tr>
<tr>
 <td valign="top">220003</td>
 <td valign="top">Creating bulk downloadUrl is failed.</td>
 <td valign="top">v</td>
 <td valign="top">119999</td>
</tr>
<tr>
 <td valign="top">220110</td>
 <td valign="top">Creating media downloadUrl is failed.</td>
 <td valign="top">v</td>
 <td valign="top">119999</td>
</tr>
<tr>
 <td valign="top">220201</td>
 <td valign="top">Creating video downloadUrl is failed.</td>
 <td valign="top">v</td>
 <td valign="top">119999</td>
</tr>
<tr>
 <td valign="top">220204</td>
 <td valign="top">Creating video uploadUrl was failed.</td>
 <td valign="top">v</td>
 <td valign="top">119999</td>
</tr>
<tr>
 <td valign="top">240007</td>
 <td valign="top">Creating report downloadUrl is failed.</td>
 <td valign="top">v</td>
 <td valign="top">119999</td>
</tr>
</table>

### 3．Deleted error codes not in use
Following error codes currently unused have been deleted.
<table class="standard">
<tbody>
<tr>
<th>Code</th>
<th>Message</th>
</tr>
<tr>
 <td valign="top">110004</td>
 <td valign="top">Quota exceeded. service = %s , Quota = %s</td>
</tr>
<tr>
 <td valign="top">120021</td>
 <td valign="top">Insufficient search parameters.</td>
</tr>
<tr>
 <td valign="top">220001</td>
 <td valign="top">Over limit of uncompleted bulk download job.</td>
</tr>
<tr>
 <td valign="top">220002</td>
 <td valign="top">Over limit of bulk download job.</td>
</tr>
</table>

## List of merged error codes
The list of merged error codes can be downloaded with the following link.<br>
[Error code strucrure (YDN API)](https://s.yimg.jp/images/promotionalads_edit/support/pdf/api_doc/error_codes_structure_YDN_en.pdf)




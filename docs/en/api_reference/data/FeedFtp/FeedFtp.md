# FeedFtp
FeedFtp object retains Periodic Upload setting information.

### Service
+ [FeedFtpService](../../services/FeedFtpService.md)

### Namespace
[FeedFtpService#Namespace](../../services/FeedFtpService.md#namespace)

| Field | Type | Description | response | add | set 
|---|---|---|---|---|---|
| accountId| xsd:long| Account ID. | yes | Ignore |　Ignore 
| feedHolderId| xsd:long| FeedHolder ID. | yes | Requirement | Requirement 
| itemListUploadType| [ItemListUploadType](./ItemListUploadType.md)| Type of uploaded item list. |  yes | Requirement | Optional 
| schedule| Schedule <br> inherited [ScheduleHourly](./ScheduleHourly.md) <br> inherited [ScheduleDaily](./ScheduleDaily.md) <br> inherited [ScheduleWeekly](./ScheduleWeekly.md) | Schedule. | yes | Requirement | Optional 
| feedUrl| xsd:string| URL of item list file. | yes | Requirement | Optional 
| userName| xsd:string| User name. | yes | Requirement | Optional 
| userPassword| xsd:string| Password. | yes | Requirement | Optional 
| activeStatus| [ActiveStatus](./ActiveStatus.md)| Active status. <br> *Default: ACTIVE | yes | Optional | Optional 

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

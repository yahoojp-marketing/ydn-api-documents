# RuleTargetList
RuleTargetList object displays the list of rule settings.
### Service
+ [RetargetingListService](../services/RetargetingListService.md)

| Field | Data Type | Description | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| TargetList(inherited)||||||
| targetListType| enum <a href="./TargetingListType.md">TargetingListType</a>| Types of target list.| Req| Req| — |
| RuleTargetList||||||
| retargetingTagId| xsd: string| Tag ID for site retargeting.| Req| —| — |
| isPreset| enum <a href="./IsPreset.md">IsPreset</a>| Flag settings for history of past visit.| Req| —| — |
| isOpen| enum <a href="./IsOpen.md">IsOpen</a>| Display the status to reserve the reach or not for the target list.| Req| targetListType=RULE：Opt<br>targetListType=DEFAULT_LIST：?| — |
| reachPeriod| xsd:long| Cookies validation period.| Req| Opt| — |
| rules[]| <a href="./Rule.md">Rule</a>| Rule information for target list.| Req| Req| — |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

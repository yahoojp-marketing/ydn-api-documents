# PlacementUrlIdea
An object that holds the placement Url information.
### Service
+ [PlacementUrlIdeaService](../../services/PlacementUrlIdeaService.md)

### Namespace
[PlacementUrlIdeaService#Namespace](../../services/PlacementUrlIdeaService.md#namespace)

| name | type | maxOccurs | minOccurs | response | add | set | remove | description | 
|---|---|---|---|---|---|---|---|---|
| operationKey| long| 1| 0| ○| -| -| -| Number |
| operationSucceeded| long| 1| 0| ○| -| -| -| Determination as to whether it was able to search from white list (success: true fixed) |
| keyword| string| 1| 0| ○| -| -| -| Search Keyword |
| siteCategory| string| 1| 0| ○| -| -| -| Search Category |
| searchUrl| string| 1| 0| ○| -| -| -| URL |
| adFormat| enum <a href="./AdFormat.md">AdFormat</a>[]| unbounded| 0| ○| -| -| -| Advertisement format |
| desktopRearches| long| 1| 0| ○| -| -| -| Reach Number of PC(100 In the case of 0) |
| desktopAdRequests| long| 1| 0| ○| -| -| -| AD Number of PC(100 In the case of 0) |
| smartPhoneRearches| long| 1| 0| ○| -| -| -| Reach Number of SmartPhone (100 In the case of 0) |
| smartPhoneAdRequests| long| 1| 0| ○| -| -| -| AD Number of SmartPhone(100 In the case of 0) |
| tabletRearches| long| 1| 0| ○| -| -| -| Tablet(100 In the case of 0) |
| tabletAdRequests| long| 1| 0| ○| -| -| -| AD Number of Tablet (100 In the case of 0) |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

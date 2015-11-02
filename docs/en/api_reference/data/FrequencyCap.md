# FrequencyCap
The objects to keep Frequency cap.
### Service
+ [CampaignService](../services/CampaignService.md)

| name | type | maxOccurs | minOccurs | response | add | set | remove | description | 
|---|---|---|---|---|---|---|---|---|
| level| enum <a href="./FrequencyLevel.md">FrequencyLevel</a>| 1| 0| ○| Optional<br>※1| Optional<br>※2| Ignore| SFrequency Cap Level (Campaign or Ad Group or Ad) |
| timeUnit| enum <a href="./FrequencyTimeUnit.md">FrequencyTimeUnit</a>| 1| 0| ○| Optional<br>※1| Optional<br>※2| Ignore| Frequency Cap Time (Campaign or Ad Group or Ad) |
| impression| long| 1| 0| ○| Optional<br>※1| Optional<br>※2| Ignore| Maximum Number of Ad Impressions to Unique User |

※1 Specify all the items to add.<br>
※2 Requesting only updating items is possible when setting.<br>
*Method to remove the frequency cap:<br>
```xml
<ns1:frequencyCap>
　　　<ns1:impression>0</ns1:impression>
</ns1:frequencyCap>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

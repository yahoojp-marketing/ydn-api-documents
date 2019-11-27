

# FrequencyCap

FrequencyCap object describes frequency restriction.<br>
<br>
* All items must be specified when add operation.<br>
* Only update items can be requested when set operation.<br>
* Method to remove the frequency cap:<br>
```<br>
<ns1:frequencyCap>
  <ns1:impression>0</ns1:impression>
</ns1:frequencyCap>
```
        

### Service

+ [CampaignService](../../services/CampaignService.md)

### Namespace

[CampaignService#Namespace](../../services/CampaignService.md#namespace)

| Field | Type | Description | response | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| level | enum [FrequencyLevel](./FrequencyLevel.md) | Frequency Cap Level. | ○ | Optional | Optional | - | |
| timeUnit | enum [FrequencyTimeUnit](./FrequencyTimeUnit.md) | Frequency Cap Time. | ○ | Optional | Optional | - | |
| impression | xsd:long | Maximum Number of Ad Impressions to Unique User. | ○ | Optional | Optional | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

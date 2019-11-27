

# FrequencyCap

FrequencyCapは、フリクエンシー制御を表します。<br>
<br>
※ add時は全ての項目の指定が必須です。<br>
※ set時は更新する項目のみのリクエストが可能です。<br>
※ フリークエンシーキャップの解除方法は、以下の通りです：<br>
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
| level | enum [FrequencyLevel](./FrequencyLevel.md) | フリークエンシー制限の単位です。 | ○ | Optional | Optional | - | |
| timeUnit | enum [FrequencyTimeUnit](./FrequencyTimeUnit.md) | フリークエンシーの単位時間です。 | ○ | Optional | Optional | - | |
| impression | xsd:long | 同一ユーザに対する広告の最大インプレッション数です。 | ○ | Optional | Optional | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

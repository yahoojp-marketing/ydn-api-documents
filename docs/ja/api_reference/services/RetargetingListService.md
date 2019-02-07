# RetargetingListService
RetargetingListServiceでは、サイトリターゲティングのターゲットリストの取得および追加・更新・削除を行います。
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201812/RetargetingListService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201812/RetargetingListService?wsdl|
#### Namespace
http://im.yahooapis.jp/V201812/RetargetingList
#### サービス概要
サイトリターゲティングターゲットリストの取得および作成・更新・削除を行います。<br>
<br>
【ターゲットリストについて】<br>
サイトを訪れたユーザーの閲覧履歴を指定した条件で振り分け、グルーピングすることができる機能です。<br>
これにより、訴求ポイントがさらに絞られ、適した広告を出し分けることができます。<br>
ターゲットリストは3種類あります：<br>
・サイトリターゲティングタグ発行時に自動で作成される“デフォルト”リスト<br>
・条件（URL、カスタムラベル）を指定し、新たに作成するターゲットリスト<br>
・“デフォルト”リストや条件指定し作成したターゲットリストを組み合わせた“コンビネーション”リスト<br>
<br>

【注意事項】<br>
サイトリターゲティングタグ は、1アカウントにつき、「1個」発行可能です。<br>
ターゲットリストは、1アカウントにつき最大300個まで設定可能です。<br>
条件は1ターゲットリストあたり最大10個まで設定可能です。<br>
ターゲットリストの組み合わせは、1ターゲットリストあたり最大10個まで設定可能です。<br>

#### 操作
RetargetingListServiceで提供される操作を説明します。

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)

#### オブジェクト
[RetargetingList](../data/RetargetingList)

## get

### リクエスト
サイトリターゲティングのターゲットリストを取得します。

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [RetargetingListSelector](../data/RetargetingList/RetargetingListSelector.md) | サイトリターゲティングのターゲットリスト情報を取得します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201812/RetargetingList" xmlns:ns2="http://im.yahooapis.jp/V201812">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201812/RetargetingList" xmlns:ns2="http://im.yahooapis.jp/V201812">
      <selector>
        <accountId>1111</accountId>
        <targetListIds>100000001</targetListIds>
        <targetListIds>100000002</targetListIds>
        <targetListTypes>COMBINATION</targetListTypes>
        <targetListTypes>RULE</targetListTypes>
        <targetListTypes>DEFAULT_LIST</targetListTypes>
        <targetListTypes>SIMILARITY</targetListTypes>
        <targetListTypes>CUSTOM_AUDIENCE</targetListTypes>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>10</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 |
|---|---|---|
| rval | [RetargetingListPage](../data/RetargetingList/RetargetingListPage.md) | 操作結果を含むコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201812/RetargetingList" xmlns:ns2="http://im.yahooapis.jp/V201812">
      <ns2:service>RetargetingList</ns2:service>
      <ns2:requestTime>1536568328146</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201812" xmlns:ns2="http://im.yahooapis.jp/V201812/RetargetingList">
      <ns2:rval>
        <totalNumEntries>4</totalNumEntries>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:retargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:targetListId>12222</ns2:targetListId>
            <ns2:targetListName>DefaultList</ns2:targetListName>
            <ns2:description>Default List</ns2:description>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:RuleTargetList">
              <ns2:targetListType>DEFAULT_LIST</ns2:targetListType>
              <ns2:retargetingTagId>ES8KY92KGT</ns2:retargetingTagId>
              <ns2:isPreset>FALSE</ns2:isPreset>
              <ns2:reachPeriod>1</ns2:reachPeriod>
            </ns2:targetList>
          </ns2:retargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:retargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:targetListId>12222</ns2:targetListId>
            <ns2:targetListName>Rule List</ns2:targetListName>
            <ns2:description>Rule List</ns2:description>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:RuleTargetList">
              <ns2:targetListType>RULE</ns2:targetListType>
              <ns2:retargetingTagId>ES8KY92KGT</ns2:retargetingTagId>
              <ns2:isPreset>FALSE</ns2:isPreset>
              <ns2:reachPeriod>1</ns2:reachPeriod>
              <ns2:rules>
                <ns2:ruleConditions>
                  <ns2:type>URL</ns2:type>
                  <ns2:compareOperator>INCLUDED</ns2:compareOperator>
                  <ns2:value>/services</ns2:value>
                </ns2:ruleConditions>
                <ns2:ruleConditions>
                  <ns2:type>LABEL</ns2:type>
                  <ns2:compareOperator>NOT_EQUAL</ns2:compareOperator>
                  <ns2:value>Test</ns2:value>
                </ns2:ruleConditions>
              </ns2:rules>
              <ns2:rules>
                <ns2:ruleConditions>
                  <ns2:type>URL</ns2:type>
                  <ns2:compareOperator>INCLUDED</ns2:compareOperator>
                  <ns2:value>/test</ns2:value>
                </ns2:ruleConditions>
              </ns2:rules>
            </ns2:targetList>
          </ns2:retargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:retargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:targetListId>12222</ns2:targetListId>
            <ns2:targetListName>CombinationTargetList</ns2:targetListName>
            <ns2:description>Combination Target List</ns2:description>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:CombinationTargetList">
              <ns2:targetListType>COMBINATION</ns2:targetListType>
              <ns2:combinations>
                <ns2:logicalOperator>AND</ns2:logicalOperator>
                <ns2:targetLists>
                  <ns2:targetListId>11111</ns2:targetListId>
                  <ns2:targetListName>AAAAA</ns2:targetListName>
                </ns2:targetLists>
                <ns2:targetLists>
                  <ns2:targetListId>2222</ns2:targetListId>
                  <ns2:targetListName>BBBBB</ns2:targetListName>
                </ns2:targetLists>
              </ns2:combinations>
              <ns2:combinations>
                <ns2:logicalOperator>OR</ns2:logicalOperator>
                <ns2:targetLists>
                  <ns2:targetListId>33333</ns2:targetListId>
                  <ns2:targetListName>CCCCC</ns2:targetListName>
                </ns2:targetLists>
                <ns2:targetLists>
                  <ns2:targetListId>444</ns2:targetListId>
                  <ns2:targetListName>DD</ns2:targetListName>
                </ns2:targetLists>
              </ns2:combinations>
            </ns2:targetList>
          </ns2:retargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:retargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:targetListId>32222</ns2:targetListId>
            <ns2:targetListName>SimilarityTargetList</ns2:targetListName>
            <ns2:description>Similarity Target List</ns2:description>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimilarityTargetList">
              <ns2:targetListType>SIMILARITY</ns2:targetListType>
              <ns2:targetListId>9999</ns2:targetListId>
              <ns2:targetListSize>RATE_6</ns2:targetListSize>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_1</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_2</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_3</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_4</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_5</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_6</ns2:targetListSize>
                <ns2:reach>6600</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_7</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_8</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_9</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_10</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
            </ns2:targetList>
          </ns2:retargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:retargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:targetListId>32222</ns2:targetListId>
            <ns2:targetListName>CustomAudienceTargetList</ns2:targetListName>
            <ns2:description>Custom Audience Target List</ns2:description>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:CustomAudienceTargetList">
              <ns2:targetListType>CUSTOM_AUDIENCE</ns2:targetListType>
              <ns2:reachPeriod>9999</ns2:reachPeriod>
              <ns2:customAudienceId>ZZZZ</ns2:customAudienceId>
            </ns2:targetList>
          </ns2:retargetingList>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)

### リクエスト
サイトリターゲティングのターゲットリストを作成します。

| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [RetargetingListOperation](../data/RetargetingList/RetargetingListOperation.md) | サイトリターゲティングのターゲットリストを作成します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201812/RetargetingList" xmlns:ns2="http://im.yahooapis.jp/V201812">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201812/RetargetingList">
      <operations>
        <operator>ADD</operator>
        <accountId>1234</accountId>
        <operand>
          <targetListName>TargetList Default</targetListName>
          <description>TargetList Default</description>
          <targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RuleTargetList">
            <targetListType>DEFAULT_LIST</targetListType>
            <retargetingTagId>ES8KY92KGT</retargetingTagId>
            <isPreset>FALSE</isPreset>
            <isOpen>TRUE</isOpen>
            <reachPeriod>1</reachPeriod>
            <rules>
              <ruleConditions>
                <type>URL</type>
                <compareOperator>INCLUDED</compareOperator>
                <value>/services</value>
              </ruleConditions>
            </rules>
          </targetList>
        </operand>
        <operand>
          <targetListName>Rule List</targetListName>
          <description>Rule List</description>
          <targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RuleTargetList">
            <targetListType>RULE</targetListType>
            <retargetingTagId>ES8KY92KGT</retargetingTagId>
            <isPreset>FALSE</isPreset>
            <isOpen>TRUE</isOpen>
            <reachPeriod>1</reachPeriod>
            <rules>
              <ruleConditions>
                <type>URL</type>
                <compareOperator>INCLUDED</compareOperator>
                <value>/services</value>
              </ruleConditions>
              <ruleConditions>
                <type>LABEL</type>
                <compareOperator>NOT_EQUAL</compareOperator>
                <value>Test</value>
              </ruleConditions>
            </rules>
            <rules>
              <ruleConditions>
                <type>URL</type>
                <compareOperator>INCLUDED</compareOperator>
                <value>/test</value>
              </ruleConditions>
            </rules>
          </targetList>
        </operand>
        <operand>
          <targetListName>CombinationTargetList</targetListName>
          <description>Combination Target List</description>
          <targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="CombinationTargetList">
            <targetListType>COMBINATION</targetListType>
            <combinations>
              <logicalOperator>AND</logicalOperator>
              <targetLists>
                <targetListId>11111</targetListId>
              </targetLists>
              <targetLists>
                <targetListId>2222</targetListId>
              </targetLists>
            </combinations>
            <combinations>
              <logicalOperator>OR</logicalOperator>
              <targetLists>
                <targetListId>33333</targetListId>
              </targetLists>
              <targetLists>
                <targetListId>444</targetListId>
              </targetLists>
            </combinations>
          </targetList>
        </operand>
        <operand>
          <targetListName>SimilarityTargetList</targetListName>
          <description>Similarity Target List</description>
          <targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimilarityTargetList">
            <targetListType>SIMILARITY</targetListType>
            <targetListId>9999</targetListId>
            <targetListSize>RATE_6</targetListSize>
          </targetList>
        </operand>
        <operand>
          <targetListName>CustomAudienceTargetList</targetListName>
          <description>Custom Audience Target List</description>
          <deliveryStatus>ACTIVE</deliveryStatus>
          <targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="CustomAudienceTargetList">
            <targetListType>CUSTOM_AUDIENCE</targetListType>
            <reachPeriod>9999</reachPeriod>
            <customAudienceId>ZZZZ</customAudienceId>
          </targetList>
        </operand>
        <operand>
          <targetListName>AppEventTargetList</targetListName>
          <description>App Event Target List</description>
          <deliveryStatus>ACTIVE</deliveryStatus>
          <targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RuleTargetList">
            <targetListType>RULE</targetListType>
            <retargetingTagId>ES8KY92KGT</retargetingTagId>
            <isPreset>FALSE</isPreset>
            <isOpen>TRUE</isOpen>
            <reachPeriod>1</reachPeriod>
            <rules>
              <ruleConditions>
                <type>EVENT_TYPE</type>
                <compareOperator>EQUAL</compareOperator>
                <value>app_install</value>
              </ruleConditions>
            </rules>
          </targetList>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [RetargetingListReturnValue](../data/RetargetingList/RetargetingListReturnValue.md) | 操作結果を含むコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201812/RetargetingList" xmlns:ns2="http://im.yahooapis.jp/V201812">
      <ns2:service>RetargetingList</ns2:service>
      <ns2:requestTime>1536568328198</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201812" xmlns:ns2="http://im.yahooapis.jp/V201812/RetargetingList">
      <ns2:rval>
        <ListReturnValue.Type>RetargetingListReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:retargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:targetListId>12222</ns2:targetListId>
            <ns2:targetListName>DefaultList</ns2:targetListName>
            <ns2:description>Default List</ns2:description>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:RuleTargetList">
              <ns2:targetListType>DEFAULT_LIST</ns2:targetListType>
              <ns2:retargetingTagId>ES8KY92KGT</ns2:retargetingTagId>
              <ns2:isPreset>FALSE</ns2:isPreset>
              <ns2:reachPeriod>1</ns2:reachPeriod>
            </ns2:targetList>
          </ns2:retargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:retargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:targetListId>12222</ns2:targetListId>
            <ns2:targetListName>Rule List</ns2:targetListName>
            <ns2:description>Rule List</ns2:description>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:RuleTargetList">
              <ns2:targetListType>RULE</ns2:targetListType>
              <ns2:retargetingTagId>ES8KY92KGT</ns2:retargetingTagId>
              <ns2:isPreset>FALSE</ns2:isPreset>
              <ns2:reachPeriod>1</ns2:reachPeriod>
              <ns2:rules>
                <ns2:ruleConditions>
                  <ns2:type>URL</ns2:type>
                  <ns2:compareOperator>INCLUDED</ns2:compareOperator>
                  <ns2:value>/services</ns2:value>
                </ns2:ruleConditions>
                <ns2:ruleConditions>
                  <ns2:type>LABEL</ns2:type>
                  <ns2:compareOperator>NOT_EQUAL</ns2:compareOperator>
                  <ns2:value>Test</ns2:value>
                </ns2:ruleConditions>
              </ns2:rules>
              <ns2:rules>
                <ns2:ruleConditions>
                  <ns2:type>URL</ns2:type>
                  <ns2:compareOperator>INCLUDED</ns2:compareOperator>
                  <ns2:value>/test</ns2:value>
                </ns2:ruleConditions>
              </ns2:rules>
            </ns2:targetList>
          </ns2:retargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:retargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:targetListId>12222</ns2:targetListId>
            <ns2:targetListName>CombinationTargetList</ns2:targetListName>
            <ns2:description>Combination Target List</ns2:description>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:CombinationTargetList">
              <ns2:targetListType>COMBINATION</ns2:targetListType>
              <ns2:combinations>
                <ns2:logicalOperator>AND</ns2:logicalOperator>
                <ns2:targetLists>
                  <ns2:targetListId>11111</ns2:targetListId>
                  <ns2:targetListName>AAAAA</ns2:targetListName>
                </ns2:targetLists>
                <ns2:targetLists>
                  <ns2:targetListId>2222</ns2:targetListId>
                  <ns2:targetListName>BBBBB</ns2:targetListName>
                </ns2:targetLists>
              </ns2:combinations>
              <ns2:combinations>
                <ns2:logicalOperator>OR</ns2:logicalOperator>
                <ns2:targetLists>
                  <ns2:targetListId>33333</ns2:targetListId>
                  <ns2:targetListName>CCCCC</ns2:targetListName>
                </ns2:targetLists>
                <ns2:targetLists>
                  <ns2:targetListId>444</ns2:targetListId>
                  <ns2:targetListName>DD</ns2:targetListName>
                </ns2:targetLists>
              </ns2:combinations>
            </ns2:targetList>
          </ns2:retargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:retargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:targetListId>32222</ns2:targetListId>
            <ns2:targetListName>SimilarityTargetList</ns2:targetListName>
            <ns2:description>Similarity Target List</ns2:description>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimilarityTargetList">
              <ns2:targetListType>SIMILARITY</ns2:targetListType>
              <ns2:targetListId>9999</ns2:targetListId>
              <ns2:targetListSize>RATE_6</ns2:targetListSize>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_1</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_2</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_3</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_4</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_5</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_6</ns2:targetListSize>
                <ns2:reach>6600</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_7</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_8</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_9</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_10</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
            </ns2:targetList>
          </ns2:retargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:retargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:targetListId>32222</ns2:targetListId>
            <ns2:targetListName>CustomAudienceTargetList</ns2:targetListName>
            <ns2:description>Custom Audience Target List</ns2:description>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:CustomAudienceTargetList">
              <ns2:targetListType>CUSTOM_AUDIENCE</ns2:targetListType>
              <ns2:reachPeriod>9999</ns2:reachPeriod>
              <ns2:customAudienceId>ZZZZ</ns2:customAudienceId>
            </ns2:targetList>
          </ns2:retargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:retargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:targetListId>42222</ns2:targetListId>
            <ns2:targetListName>AppEventTargetList</ns2:targetListName>
            <ns2:description>App Event Target List</ns2:description>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:RuleTargetList">
              <ns2:targetListType>RULE</ns2:targetListType>
              <ns2:retargetingTagId>ES8KY92KGT</ns2:retargetingTagId>
              <ns2:isPreset>FALSE</ns2:isPreset>
              <ns2:reachPeriod>1</ns2:reachPeriod>
              <ns2:rules>
                <ns2:ruleConditions>
                  <ns2:type>EVENT_TYPE</ns2:type>
                  <ns2:compareOperator>EQUAL</ns2:compareOperator>
                  <ns2:value>app_install</ns2:value>
                </ns2:ruleConditions>
              </ns2:rules>
            </ns2:targetList>
          </ns2:retargetingList>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)

### リクエスト

| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [RetargetingListOperation](../data/RetargetingList/RetargetingListOperation.md) | サイトリターゲティングのターゲットリストを更新します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201812/RetargetingList" xmlns:ns2="http://im.yahooapis.jp/V201812">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201812/RetargetingList">
      <operations>
        <operator>SET</operator>
        <accountId>0</accountId>
        <operand>
          <targetListId>1111</targetListId>
          <targetListName>TargetList Default</targetListName>
          <description>TargetList Default</description>
          <targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RuleTargetList">
            <targetListType>DEFAULT_LIST</targetListType>
            <reachPeriod>1</reachPeriod>
            <rules>
              <ruleConditions>
                <type>URL</type>
                <compareOperator>INCLUDED</compareOperator>
                <value>/services</value>
              </ruleConditions>
            </rules>
          </targetList>
        </operand>
        <operand>
          <targetListId>2222</targetListId>
          <targetListName>Rule List</targetListName>
          <description>Rule List</description>
          <targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RuleTargetList">
            <targetListType>RULE</targetListType>
            <isPreset>FALSE</isPreset>
            <isOpen>TRUE</isOpen>
            <reachPeriod>1</reachPeriod>
            <rules>
              <ruleConditions>
                <type>URL</type>
                <compareOperator>INCLUDED</compareOperator>
                <value>/services</value>
              </ruleConditions>
              <ruleConditions>
                <type>LABEL</type>
                <compareOperator>NOT_EQUAL</compareOperator>
                <value>Test</value>
              </ruleConditions>
            </rules>
            <rules>
              <ruleConditions>
                <type>URL</type>
                <compareOperator>INCLUDED</compareOperator>
                <value>/test</value>
              </ruleConditions>
            </rules>
          </targetList>
        </operand>
        <operand>
          <targetListId>3333</targetListId>
          <targetListName>CombinationTargetList</targetListName>
          <description>Combination Target List</description>
          <targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="CombinationTargetList">
            <targetListType>COMBINATION</targetListType>
            <combinations>
              <logicalOperator>AND</logicalOperator>
              <targetLists>
                <targetListId>11111</targetListId>
              </targetLists>
              <targetLists>
                <targetListId>2222</targetListId>
              </targetLists>
            </combinations>
            <combinations>
              <logicalOperator>OR</logicalOperator>
              <targetLists>
                <targetListId>33333</targetListId>
              </targetLists>
              <targetLists>
                <targetListId>444</targetListId>
              </targetLists>
            </combinations>
          </targetList>
        </operand>
        <operand>
          <targetListId>4444</targetListId>
          <targetListName>SimilarityTargetList</targetListName>
          <description>Similarity Target List</description>
          <targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimilarityTargetList">
            <targetListType>SIMILARITY</targetListType>
            <targetListId>9999</targetListId>
            <targetListSize>RATE_6</targetListSize>
          </targetList>
        </operand>
        <operand>
          <targetListId>32222</targetListId>
          <targetListName>CustomAudienceTargetList</targetListName>
          <description>Custom Audience Target List</description>
          <targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="CustomAudienceTargetList">
            <targetListType>CUSTOM_AUDIENCE</targetListType>
          </targetList>
        </operand>
        <operand>
          <targetListId>42222</targetListId>
          <targetListName>AppEventTargetList</targetListName>
          <description>App Event Target List</description>
          <targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RuleTargetList">
            <targetListType>RULE</targetListType>
            <isPreset>FALSE</isPreset>
            <isOpen>TRUE</isOpen>
            <reachPeriod>1</reachPeriod>
            <rules>
              <ruleConditions>
                <type>EVENT_TYPE</type>
                <compareOperator>EQUAL</compareOperator>
                <value>app_launch</value>
              </ruleConditions>
            </rules>
          </targetList>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [RetargetingListReturnValue](../data/RetargetingList/RetargetingListReturnValue.md) | 操作結果を含むレポートのコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201812/RetargetingList" xmlns:ns2="http://im.yahooapis.jp/V201812">
      <ns2:service>RetargetingList</ns2:service>
      <ns2:requestTime>1536568328242</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201812" xmlns:ns2="http://im.yahooapis.jp/V201812/RetargetingList">
      <ns2:rval>
        <ListReturnValue.Type>RetargetingListReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:retargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:targetListId>12222</ns2:targetListId>
            <ns2:targetListName>DefaultList</ns2:targetListName>
            <ns2:description>Default List</ns2:description>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:RuleTargetList">
              <ns2:targetListType>DEFAULT_LIST</ns2:targetListType>
              <ns2:retargetingTagId>ES8KY92KGT</ns2:retargetingTagId>
              <ns2:isPreset>FALSE</ns2:isPreset>
              <ns2:reachPeriod>1</ns2:reachPeriod>
            </ns2:targetList>
          </ns2:retargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:retargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:targetListId>12222</ns2:targetListId>
            <ns2:targetListName>Rule List</ns2:targetListName>
            <ns2:description>Rule List</ns2:description>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:RuleTargetList">
              <ns2:targetListType>RULE</ns2:targetListType>
              <ns2:retargetingTagId>ES8KY92KGT</ns2:retargetingTagId>
              <ns2:isPreset>FALSE</ns2:isPreset>
              <ns2:reachPeriod>1</ns2:reachPeriod>
              <ns2:rules>
                <ns2:ruleConditions>
                  <ns2:type>URL</ns2:type>
                  <ns2:compareOperator>INCLUDED</ns2:compareOperator>
                  <ns2:value>/services</ns2:value>
                </ns2:ruleConditions>
                <ns2:ruleConditions>
                  <ns2:type>LABEL</ns2:type>
                  <ns2:compareOperator>NOT_EQUAL</ns2:compareOperator>
                  <ns2:value>Test</ns2:value>
                </ns2:ruleConditions>
              </ns2:rules>
              <ns2:rules>
                <ns2:ruleConditions>
                  <ns2:type>URL</ns2:type>
                  <ns2:compareOperator>INCLUDED</ns2:compareOperator>
                  <ns2:value>/test</ns2:value>
                </ns2:ruleConditions>
              </ns2:rules>
            </ns2:targetList>
          </ns2:retargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:retargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:targetListId>12222</ns2:targetListId>
            <ns2:targetListName>CombinationTargetList</ns2:targetListName>
            <ns2:description>Combination Target List</ns2:description>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:CombinationTargetList">
              <ns2:targetListType>COMBINATION</ns2:targetListType>
              <ns2:combinations>
                <ns2:logicalOperator>AND</ns2:logicalOperator>
                <ns2:targetLists>
                  <ns2:targetListId>11111</ns2:targetListId>
                  <ns2:targetListName>AAAAA</ns2:targetListName>
                </ns2:targetLists>
                <ns2:targetLists>
                  <ns2:targetListId>2222</ns2:targetListId>
                  <ns2:targetListName>BBBBB</ns2:targetListName>
                </ns2:targetLists>
              </ns2:combinations>
              <ns2:combinations>
                <ns2:logicalOperator>OR</ns2:logicalOperator>
                <ns2:targetLists>
                  <ns2:targetListId>33333</ns2:targetListId>
                  <ns2:targetListName>CCCCC</ns2:targetListName>
                </ns2:targetLists>
                <ns2:targetLists>
                  <ns2:targetListId>444</ns2:targetListId>
                  <ns2:targetListName>DD</ns2:targetListName>
                </ns2:targetLists>
              </ns2:combinations>
            </ns2:targetList>
          </ns2:retargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:retargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:targetListId>32222</ns2:targetListId>
            <ns2:targetListName>SimilarityTargetList</ns2:targetListName>
            <ns2:description>Similarity Target List</ns2:description>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimilarityTargetList">
              <ns2:targetListType>SIMILARITY</ns2:targetListType>
              <ns2:targetListId>9999</ns2:targetListId>
              <ns2:targetListSize>RATE_6</ns2:targetListSize>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_1</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_2</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_3</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_4</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_5</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_6</ns2:targetListSize>
                <ns2:reach>6600</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_7</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_8</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_9</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_10</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
            </ns2:targetList>
          </ns2:retargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:retargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:targetListId>32222</ns2:targetListId>
            <ns2:targetListName>CustomAudienceTargetList</ns2:targetListName>
            <ns2:description>Custom Audience Target List</ns2:description>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:CustomAudienceTargetList">
              <ns2:targetListType>CUSTOM_AUDIENCE</ns2:targetListType>
              <ns2:reachPeriod>9999</ns2:reachPeriod>
              <ns2:customAudienceId>ZZZZ</ns2:customAudienceId>
            </ns2:targetList>
          </ns2:retargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:retargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:targetListId>42222</ns2:targetListId>
            <ns2:targetListName>AppEventTargetList</ns2:targetListName>
            <ns2:description>App Event Target List</ns2:description>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:RuleTargetList">
              <ns2:targetListType>RULE</ns2:targetListType>
              <ns2:retargetingTagId>ES8KY92KGT</ns2:retargetingTagId>
              <ns2:isPreset>FALSE</ns2:isPreset>
              <ns2:reachPeriod>1</ns2:reachPeriod>
              <ns2:rules>
                <ns2:ruleConditions>
                  <ns2:type>EVENT_TYPE</ns2:type>
                  <ns2:compareOperator>EQUAL</ns2:compareOperator>
                  <ns2:value>app_launch</ns2:value>
                </ns2:ruleConditions>
              </ns2:rules>
            </ns2:targetList>
          </ns2:retargetingList>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)

### リクエスト

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| operations | ○ | [RetargetingListOperation](../data/RetargetingList/RetargetingListOperation.md)|サイトリターゲティングのターゲットリストを削除します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201812/RetargetingList" xmlns:ns2="http://im.yahooapis.jp/V201812">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201812/RetargetingList">
      <operations>
        <operator>REMOVE</operator>
        <accountId>0</accountId>
        <operand>
          <targetListId>1111</targetListId>
        </operand>
        <operand>
          <targetListId>2222</targetListId>
        </operand>
        <operand>
          <targetListId>3333</targetListId>
        </operand>
        <operand>
          <targetListId>4444</targetListId>
        </operand>
        <operand>
          <targetListId>32222</targetListId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 |
|---|---|---|
| rval | [RetargetingListReturnValue](../data/RetargetingList/RetargetingListReturnValue.md) | 操作結果を含むコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201812/RetargetingList" xmlns:ns2="http://im.yahooapis.jp/V201812">
      <ns2:service>RetargetingList</ns2:service>
      <ns2:requestTime>1536568328287</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201812" xmlns:ns2="http://im.yahooapis.jp/V201812/RetargetingList">
      <ns2:rval>
        <ListReturnValue.Type>RetargetingListReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:retargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:targetListId>12222</ns2:targetListId>
            <ns2:targetListName>DefaultList</ns2:targetListName>
            <ns2:description>Default List</ns2:description>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:RuleTargetList">
              <ns2:targetListType>DEFAULT_LIST</ns2:targetListType>
              <ns2:retargetingTagId>ES8KY92KGT</ns2:retargetingTagId>
              <ns2:isPreset>FALSE</ns2:isPreset>
              <ns2:reachPeriod>1</ns2:reachPeriod>
            </ns2:targetList>
          </ns2:retargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:retargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:targetListId>12222</ns2:targetListId>
            <ns2:targetListName>Rule List</ns2:targetListName>
            <ns2:description>Rule List</ns2:description>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:RuleTargetList">
              <ns2:targetListType>RULE</ns2:targetListType>
              <ns2:retargetingTagId>ES8KY92KGT</ns2:retargetingTagId>
              <ns2:isPreset>FALSE</ns2:isPreset>
              <ns2:reachPeriod>1</ns2:reachPeriod>
              <ns2:rules>
                <ns2:ruleConditions>
                  <ns2:type>URL</ns2:type>
                  <ns2:compareOperator>INCLUDED</ns2:compareOperator>
                  <ns2:value>/services</ns2:value>
                </ns2:ruleConditions>
                <ns2:ruleConditions>
                  <ns2:type>LABEL</ns2:type>
                  <ns2:compareOperator>NOT_EQUAL</ns2:compareOperator>
                  <ns2:value>Test</ns2:value>
                </ns2:ruleConditions>
              </ns2:rules>
              <ns2:rules>
                <ns2:ruleConditions>
                  <ns2:type>URL</ns2:type>
                  <ns2:compareOperator>INCLUDED</ns2:compareOperator>
                  <ns2:value>/test</ns2:value>
                </ns2:ruleConditions>
              </ns2:rules>
            </ns2:targetList>
          </ns2:retargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:retargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:targetListId>12222</ns2:targetListId>
            <ns2:targetListName>CombinationTargetList</ns2:targetListName>
            <ns2:description>Combination Target List</ns2:description>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:CombinationTargetList">
              <ns2:targetListType>COMBINATION</ns2:targetListType>
              <ns2:combinations>
                <ns2:logicalOperator>AND</ns2:logicalOperator>
                <ns2:targetLists>
                  <ns2:targetListId>11111</ns2:targetListId>
                  <ns2:targetListName>AAAAA</ns2:targetListName>
                </ns2:targetLists>
                <ns2:targetLists>
                  <ns2:targetListId>2222</ns2:targetListId>
                  <ns2:targetListName>BBBBB</ns2:targetListName>
                </ns2:targetLists>
              </ns2:combinations>
              <ns2:combinations>
                <ns2:logicalOperator>OR</ns2:logicalOperator>
                <ns2:targetLists>
                  <ns2:targetListId>33333</ns2:targetListId>
                  <ns2:targetListName>CCCCC</ns2:targetListName>
                </ns2:targetLists>
                <ns2:targetLists>
                  <ns2:targetListId>444</ns2:targetListId>
                  <ns2:targetListName>DD</ns2:targetListName>
                </ns2:targetLists>
              </ns2:combinations>
            </ns2:targetList>
          </ns2:retargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:retargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:targetListId>32222</ns2:targetListId>
            <ns2:targetListName>SimilarityTargetList</ns2:targetListName>
            <ns2:description>Similarity Target List</ns2:description>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimilarityTargetList">
              <ns2:targetListType>SIMILARITY</ns2:targetListType>
              <ns2:targetListId>9999</ns2:targetListId>
              <ns2:targetListSize>RATE_6</ns2:targetListSize>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_1</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_2</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_3</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_4</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_5</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_6</ns2:targetListSize>
                <ns2:reach>6600</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_7</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_8</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_9</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
              <ns2:targetListSizeReaches>
                <ns2:targetListSize>RATE_10</ns2:targetListSize>
                <ns2:reach>0</ns2:reach>
              </ns2:targetListSizeReaches>
            </ns2:targetList>
          </ns2:retargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:retargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:targetListId>32222</ns2:targetListId>
            <ns2:targetListName>CustomAudienceTargetList</ns2:targetListName>
            <ns2:description>Custom Audience Target List</ns2:description>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:CustomAudienceTargetList">
              <ns2:targetListType>CUSTOM_AUDIENCE</ns2:targetListType>
              <ns2:reachPeriod>9999</ns2:reachPeriod>
              <ns2:customAudienceId>ZZZZ</ns2:customAudienceId>
            </ns2:targetList>
          </ns2:retargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:retargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:targetListId>42222</ns2:targetListId>
            <ns2:targetListName>AppEventTargetList</ns2:targetListName>
            <ns2:description>App Event Target List</ns2:description>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:RuleTargetList">
              <ns2:targetListType>RULE</ns2:targetListType>
              <ns2:retargetingTagId>ES8KY92KGT</ns2:retargetingTagId>
              <ns2:isPreset>FALSE</ns2:isPreset>
              <ns2:reachPeriod>1</ns2:reachPeriod>
              <ns2:rules>
                <ns2:ruleConditions>
                  <ns2:type>EVENT_TYPE</ns2:type>
                  <ns2:compareOperator>EQUAL</ns2:compareOperator>
                  <ns2:value>app_launch</ns2:value>
                </ns2:ruleConditions>
              </ns2:rules>
            </ns2:targetList>
          </ns2:retargetingList>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

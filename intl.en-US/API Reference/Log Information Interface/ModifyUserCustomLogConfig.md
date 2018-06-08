# ModifyUserCustomLogConfig {#reference_zy3_f4f_vdb .reference}

Modifies the user customized log configuration information.

## Request parameters {#section_j5v_h4f_vdb .section}

|Parameters|Type|Required|Description|
|:---------|:---|:-------|:----------|
|Action|String|Yes|Operation interface name, required parameter. Value: ModifyUserCustomLogConfig|
|ConfigId|String|Yes|Log configuration ID.|
|Tag|String|Yes|Log configuration tag information \(no more than 256 characters\)|

## Return Parameters {#section_wk3_l4f_vdb .section}

|Parameters|Type|Description|
|:---------|:---|:----------|
|RequestID|String|Request ID of the task|

## Specific error codes {#section_tjv_n4f_vdb .section}

|Error Code|Message|HTTP Return Code|Meaning|
|:---------|:------|:---------------|:------|
|InvalidConfigId|The configId provided does not belong to you.|404|Tag information contains up to 256 characters|
|InvalidTag|Tag should be less than 256 characters.|403| Tag information contains up to 256 characters|

## Examples {#section_s5v_h4f_vdb .section}

**Request example**

```
https://cdn.aliyuncs.com?Action=ModifyUserCustomLogConfig&Tag=xxxxPublic Request Parameter>
```

**Return example**

```
{"RequestId":"CEC1492F-EB71-4481-94CF-34BA007DC8E1"}
```


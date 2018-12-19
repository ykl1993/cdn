# BatchStartCdnDomain {#reference613 .reference}

启用状态为停用的加速域名，将 DomainStatus 变更为 Online。

**说明：** 域名对应账户如果由于欠费，或域名处于非法状态，无法正常调用该接口启用加速域名。

## 请求参数 { .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数。取值：BatchStartCdnDomain|
|DomainNames|String|是|需要接入DCDN的域名，用逗号分隔。|

## 返回参数 { .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|该条任务请求ID|

## 示例 { .section}

请求示例：

```
http://cdn.aliyuncs.com?Action=BatchStartCdnDomain&DomainNames=example.com&<公共请求参数>


```

返回示例

JSON格式：

```language-json
{
  "RequestId": "0AEDAF20-4DDF-4165-8750-47FF9C1929C9"
}


```


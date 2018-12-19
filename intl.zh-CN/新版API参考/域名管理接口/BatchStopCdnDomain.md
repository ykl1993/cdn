# BatchStopCdnDomain {#reference1401 .reference}

停用某个加速域名，将 DomainStatus 变更为 Offline。

**说明：** 

-   停用该加速域名后，该条加速域名信息仍保留，针对加速域名的请求系统将做自动回源处理。
-   若暂时不需要对某域名进行加速，推荐使用StopDomain接口，暂停域名加速效果。

## 请求参数 { .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：BatchStopCdnDomain|
|DomainNames|String|是|需要接入DCDN的域名，逗号分隔。|

## 返回参数 { .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestID|String|该条任务请求ID|

## 示例 { .section}

请求示例

```
http://cdn.aliyuncs.com?Action=BatchStopCdnDomain&DomainNames=example.com&<公共请求参数>
```

返回示例

JSON格式：

```language-json
{
  "RequestId": "324AEFFF-308C-4DA7-8CD3-01B277B98F28"
}
```


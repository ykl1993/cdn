# StopCdnDomain {#reference1012 .reference}

停用某个加速域名，将 DomainStatus 变更为 Offline。

**说明：** 停用该加速域名后，该条加速域名信息仍保留，针对加速域名的请求系统将做自动回源处理。

## 请求参数 { .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数 取值：StopCdnDomain|
|DomainName|String|是|需要接入DCDN的域名|

## 返回参数 { .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|该条任务请求ID|

## 示例 { .section}

请求示例：

```
http://cdn.aliyuncs.com?Action=StopCdnDomain&DomainName=example.com&<公共请求参数>



```

返回示例

JSON格式：

```language-json
{
  "RequestId": "324AEFFF-308C-4DA7-8CD3-01B277B98F28"
}


```

## 错误码 { .section}

|错误代码|错误信息|HTTP 状态码|描述|
|:---|:---|:-------|:-|
|InvalidDomain.NotFound|The domain provided does not belong to you.|404|域名不存在或不属于当前用户|
|IllegalOperation|Illegal domain operate is not permitted.|403|没有权限执行当前操作|
|ServiceBusy|The specified Domain is configuring, please retry later.|403|域名正在配置中, 请稍后再试|


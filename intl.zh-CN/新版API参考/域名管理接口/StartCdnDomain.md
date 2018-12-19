# StartCdnDomain {#reference1016 .reference}

启用状态为停用的加速域名，将 DomainStatus 变更为 Online。

**说明：** 域名对应账户如果由于欠费，或域名处于非法状态，无法正常调用该接口启用加速域名。

## 请求参数 { .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数 取值：StartCdnDomain|
|DomainName|String|是|需要接入DCDN的域名|

## 返回参数 { .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|该条任务请求ID|

## 示例 { .section}

请求示例：

```
http://cdn.aliyuncs.com?Action=StartCdnDomain&DomainName=example.com&<公共请求参数>


```

返回示例

JSON格式：

```language-json
{
  "RequestId": "0AEDAF20-4DDF-4165-8750-47FF9C1929C9"
}


```

## 错误码 { .section}

|错误代码|错误信息|HTTP 状态码|描述|
|:---|:---|:-------|:-|
|InvalidDomain.NotFound|The domain provided does not belong to you.|404|域名不存在或不属于当前用户|
|IllegalOperation|Illegal domain operate is not permitted.|403|没有权限执行当前操作|
|ServiceBusy|The specified Domain is configuring, please retry later.|403|域名正在配置中，请稍后再试。|


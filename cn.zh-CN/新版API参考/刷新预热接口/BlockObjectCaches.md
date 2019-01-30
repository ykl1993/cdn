# BlockObjectCaches {#reference2288 .reference}

封禁节点上的文件内容。封禁Cache节点指定URL内容，支持URL批量操作。

**说明：** 

-   同一个 ID 每天最多可提交100个封禁请求。
-   该资源封禁后，访问将返回403。
-   您需要添加白名单后才能使用词接口，白名单请您提交工单联系售后技术同学。

## 请求参数 { .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数。取值：BlockObjectCaches。|
|ObjectPath|String|是|输入示例：example.com/image/1.png，多个URL之间需要用换行符（\\n或\\r\\n）分隔。|
|Maxage|Integer|否|block生效时长。单位：秒。最小600，最大864000。|
|Type|String|是| -   block：封禁。
-   unblock：解封。

 |

## 返回参数 { .section}

|名称|类型|描述|
|:-|:-|:-|
|BlockTaskId|String|封禁返回的任务ID，多个任务ID用逗号（半角）分隔。|

## 示例 { .section}

请求示例

```
https://cdn.aliyuncs.com?&Action=BlockObjectCaches&ObjectPath=example.com/test.txt&Type=block&<公共请求参数>

```

返回示例

JSON格式：

```
{
"BlockTaskId":"704222904","RequestId":"D61E4801-EAFF-4A63-AAE1-FBF6CE1CFD1C"
}
```

## 错误码 { .section}

|错误代码|错误信息|HTTP 状态码|描述|
|:---|:---|:-------|:-|
|Throttling|Request was denied due to request throttling.|503|请求被流量控制限制。|
|IllegalOperation|Illegal domain operate is not permitted.|403|非法域名，无法操作。|
|OperationDenied|Your account does not open CDN service yet.|403|未开通CDN服务。|
|OperationDenied|Your CDN service is suspended.|403|CDN服务已被停止。|
|InvalidDomain.NotFound|The domain provided does not belong to you.|404|域名不存在或不属于当前用户。|
|InvalidDomain.Offline|The domain provided is offline.|404|域名已下线。|
|QuotaExceeded.Refresh|You've exceeded the prescribed refresh limits.|400|超出当日刷新限制。|
|ServiceBusy|The specified Domain is configuring, please retry later.|403|域名正在配置中，请稍后再试。|
|InvalidDomain.Configure\_failed|Failed to configure the provided domain.|500|域名配置失败，无法封禁。|
|MissingParameter|The input parameter "ObjectPath" that is mandatory for processing this request is not supplied.|400|缺少ObjectPath参数。|
|InvalidObjectPath.Malformed|The specific value of parameter ObjectPath is malformed.|400|ObjectPath值格式错误。|
|InvalidExtensiveDomain.ValueNotSupported|Extensive domain not supported.|400|不支持泛域名。|


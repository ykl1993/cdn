# DescribeRefreshRemainNumber {#reference1270 .reference}

查询刷新、预热URL及目录的最大限制数量，以及当日剩余刷新、预热URL及目录的次数。

**说明：** 刷新预热类接口包含 RefreshObjectCaches 刷新接口和 PushObjectCache 预热接口。

## 请求参数 { .section}

|参数|类型|是否必需|描述|
|--|--|----|--|
|Action|String|是|操作接口名，系统规定参数。取值：DescribeRefreshRemainNumber。|

## 返回参数 { .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|UrlQuota|String|当天url刷新数量上限。|
|DirQuota|String|当天路径刷新数量上限。|
|UrlRemain|String|当天剩余url刷新数量。|
|DirRemain|String|当天剩余目录刷新数量。|
|PreloadQuota|String|当天预热数量上限。|
|PreloadRemain|String|当天剩余预热数量。|

## 示例 { .section}

请求示例：

```
http://cdn.aliyuncs.com?Action=DescribeRefreshQuota
&<公共请求参数>

```

返回示例：

JSON格式

```language-json
{
    "DirQuota": "100",
    "DirRemain": "99",
    "RequestId": "42E0554B-80F4-4921-AED6-ACFB22CAAAD0",
    "UrlQuota": "2000",
    "UrlRemain": "1996",
    "PreloadQuota": "500",
    "PreloadRemain": "400"
}

```

## 错误码 { .section}

|错误代码|错误信息|HTTP 状态码|描述|
|:---|:---|:-------|:-|
|Throttling|Request was denied due to request throttling.|503|请求被流量控制限制。|
|OperationDenied|Your account does not open CDN service yet.|403|未开通CDN服务。|
|OperationDenied|Your CDN service is suspended.|403|CDN服务已被停止。|

公共错误码参见 [附录](../../../../dita-oss-bucket/SP_19/DNCDN11878652/ZH-CN_TP_5278.dita)。


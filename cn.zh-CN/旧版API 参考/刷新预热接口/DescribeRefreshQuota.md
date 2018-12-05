# DescribeRefreshQuota {#reference_snj_mvz_5db .reference}

刷新（包含预热）URL及目录的最大限制数量。

当日剩余刷新（含预热）URL及目录的次数。

限制条件：

-   刷新预热类接口包含RefreshObjectCaches 刷新接口和 PushObjectCache 预热接口。

## 请求参数 {#section_nrf_vvz_5db .section}

|参数|类型|是否必选|示例值|描述|
|:-|:-|:---|:--|:-|
|Action|String|是|DescribeRefreshQuota| 系统规定参数。取值：

 DescribeRefreshQuota

 |

## 返回参数 {#section_mtw_cwz_5db .section}

|参数|类型|示例值|描述|
|:-|:-|:--|:-|
|RequestId|String|42E0554B-80F4-4921-AED6-ACFB22CAAAD0| 请求ID。

 |
|UrlQuota|String|2000| 当天URL刷新数量上限。

 |
|DirQuota|String|100| 当天路径刷新数量上限。

 |
|UrlRemain|String|1996| 当天剩余URL刷新数量。

 |
|DirRemain|String|99| 当天剩余目录刷新数量。

 |
|PreloadQuota|String|500|当天预热数量上限。|
|PreloadRemain|String|400|当天剩余预热数量。|
|BlockQuota|String|300|当天封禁上限。|
|blockRemain|String|200|当天封禁剩余量。|

## 示例 {#section_mdj_rwz_5db .section}

**请求示例**

```
http://cdn.aliyuncs.com?Action=DescribeRefreshQuota&公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "DirQuota":"100",
        "DirRemain":"99",
        "PreloadQuota":"500",
        "PreloadRemain":"400",
        "RequestId":"42E0554B-80F4-4921-AED6-ACFB22CAAAD0",
        "UrlQuota":"2000",
        "UrlRemain":"1996"
    }
    ```


**异常返回格式**

-   JSON格式

    ```
    {
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    }
    ```



# ModifyCdnService {#reference_kdm_l5t_vdb .reference}

变更CDN服务的计费类型。

-   需先开通才可执行此操作。
-   变更计费类型，次日00:00生效；多次变更以最新提交的为准。
-   计费类型：
    -   按峰值带宽计费。
    -   按使用流量计费。

## 请求参数 {#section_mbs_s5t_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|ModifyCdnService|系统规定参数。取值：ModifyCdnService|
|InternetChargeType|String|是|PayByTraffic|开通服务的计费类型。

 -   按流量
-   按带宽峰值

 用户必须指定类型：按流量（PayByTraffic），按带宽峰值（PayByBandwidth）。|

## 返回参数 {#section_gl2_3xt_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID|

## 示例 {#section_sz4_ctt_vdb .section}

**请求示例**

```
https://cdn.aliyuncs.com?&Action=ModifyCdnService&InternetChargeType=PayByTraffic&公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "RequestId":"97C68796-EB7F-4D41-9D5B-12B909D76508"
    }
    ```


**异常返回示例**

-   JSON格式

    ```
    {
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    }
    ```



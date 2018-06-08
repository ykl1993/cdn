# 开通CDN {#reference_llj_4bt_vdb .reference}

开通CDN服务，只有开通后，才能进行域名操作。

-   一个用户只能开通一次。
-   开通条件：帐号已通过实名认证。

**说明：** 请确保在使用该接口前，已充分了解CDN产品的收费方式和价格。详情参见 [计费方式](../intl.zh-CN/产品定价/计费方式.md#)详情。

## 请求参数 {#section_lgd_3rt_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|OpenCdnService|系统规定参数。取值：OpenCdnService|
|InternetChargeType|String|是|PayByTraffic|开通服务的计费类型：

 -   按流量\(PayByTraffic\)
-   按带宽峰值\(PayByBandwidth\)

 如果用户不指定，默认按流量（PayByTraffic）。|

## 返回参数 {#section_zgb_cst_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID|

## 示例 {#section_sz4_ctt_vdb .section}

**请求示例**

```
https://cdn.aliyuncs.com?&Action=OpenCdnService&InternetChargeType=PayByBandwidth&公共请求参数
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



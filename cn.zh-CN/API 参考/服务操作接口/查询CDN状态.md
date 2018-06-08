# 查询CDN状态 {#reference_tnf_qtt_vdb .reference}

查询CDN服务状态。包括：当前计费类型，服务开通时间，下次生效的计费类型，当前业务状态等。

## 请求参数 {#section_v4v_5tt_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|DescribeCdnService|系统规定参数。取值：DescribeCdnService|

## 返回参数 {#section_ukj_xtt_vdb .section}

|参数|类型|示例值|描述|
|InternetChargeType|String|PayByTraffic| 计费类型。

 -   PayByTraffic
-   PayByBandwidth

 |
|OpeningTime|String|2014-02-28T13:11:49Z|开通服务时间，ISO 8601时间格式。|
|ChangingChargeType|String|PayByTraffic| 下次生效的计费类型。

 -   PayByTraffic
-   PayByBandwidth

 |
|ChangingAffectTime|String|2014-11-27T16:00:00Z|GMT时间。|
|OperationLocks| | |业务锁定状态，例如：欠费、安全等。|
|  └LockReason|String|financial|业务锁定的原因。|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。|
|InstanceId|String|aliuid|实例ID。|

## 示例 {#section_sz4_ctt_vdb .section}

**请求示例**

```
https://cdn.aliyuncs.com?&Action=DescribeCdnService&公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "ChangingAffectTime":"2014-11-27T16:00:00Z",
        "ChangingChargeType":"PayByBandwidth",
        "InternetChargeType":"PayByTraffic",
        "OpeningTime":"2014-02-28T13:11:49Z",
        "OperationLocks":{
            "LockReason":[]
        },
        "RequestId":"BFFCDFAD-DACC-484E-9BE6-0AF3B3A0DD23"
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



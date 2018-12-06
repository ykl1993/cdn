# StopCdnDomain {#reference_vdv_zrx_5db .reference}

停用某个加速域名，将DomainStatus变更为offline。

**说明：** 

-   停用该加速域名后，该条加速域名信息仍保留，针对加速域名的请求系统将做自动回源处理。
-   若暂时不需要对某域名进行加速，推荐使用StopDomain接口，暂停域名加速效果。

## 请求参数 {#section_zv2_w1y_5db .section}

|参数|类型|是否必选|示例值|描述|
|:-|:-|:---|:--|:-|
|Action|String|是|StopCdnDomain| 系统规定参数。取值：

 StopCdnDomain

 |
|DomainName|String|是|www.yourdomain.com| 需要接入CDN的域名。

 |

## 返回参数 {#section_tlm_hby_5db .section}

|参数|类型|示例值|描述|
|:-|:-|:--|:-|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8| 请求ID

 |

## 示例 {#section_ur3_qby_5db .section}

**请求示例**

```
http://cdn.aliyuncs.com?Action=StopDomain&DomainName=test.com&公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "RequestId":"324AEFFF-308C-4DA7-8CD3-01B277B98F28"
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



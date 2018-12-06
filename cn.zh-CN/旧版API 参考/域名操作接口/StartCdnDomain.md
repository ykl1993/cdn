# StartCdnDomain {#reference_gwk_pry_5db .reference}

启用状态为“停用”的加速域名，将DomainStatus变更为online。

**说明：** 域名对应账户如果由于欠费，或域名处于非法状态，无法正常调用该接口启用加速域名。

## 请求参数 {#section_j31_wry_5db .section}

|参数|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|StartCdnDomain| 系统规定参数。 取值：

 StartCdnDomain

 |
|DomainName|String|是|www.yourdomain.com|需要接入CDN的域名。|

## 返回参数 {#section_t25_csy_5db .section}

|参数|类型|示例值|描述|
|:-|:-|:--|:-|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8| 请求ID

 |

## 示例 {#section_mkz_gsy_5db .section}

**请求示例**

```
http://cdn.aliyuncs.com?Action=StartCdnDomain&DomainName=test.com&公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "RequestId":"0AEDAF20-4DDF-4165-8750-47FF9C1929C9"
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



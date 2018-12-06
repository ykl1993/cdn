# SetHttpHeaderConfig {#reference_ery_zgl_vdb .reference}

设置自定义http头。

## 请求参数 {#section_u4z_2hl_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|SetHttpHeaderConfig|系统规定参数。取值：SetHttpHeaderConfig|
|DomainName|String|是|www.yourdomain.com|您的加速域名。|
|HeaderKey|String|是|Content-Type| 要设置HTTP头参数。取值：

 -   Content-Type
-   Cache-Control
-   Content-Disposition
-   Content-Language
-   Expires
-   Access-Control-Allow-Origin
-   Access-Control-Allow-Methods
-   Access-Control-Allow-Headers
-   Access-Control-Max-Age
-   Access-Control-Expose-Headers
-   Access-Control-Allow-Credentials

 |
|HeaderValue|String|是|application|要设置的HTTP头参数的取值。|

## 回参数 {#section_cgc_33l_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID|

## 示例 {#section_g1p_gcg_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com/?Action=SetHttpHeaderConfig
&DomainName=www.macaron.org.cn
&HeaderKey=Content-Type
&headerValue=application
&公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "RequestId":"04F0F334-1335-436C-A1D7-6C044FE73368"
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



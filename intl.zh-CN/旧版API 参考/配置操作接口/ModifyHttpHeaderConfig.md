# ModifyHttpHeaderConfig {#reference_tbh_p3l_vdb .reference}

修改自定义http头。

## 请求参数 {#section_bxg_r3l_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|ModifyHttpHeaderConfig|系统规定参数。取值：ModifyHttpHeaderConfig|
|ConfigID|String|是|892783|要修改的配置ID。|
|DomainName|String|是|www.yourdomain.com|您的加速域名。|
|HeaderKey|String|是|content-type| 要设置HTTP头参数。取值：

 -   content-type
-   cache-control
-   content-disposition
-   content-language
-   expires
-   access-control-allow-origin
-   access-control-allow-methods
-   access-control-max-age

 |
|HeaderValue|String|是|application|要设置的HTTP头参数的取值。|

## 返回参数 {#section_ih1_z3l_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID。|

## 示例 {#section_g1p_gcg_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com/?Action=ModifyHttpHeaderConfig
&DomainName=www.macaron.org.cn
&HeaderKey=content-type
&headerValue=application
&ConfigID=892783
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



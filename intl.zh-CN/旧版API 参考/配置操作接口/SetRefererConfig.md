# SetRefererConfig {#reference_bf3_kdg_vdb .reference}

设置加速域名的Refer防盗链功能。

## 请求参数 {#section_cfq_mdg_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|SetRefererConfig|系统规定参数。取值：SetRefererConfig|
|DomainName|String|是|www.yourdomain.com|您的加速域名。|
|ReferType|String|是|block| refer类型。取值：

 -   block：黑名单
-   allow：白名单

 |
|AllowEmpty|String|否|on|是否允许空refer访问。取值：

 -   on：允许
-   off：不允许

 默认值：on|
|DisableAst|String|否|off|是否精确匹配域名。取值：

 -   on：精确匹配，不自动匹配子域名
-   off：模糊匹配，自动匹配子域名

 默认值：off|
|ReferList|String|否|a.com,b.com|逗号隔开的域名列表。|

## 返回参数 {#section_asb_pdg_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID|

## 示例 {#section_g1p_gcg_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com/?Action=SetRefererConfig
&DomainName=www.macaron.org.cn
&ReferList=www.aliyun.com%2Cwww.taobao.com
&ReferType=allow
&AllowEmpty=on
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



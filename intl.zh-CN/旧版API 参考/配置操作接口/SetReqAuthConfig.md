# SetReqAuthConfig {#reference_y2t_lxg_vdb .reference}

设置加速域名的访问鉴权配置。

-   [鉴权功能说明](../../../../intl.zh-CN/用户指南/域名管理/访问控制设置/鉴权配置.md#)
-   python版本的鉴权代码示例

## 请求参数 {#section_gvp_cgl_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|SetReqAuthConfig|系统规定参数。取值：SetReqAuthConfig|
|AuthType|String|是|no\_auth| 鉴权类型。取值:

 -   “no\_auth”：关闭
-   “type\_a”：A方式
-   “type\_b”：B方式
-   “type\_c”：C方式
-   “type\_d”：D方式
-   ”type\_e”：E方式

 |
|DomainName|String|是|www.yourdomain.com|您的加速域名。|
|AuthRemoteDesc|String|否|aaa|模式字符串。|
|Key1|String|否|fd8eqw3Q|主鉴权key，输入大小写字母、数字，长度1到64位。|
|Key2|String|否|v83ka2np|副鉴权Key，输入大小写字母、数字，长度1到64位。|
|TimeOut|String|否|2400|有效时间，输入数字。|

## 返回参数 {#section_pkl_kgl_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID|

## 示例 {#section_g1p_gcg_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com/?Action=SetReqAuthConfig
&DomainName=www.macaron.org.cn
&AuthType=type_a
&Key1=fd8eqw3Q
&Key2=v83ka2np
&TimeOut=2400
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



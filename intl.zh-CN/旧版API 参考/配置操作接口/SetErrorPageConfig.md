# SetErrorPageConfig {#reference_erv_kbg_vdb .reference}

设置加速域名自定义404错误页面跳转。

## 请求参数 {#section_myj_mbg_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|SetErrorPageConfig|系统规定参数。取值：SetErrorPageConfig|
|DomainName|String|是|www.yourdomain.com|您的加速域名。|
|PageType|String|是|default| 错误页面类型。取值：

 -   default：默认页面
-   charity：公益页面
-   other：自定义页面

 |
|CustomPageUrl|String|否|[http://www.macaron.org.cn/notfound.html](http://www.macaron.org.cn/notfound.html)|自定义发生错误后跳转到页面URL（该加速域名下的完整路径）。|

## 返回参数 {#section_mns_ccg_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID|

## 示例 {#section_g1p_gcg_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com/?Action=SetErrorPageConfig
&DomainName=www.macaron.org.cn
&CustomPageUrl=http://www.macaron.org.cn/notfound.html
&PageType=other
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



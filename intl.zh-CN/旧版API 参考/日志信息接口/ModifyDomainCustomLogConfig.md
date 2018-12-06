# ModifyDomainCustomLogConfig {#reference_w1y_nnf_vdb .reference}

修改域名所属日志自定义日志配置信息。

## 请求参数 {#section_u2t_4nf_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|ModifyDomainCustomLogConfig|系统规定参数。取值：ModifyDomainCustomLogConfig|
|ConfigId|String|是|123|日志配置ID。|
|DomainName|String|是|a.com|域名。|
|Version|String|否|2014-11-11|API版本号。|

## 返回参数 {#section_pg1_5nf_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|94E3559F-7B6A-4A5E-AFFD-44E2A208A249|请求ID。|

## 示例 {#section_zmh_wnf_vdb .section}

**请求示例**

```
https://cdn.aliyuncs.com?Action=ModifyDomainCustomLogConfig&DomainName=xxx&ConfigId=xxx&公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "RequestId":"94E3559F-7B6A-4A5E-AFFD-44E2A208A249"
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



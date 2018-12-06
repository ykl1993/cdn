# ModifyCdnDomain {#reference_xl4_xcy_5db .reference}

修改加速域名，目前支持修改源站。

限制条件：

-   创建加速域名之前, 必须先开通CDN服务。
-   加速域名必须已备案完成。

## 请求参数 {#section_xhz_fdy_5db .section}

|参数|类型|是否必选|示例值|描述|
|:-|:-|:---|:--|:-|
|Action|String|是|ModifyCdnDomain| 系统规定参数。取值：

 ModifyCdnDomain

 |
|DomainName|String|是|www.yourdomain.com| 接入CDN的域名。

 |
|Priorities|String|否|20| 源站地址对应的优先级。

 多个源站时，用逗号分隔。

 默认值：20

 |
|ResourceGroupId|String|否|abcdabcd| 资源组ID。

 |
|SourcePort|Integer|否|80| 回源端口。

 |
|SourceType|String|否|domain| 源站类型。取值：

-   ipaddr：IP源站
-   domain：域名源站
-   oss：OSS Bucket为源站（内部common：公共源）

**说明：** 若选择了直播流媒体加速的业务类型，无需填写源站类型和信息。

 |
|Sources|String|否|yourdomain.com| 回源地址，可以是IP或域名。

-   IP或域名支持最多20个，以逗号区分。
-   IP与域名不能同时输入。
-   除了业务类型为直播流媒体加速无需输入源站地址外，其他业务类型源站地址必填（内部用户，类型为common公有源，可以填写类型枚举值）。

 |
|TopLevelDomain|String|否|your.top.domain.com| 顶级接入域，只有白名单用户CDN\_TOP\_LEVEL\_DOMAIN\_GREY\_USER\_LIST设置才有效。

 |

## 返回参数 {#section_zx1_qjy_5db .section}

|参数|类型|示例值|描述|
|:-|:-|:--|:-|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|请求ID|

## 示例 {#section_idd_vjy_5db .section}

**请求示例**

```
http://cdn.aliyuncs.com?Action=ModifyCdnDomain&SourceType=domain&DomainName=test.com&Sources=test.com&公共请求参数
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



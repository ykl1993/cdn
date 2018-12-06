# AddCdnDomain {#reference_zyj_bw1_5db .reference}

添加加速域名时，您一次只能提交一个加速域名。您最多可以添加20个域名。

限制条件：

-   创建加速域名之前，请先开通CDN服务。
-   您的加速域名必须完成备案。
-   如果您的源站内容不在阿里云平台上，则需要审核。审核会在下一工作日前完成。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|示例值|描述|
|:-|:-|:---|:--|:-|
|Action|String|是|AddCdnDomain| 系统规定参数。取值：

 AddCdnDomain

 |
|CdnType|String|是|web| 加速域名的业务类型。取值范围：

-   web：图片及小文件分发。
-   download：大文件下载加速。
-   video：视音频点播加速。
-   liveStream：直播流媒体加速。

 |
|DomainName|String|是|www.yourdomain.com| 需要接入CDN的域名。支持泛域名，以符号“.”开头，如：.a.com。

 |
|CheckUrl|String|否|www.yourdomain.com/test.html| 源站健康检查。

 |
|LiveType|String|否|liveEdge| 直播边缘推流。

 |
|OwnerAccount|String|否|your OwnerAccount| 您的账户。

 |
|Priorities|String|否|20| 优先级，用逗号分隔，个数与Sources保持一致。

 |
|Region|String|否|cn-shanghai| 直播域名单元化信息。

 |
|ResourceGroupId|String|否|your resourceGroupId| 资源组ID。

 |
|Scope|String|否|domestic| 取值范围：

-   domestic
-   overseas
-   global

默认值：domestic。国际用户、国内L3及以上用户设置有效。

 |
|SourcePort|String|否|80| 可以指定443或80。 默认值：80。

 443走https回源。oss不支持443。

 |
|SourceType|String|否|domain| 源站类型。取值范围：

-   ipaddr：IP源站。
-   domain：域名源站。
-   oss：OSS Bucket为源站。

**说明：** 如果您选择了直播流媒体加速的业务类型，则无需填写源站类型和信息。

 |
|Sources|String|否|www.yourdomain.com| 回源地址，可以是IP或域名。

 -   IP支持最多10个，以逗号区分。
-   域名只能输入一个，IP与域名不能同时输入。
-   除了业务类型为直播流媒体加速无需输入源站地址外，其他业务类型源站地址必填（内部用户，类型为common公有源，可以填写类型枚举值）。

 |
|TopLevelDomain|String|否|www.yourTopLevelDomain| 顶级调度域。

 |

## 返回参数 {#section_hdn_f2c_5db .section}

|名称|类型|示例值|描述|
|:-|:-|:--|:-|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8| RequestId

 |

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
1. http://cdn.aliyuncs.com?Action=AddCdnDomain&CdnType=web&SourceType=domain&DomainName=test.com&Sources=test.com&<公共请求参数>
```

**正常返回示例**

-   JSON格式

    ```
    { 
         "RequestId":"15C66C7B-671A-4297-9187-2C4477247A74"
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



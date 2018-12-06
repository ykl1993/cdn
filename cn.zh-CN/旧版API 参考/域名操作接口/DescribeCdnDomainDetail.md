# DescribeCdnDomainDetail {#reference_crt_dny_5db .reference}

获取指定加速域名配置的基本信息。

## 请求参数 {#section_cqh_sny_5db .section}

|参数|类型|是否必选|示例值|描述|
|:-|:-|:---|:--|:-|
|Action|String|是|DescribeCdnDomainDetail| 系统规定参数。取值：

 DescribeCdnDomainDetail

 |
|DomainName|String|是|www.yourdomain.com| 域名。

 |

## 返回参数 {#section_rkq_d4y_5db .section}

|参数|类型|示例值|描述|
|:-|:-|:--|:-|
|RequestId|String|15C66C7B-671A-4297-9187-2C4477247A74| requestid。

 |
|GetDomainDetailModel| | | 域名详情。

 |
|└GmtCreated|String|2015-06-25T03:30:50Z| 创建时间。

 |
|└GmtModified|String|2017-06-25T03:30:50Z| 最近修改时间。

 |
|└SourceType|String|domain| 源站类型。取值含义：

-   ipaddr表示IP源站
-   domain表示域名源站
-   oss表示指定OSS Bucket为源站

 |
|└DomainStatus|String|online| 域名状态。

 |
|└SourcePort|Integer|80| 回源端口号。

 |
|└CdnType|String|web| 加速域名的业务类型。取值含义：

-   web表示图片及小文件加速 速
-   download表示大文件下载加速
-   video表示视音频点播加速
-   liveStream表示直播流体加速媒

 |
|└Cname|String|domain.w.alikunlun.net| 为加速域名生成的一个CNAME域名，需要在域名解析服务商处将加速域名CNAME解析到该域名。

 |
|└HttpsCname|String|yourdomain.com.alikunlun.com| 开启https的CNAME域名。

 |
|└DomainName|String|yourdomain.com| 域名。

 |
|└Description|String|直播域名| 备注。

 |
|└ServerCertificateStatus|String|on| 是否开启ssl证书。

-   on表示开启
-   off表示关闭

 |
|└ServerCertificate|String|——-BEGIN CERTIFICATE——-\\nMIxxxxxxxxx8LDVT2o=\\n——-END CERTIFICATE——-| 如果开启，此处为证书公钥。

 |
|└Region|String|cn-hangzhou| 直播域名单元化信息。

 |
|└Scope|String|domestic| 区域。

 |
|└CertificateName|String|证书1| 证书名称。

 |
|└ResourceGroupId|String|abcd1234abcd1234| 资源组id。

 |
|└SourceModels| | | 源站信息。

 |
|└Content|String|test.com| 回源地址。

 |
|└Type|String|domain| 源站类型。取值：

-   ipaddr：IP源站
-   domain：域名源站
-   oss：OSS Bucket为源站

 |
|└Port|Integer|80| 端口，支持443和80。

 |
|└Enabled|String|online| 状态。

 |
|└Priority|String|20| 优先级。

 |
|└Sources|String|源站信息。| \{ "Source": \[ "yourdomain.com" \] \}

 |

## 示例 {#section_qbz_lqy_5db .section}

**请求示例**

```
http://cdn.aliyuncs.com?Action=DescribeCdnDomainDetail&公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "GetDomainDetailModel":{
            "CdnType":"web",
            "Cname":"bb.test.com.w.kunlunle.com",
            "DomainName":"bb.test.com",
            "DomainStatus":"online",
            "GmtCreated":"2015-06-25T03:30:50Z",
            "GmtModified":"2015-06-25T03:30:53Z",
            "HttpsCname":"bb-test-com.alikunlun.com",
            "Region":"huadong",
            "ResourceGroupId":"abcd1234abcd1234",
            "SourceModels":{
                "SourceModel":[{
                    "Content":"test.com",
                    "Enabled":"online",
                    "Port":80,
                    "Priority":"20",
                    "Type":"domain"
                }]
            },
            "SourceType":"domain",
            "Sources":{
                "Source":["test.com"]
            }
        },
        "RequestId":"18CF38AA-1275-451D-A12B-4EC0BF1C5E30"
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



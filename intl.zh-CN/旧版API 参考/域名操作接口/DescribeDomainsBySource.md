# DescribeDomainsBySource {#reference_hpj_gty_5db .reference}

查询用户名下，源站对应的所有域名名称列表。不支持模糊匹配。支持多个源站查询，源站用逗号隔开。

## 请求参数 {#section_aqw_lty_5db .section}

|参数|类型|是否必选|**示例值**|**描述**|
|:-|:-|:---|:------|:-----|
|Action|String|是|DescribeDomainsBySource| 系统规定参数。取值：

 DescribeDomainsBySource

 |
|Sources|String|是|aaa.source.com| 源站，多个源站用逗号隔开。

 |

## 返回参数 {#section_gp2_vty_5db .section}

|参数|类型|示例值|描述|
|:-|:-|:--|:-|
|RequestId|String|B0F074E5-A1AC-4B32-8EA2-6F450410D1E0| 请求ID。

 |
|Sources|String|aaa.source.com,b.source.com| 请求的源站。

 |
|DomainsList| | | 由DomainsData组成的数组格式，返回各个源站对应的域名名称列表。

 |
|└Source|String|b.source.com| 请求的一个源站。

 |
|└Domains|String|b1.com| 由domainNames组成的list格式，返回单个域名对应的域名名称列表。

 |
|└DomainInfos| | | 由domainInfo组成的list格式，返回域名的详细信息。

 |
|  └DomainName|String|b1.com| 域名。

 |
|└Status|String|online| 域名状态。

 |
|└CreateTime|String|2016-07-12T11:53:19+08:00| 创建时间。

 |
|└UpdateTime|String|2017-03-31T04:49:00+08:00| 更新时间。

 |
|└DomainCname|String|b1.com.w.alikunlun.com| CNAME。

 |

## 示例 {#section_zvg_45y_5db .section}

**请求示例**

```
https://cdn.aliyuncs.com?&Action=DescribeDomainsBySource&Sources=aaa.source.com,b.source.com&公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "DomainsList":{
            "DomainsData":[
                {
                    "DomainInfos":{
                        "domainInfo":[{
                            "CreateTime":"2016-07-12T11:53:19+08:00",
                            "DomainCname":"a1.w.kunlunar.com",
                            "DomainName":"a1.com",
                            "Status":"online",
                            "UpdateTime":"2017-03-31T04:49:00+08:00"
                        }]
                    },
                    "Domains":{
                        "domainNames":["a1.com"]
                    },
                    "Source":"aaa.source.com"
                },
                {
                    "DomainInfos":{
                        "domainInfo":[{
                            "CreateTime":"2017-01-13T18:01:00+08:00",
                            "DomainCname":"b1.com.w.alikunlun.com",
                            "DomainName":"b1.com",
                            "Status":"online",
                            "UpdateTime":"2017-01-17T21:16:16+08:00"
                        }]
                    },
                    "Domains":{
                        "domainNames":["b1.com"]
                    },
                    "Source":"b.source.com"
                }
            ]
        },
        "RequestId":"B0F074E5-A1AC-4B32-8EA2-6F450410D1E0",
        "Sources":"aaa.source.com,b.source.com"
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



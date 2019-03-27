# DescribeDomainsBySource {#reference3301 .reference}

查询用户名下，源站对应的所有域名名称列表。不支持模糊匹配。

支持多个源站查询，源站用逗号分隔。

## 请求参数 { .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeDomainsBySource|
|Sources|String|是|源站，多个源站用逗号隔开。|

## 返回参数 { .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID|
|Sources|String|请求的源站|
|DomainsList|DomainsData\[\]|由DomainsData组成的数组格式，返回各个源站对应的域名名称列表。|

## 数据类型DomainsData { .section}

|名称|类型|描述|
|:-|:-|:-|
|Source|String|请求的一个源站|
|Domains|domainNames\[\]|由domainNames组成的list格式，返回单个域名对应的域名名称列表。|
|DomainInfos|domainInfo\[\]|由domainInfo组成的list格式，返回域名的详细信息。|

## 数据类型domainNames { .section}

|名称|类型|描述|
|:-|:-|:-|
|domainNames|String|请求的这个源站对应的域名名称列表|

## 数据类型domainInfo { .section}

|名称|类型|描述|
|:-|:-|:-|
|DomainName|String|域名|
|Status|String|域名状态|
|CreateTime|String|创建时间|
|UpdateTime|String|更新时间|
|DomainCname|String|Cname|

## 示例 { .section}

请求示例

```
https://cdn.aliyuncs.com?&Action=DescribeDomainsBySource&Sources=exampleaaa.source.com,exampleb.source.com&<公共请求参数>

```

返回示例

JSON格式：

```language-json

{
    "DomainsList": {
        "DomainsData": [
            {
                "Source": "exampleaaa.source.com",
                "Domains": {
                    "domainNames": [
                        "examplea1.com"
                    ]
                },
                "DomainInfos": {
                    "domainInfo": [
                        {
                            "DomainCname": "examplea1.w.kunlunar.com",
                            "Status": "online",
                            "CreateTime": "2016-07-12T11:53:19+08:00",
                            "UpdateTime": "2017-03-31T04:49:00+08:00",
                            "DomainName": "examplea1.com"
                        }
                    ]
                }
            },
            {
                "Source": "exampleb.source.com",
                "Domains": {
                    "domainNames": [
                        "exampleb1.com"
                    ]
                },
                "DomainInfos": {
                    "domainInfo": [
                        {
                            "DomainCname": "exampleb1.com.w.alikunlun.com",
                            "Status": "online",
                            "CreateTime": "2017-01-13T18:01:00+08:00",
                            "UpdateTime": "2017-01-17T21:16:16+08:00",
                            "DomainName": "exampleb1.com"
                        }
                    ]
                }
            }
        ]
    },
    "RequestId": "B0F074E5-A1AC-4B32-8EA2-6F450410D1E0",
    "Sources": "exampleaaa.source.com,exampleb.source.com"
}

```

## 错误码 { .section}

公共错误码参见 [附录](../../../../../cn.zh-CN/旧版API参考/附录.md)。

|错误代码|错误信息|HTTP 状态码|描述|
|:---|:---|:-------|:-|
|MissingParameter|The parameter Sources miss.|400|没有传Sources参数|
|InvalidSources.Malformed|Specified Sources is malformed.|400|输入的Sources参数值不支持|


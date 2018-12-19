# DescribeCdnCertificateList {#reference1754 .reference}

获取证书列表信息。

## 请求参数 { .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeCdnCertificateList|
|DomainName|String|否|域名|

## 返回参数 { .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|RequestId|
|CertificateListModel|CertificateListModel类型|证书id|

## 数据类型CertificateListModel { .section}

|名称|类型|描述|
|:-|:-|:-|
|Count|Integer|证书个数|
|CertList|Cert|证书列表信息|

## 数据类型Cert { .section}

|名称|类型|描述|
|:-|:-|:-|
|CertName|String|证书名称|
|CertId|Long|证书id|
|Fingerprint|String| |
|Common|String| |
|Issuer|String|证书发行商|
|LastTime|Long|时间|

## 示例 { .section}

请求示例：

```
http://cdn.aliyuncs.com?Action=DescribeCdnCertificateList&DomainName=xxx&<公共请求参数>

```

返回示例：

JSON格式

```language-json
{
    "CertificateListModel": {
        "Count": 2,
        "CertList": {
            "Cert": [
                {
                    "CertName": "证书1",
                    "Issuer": "xxx",
                    "LastTime": 1512388610,
                    "CertId": xxx,
                    "Common": "test",
                    "Fingerprint": "xxx"
                },
                {
                    "CertName": "证书2",
                    "Issuer": "xxx",
                    "LastTime": 1512388659,
                    "CertId": xxx,
                    "Common": "test",
                    "Fingerprint": "xxx"
                }
            ]
        }
    },
    "RequestId": "FC0E34AC-0239-44A7-AB0E-800DE522C8DA"
}

```


# DescribeL2VipsByDomain {#reference1049 .reference}

按域名查询L2节点的回源IP。

**说明：** 

-   支持日峰值带宽为 1Gbps 以上的用户提工单申请该接口的调用权限。单击[立即申请](https://workorder.console.aliyun.com/console.htm?lang=#/ticket/add?productCode=cdn)。
-   使用场景介绍，参见 [CDN的回源地址有哪些？](../../../../../intl.zh-CN/.md)

## 请求参数 { .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数，取值：DescribeL2VipsByDomain|
|DomainName|String|是|域名，取值范围： 只支持单个域名。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|DomainName|String|域名|
|Vips|Vip\[\]|Vip列表|

## 示例 { .section}

请求示例

```
https://cdn.aliyuncs.com?Action=DescribeL2VipsByDomain&DomainName=example.com&<公共请求参数>
```

返回示例

```language-json
{
  "Vips": {
    "Vip": [
      "111.111.111.111/25",
      "112.112.112.112/25",
      "122.72.33.190/25",
      "119.14.96.109/25",
      "221.13.20.226/25",
      "124.95.19.140/25",
      "58.211.215.140/25"
    ]
  },
  "RequestId": "820E7900-5CA9-4AEF-B0DD-20ED5F64BE55",
  "DomainName": "example.com"
}

```

## 错误码 { .section}

|错误代码|错误信息|HTTP 状态码|描述|
|----|----|--------|--|
|MissingParameter|The specified value of parameter "DomainName" can not be empty.|400|参数DomainName不能为空|


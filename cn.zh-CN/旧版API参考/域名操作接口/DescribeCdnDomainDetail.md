# DescribeCdnDomainDetail {#doc_api_Cdn_DescribeCdnDomainDetail .reference}

调用DescribeCdnDomainDetail接口获取指定加速域名配置的基本信息。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Cdn&api=DescribeCdnDomainDetail)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeCdnDomainDetail|操作接口名，系统规定参数。取值：**DescribeCdnDomainDetail**。

 |
|DomainName|String|是|www.yourdomain.com|域名

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|GetDomainDetailModel| | |域名详情

 |
|└CdnType|String|web|加速域名的业务类型 。取值：

 -   **web**：图片及小文件加速
-   **download**：大文件下载加速
-   **video**：视音频点播加速
-   **liveStream**：直播流媒体加速

 |
|└CertificateName|String|证书1|证书名称

 |
|└Cname|String|domain.w.alikunlun.net|为加速域名生成的一个CNAME域名，需要在域名解析服务商处将加速域名CNAME解析到该域名。

 |
|└Description|String|直播域名|备注

 |
|└DomainName|String|yourdomain.com|域名

 |
|└DomainStatus|String|online|域名状态

 |
|└GmtCreated|String|2015-06-25T03:30:50Z|创建时间

 |
|└GmtModified|String|2017-06-25T03:30:50Z|最近修改时间

 |
|└HttpsCname|String|yourdomain.com.alikunlun.com|开启https的CNAME域名

 |
|└Region|String|cn-hangzhou|直播域名单元化信息

 |
|└ResourceGroupId|String|abcd1234abcd1234|资源组id

 |
|└Scope|String|domestic|区域

 |
|└ServerCertificate|String|-----BEGIN CERTIFICATE-----\\nMIxxxxxxxxx8LDVT2o=\\n-----END CERTIFICATE-----|如果开启，此处为证书公钥。

 |
|└ServerCertificateStatus|String|on|是否开启SSL证书。

 -   **on**：开启
-   **off**：关闭

 |
|└SourceModels| | |源站信息

 |
|└Content|String|test.com|回源地址

 |
|└Enabled|String|online|状态

 |
|└Port|Integer|80|端口，支持443和80。

 |
|└Priority|String|20|优先级

 |
|└Type|String|domain|源站类型。取值范围：

 -   **ipaddr：IP**源站
-   **domain**：域名源站
-   **oss**：OSS Bucket为源站

 |
|└SourcePort|Integer|80|回源端口号

 |
|└SourceType|String|domain|源站类型。取值：

 -   **ipaddr**：IP源站
-   **domain**：域名源站
-   **oss**：指定OSS Bucket为源站

 |
|└Sources| |源站信息|\{

 "Source": "yourdomain.com"

 \}

 |
|RequestId|String|15C66C7B-671A-4297-9187-2C4477247A74|请求ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://cdn.aliyuncs.com?Action=DescribeCdnDomainDetail
&DomainName=www.yourdomain.com
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<APINAMEResponse>
  <RequestId>28FB897D-4081-4AE7-8D19-0B8A09F0726D</RequestId>
  <HostId>cdn.aliyuncs.com</HostId>
  <Code>InvalidDomain.NotFound</Code>
  <Message>The domain provided does not belong to you.</Message>
</APINAMEResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Message":"The domain provided does not belong to you.",
	"RequestId":"28FB897D-4081-4AE7-8D19-0B8A09F0726D",
	"HostId":"cdn.aliyuncs.com",
	"Code":"InvalidDomain.NotFound"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidParameter|Describe live region parameters have error.|查询直播区域参数异常。|
|400|NotExist|Not find the certificate info.|证书不存在。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Cdn)


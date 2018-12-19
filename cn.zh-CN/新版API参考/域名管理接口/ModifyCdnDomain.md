# ModifyCdnDomain {#reference2756 .reference}

修改加速域名。

**说明：** 创建加速域名之前，必须先开通CDN服务。

## 请求参数 { .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|操作接口名，系统规定参数。取值：ModifyCdnDomain。|
|DomainName|String|是|需要接入CDN的域名。|
|Sources|Json|否|回源地址列表。|
|ResourceGroupId|String|否|资源组id。|
|TopLevelDomain|String|否|顶级接入域。|

## Sources格式 { .section}

\[\{“content”:”1.1.1.1”,”type”:”ipaddr”,””:”20”,”port”:80,”weight”:”15”\}\]

## Sources各字段含义 { .section}

|参数|类型|是否必须|描述|
|:-|:-|:---|:-|
|type|String|是|源站类型 。取值：-   ipaddr：IP源站
-   domain：域名源站
-   oss：OSS Bucket为源站

|
|content|String|是|回源地址。可以是IP或域名。|
|port|Integer|否|可以指定443或80。默认值：80。443走https回源或自定义端口。|
|priority|String|否|源站地址对应的优先级。默认值：20。|
|weight|String|否|回源权重。默认值：10。|

## 返回参数 {#section_qz2_j1g_cgb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestID|String|该条任务请求ID。|

## 示例 { .section}

请求示例：

```
http://cdn.aliyuncs.com?Action=ModifyCdnDomain&SourceType=domain&DomainName=example.com&Sources=[{"content":"1.1.1.1","type":"ipaddr","priority":"20","port":80}]&<公共请求参数>


```

返回示例：

JSON格式：

```
{
  "RequestId": "15C66C7B-671A-4297-9187-2C4477247A74"
}
```

## 错误码 { .section}

公共错误码参见 [附录](../../../../intl.zh-CN/旧版API参考/附录.md)。

|错误代码|错误信息|HTTP 状态码|描述|
|:---|:---|:-------|:-|
|InvalidDomainName.Malformed|Specified DomainName is malformed.|400|DomainName 参数错误。|
|InvalidSource.Content.Malformed|Specified source content is malformed.|400|回源地址参数错误。|
|InvalidSource.Type.Malformed|Specified source type is malformed.|400|源站类型参数错误。|
|InvalidTypeContent.Mismatch|Specified source type does not math the specified source content.|400|回源地址与回源类型不匹配。|
|InvalidSource.Priority.Malformed|Specified source priority is malformed.|400|优先级参数错误。|
|InvalidScope.Malformed|Specified Scope is malformed.|400|Scope 参数错误。|
|IllegalOperation|Illegal domain operate is not permitted.|403|没有权限执行当前操作。|
|InvalidDomain.NotFound|The domain provided does not belong to you.|404|域名不存在或不属于当前用户。|
|Abs.resourceGroupId.Malformed|Specified ResourceGroupId is malformed.|400|资源组id参数不正确。|
|EntityNotExists.ResourceGroup|The resource group does not exist.|400|资源组不存在。|
|InvalidStatus.ResourceGroup|It's now allowed to do this operation because of the current status of resource-group.|400|资源组状态检查失败。|


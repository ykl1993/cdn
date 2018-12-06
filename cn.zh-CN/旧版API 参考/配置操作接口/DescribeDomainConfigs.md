# DescribeDomainConfigs {#reference_vfx_sb2_vdb .reference}

获取指定加速域名的配置。

## 请求参数 {#section_o45_zrf_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|DescribeDomainConfigs|系统规定参数。取值：DescribeDomainConfigs|
|DomainName|String|是|test.test.com|需要接入CDN的域名。|
|ConfigList|String|否|cache\_expired|需要查询的配置，多个配置用逗号（半角）分隔，当前支持cache\_expired、cc、error\_page、http\_header、optimize、page\_compress、ignore\_query\_string、range、referer、req\_auth、src\_host、video\_seek、waf、 notify\_url、redirect\_type 配置；不填代表查询所有。|

## 返回参数 {#section_tc5_ksf_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|67E027D8-7A58-4599-B17A-63E9A54FC54F|请求ID。|
|DomainConfigs| | |对应的配置数据。|
|  └CacheExpiredConfigs| | |文件、路径过期时间设置。|
|    └ConfigId|String|604991|配置ID。|
|    └CacheType|String|suffix|suffix/path。|
|    └CacheContent|String|jpeg|文件类型/路径。|
|    └TTL|String|1000| cache时间。

 单位：秒。

 |
|    └Weight|String|1|SeqID。|
|    └Status|String|success|配置状态。|
|  └HttpErrorPageConfigs| | |错误页面重定向。|
|    └ConfigId|String|23|配置ID。|
|    └ErrorCode|String|501|错误码。|
|    └PageUrl|String| |重定向页面。|
|    └Status|String|success|配置状态。|
|  └HttpHeaderConfigs| | |设置响应头（浏览器端可见）。|
|    └ConfigId|String|602016|配置ID。|
|    └HeaderKey|String|content-type|应答头支持参数任何内容。|
|    └HeaderValue|String|application|应答头内容支持参数任何内容，删除头请填写null。|
|    └Status|String|success|配置状态。|
|  └DynamicConfigs| | |全站加速配置。|
|    └ConfigId|String|20|配置ID。|
|    └DynamicOrigin|String|http|回源路由 scheme。|
|    └StaticType|String|jpg| 文件后缀名完全匹配配置内容时关闭动态加速，多个用空格隔开。

 示例：.jpg .txt .html。

 |
|    └StaticUri|String|yyy/ggss/ccc/a.txt| URI和配置内容完全匹配时关闭动态加速，多个用空格隔开。

 示例： /1/2/3.jpg /a/b/4.js。

 |
|    └StaticPath|String|/to/no\_dynamic\_rou| URI为和配置内容正则匹配正确时关闭动态加速，多个用空格隔开，完全匹配\(^配置内容$\)，如需要彻底关闭动态加速可用"/*"或"*"。

 示例： /1.py。

 |
|    └DynamicCacheControl|String|no-cache| Cache-Control内容匹配配置中任一规则强制开启动态加速，不再检查其余配置。

 样例：no-cache no-store。

 |
|    └Status|String|success|配置状态。|
|  └ReqHeaderConfigs| | |修改回源自定义头。|
|    └ConfigId|String|123|配置ID。|
|    └Key|String|testKey|回源头。|
|    └Value|String|testValue|回源头内容，删除头请填写null。|
|    └Status|String|success|配置状态。|
|  └SetVarsConfigs| | |变量设置。|
|    └ConfigId|String|4125719|配置ID。|
|    └VarName|String|typeb|已存在的nginx可写变量。|
|    └VarValue|String|typeb|变量值，可引用其他变量。|
|    └Status|String|success|配置状态。|
|  └CcConfig| | |防cc攻击。|
|    └ConfigId|String|123|配置ID。|
|    └Enable|String|on|开启或关闭防CC攻击。|
|    └AllowIps|String|1.2.3.4|TMD免拦截。|
|    └BlockIps|String|3.4.5.6|IP黑名单。|
|    └Status|String|success|配置状态。|
|  └ErrorPageConfig| | |错误页面重定向。|
|    └ConfigId|String|123|配置ID。|
|    └ErrorCode|String|404|错误码。|
|    └PageType|String|charity|类型。|
|    └CustomPageUrl|String|[http://promotion.alicdn.com/help/oss/error.html](http://promotion.alicdn.com/help/oss/error.html)|重定向页面。|
|    └Status|String|success|配置状态。|
|  └OptimizeConfig| | |页面优化加速。|
|    └ConfigId|String|123123|配置ID。|
|    └Enable|String|off|开关。|
|    └Status|String|success|配置状态。|
|  └PageCompressConfig| | |页面Gzip优化。|
|    └ConfigId|String|123|配置ID。|
|    └Enable|String|off|开关。|
|    └Status|String|success|配置状态。|
|  └IgnoreQueryStringConfig| | |忽略URL参数\(保留\)。|
|    └ConfigId|String|123|配置ID。|
|    └HashKeyArgs|String|time|缓存hashkey保留的参数列表，多个用逗号分隔，内容只允许是64位的10个元素。|
|    └Enable|String|on|缓存hashkey忽略所有参数。|
|    └Status|String|success|配置状态。|
|  └RangeConfig| | |Range请求功能。|
|    └ConfigId|String|123|配置ID。|
|    └Enable|String|on|开关。|
|    └Status|String|success|配置状态。|
|  └RefererConfig| | |Referer黑白名单设置。|
|    └ConfigId|String|123|配置ID。|
|    └ReferType|String|block|refer类型|
|    └ReferList|String|www.aliyun.com| refer域名，多个域名用逗号隔开，前后不能包含“.” ；后缀匹配。

 示例：sina.com 匹配www.sina.com,www.ch.sina.com

 |
|    └AllowEmpty|String|on|允许空refer进入。|
|    └DisableAst|String|test|关闭域名前的. ，使用精确匹配。|
|    └Status|String|success|配置状态。|
|  └ReqAuthConfig| | |阿里鉴权。|
|    └ConfigId|String|123|配置ID。|
|    └AuthType|String|type\_c|类型。|
|    └Key1|String|vadfawerq|鉴权keyA。|
|    └Key2|String|Acbdert|鉴权keyB。|
|    └Status|String|success|配置状态。|
|    └AliAuthWhiteList|String|test|鉴权白名单。|
|    └AuthM3u8|String|on|开启m3u8内容改写功能：\(on|off\)。|
|    └AuthAddr|String|[http://test.com/test](http://test.com/test)|远程验证服务器地址URL。|
|    └AuthRemoteDesc|String|test|模式字符串。|
|    └TimeOut|String|2400|自定义鉴权缓冲时间。|
|  └SrcHostConfig| | |修改回源Host头。|
|    └ConfigId|String|123|配置ID。|
|    └DomainName|String|www.aliyun.com|回源Host头内容。|
|    └Status|String|success|配置状态。|
|  └VideoSeekConfig| | |视频切片拖拽开关。|
|    └ConfigId|String|123|配置ID。|
|    └Enable|String|on|开关。|
|    └Status|String|success|配置状态。|
|  └WafConfig| | |防跨站注入攻击。|
|    └ConfigId|String|123|配置ID。|
|    └Enable|String|off|开关。|
|    └Status|String|success|配置状态。|
|  └NotifyUrlConfig| | |直播。|
|    └Enable|String|on|开关。|
|    └NotifyUrl|String|[http://test.com](http://test.com/)|URL。|
|  └RedirectTypeConfig| | |强制HTTP/HTTPS跳转。|
|    └RedirectType|String|Https|强制跳转。|
|  └ForwardSchemeConfig| | |swift自适应回源。|
|    └ConfigId|String|123|配置ID。|
|    └Enable|String|on|开关。|
|    └SchemeOrigin|String|http|回源站协议 \(http|https|follow\)。|
|    └SchemeOriginPort|String|80|回源站协议端口 \(80|443|80:443\)。|
|    └Status|String|success1|配置状态。|
|  └RemoveQueryStringConfig| | |忽略URL参数\(删除\)。|
|    └AliRemoveArgs|String|time|删除指定的参数，多个参数之间用空格隔开，剩余参数将作为hashkey中URL args部分。|
|    └ConfigId|String|1123|配置ID。|
|    └Status|String|success|配置状态。|
|  └L2OssKeyConfig| | |L2 OSS 回源私钥。|
|    └PrivateOssAuth|String|on|是否开启私有oss鉴权功能。|
|    └ConfigId|String|3512607|配置ID。|
|    └Status|String|success|配置状态。|
|  └MacServiceConfig| | |移动加速。|
|    └AppList|String|app,app2|applist。|
|    └Enabled|String|on|开关。|
|    └ProcessResult|String|0| -   0 配置成功
-   1 移动加速SDK配置下发失败
-   2 移动加速调度节点配置失败
-   3 移动加速节点配置失败
-   4 移动加速证书生成失败
-   5 系统错误

 |
|    └ConfigId|String|3605171|配置ID。|
|    └Status|String|success|配置状态。|
|  └GreenManagerConfig| | |图片鉴黄。|
|    └Enabled|String|off|开关。|
|    └ConfigId|String|4047862|配置ID。|
|    └Status|String|success|配置状态。|
|  └HttpsOptionConfig| | |HTTPS基础参数。|
|    └Http2|String|off|http2开关。|
|    └ConfigId|String|3498758|配置ID。|
|    └Status|String|success|配置状态。|
|  └AliBusinessConfig| | |特定用户定制。|
|    └AliBusinessTable|String|abc|模式字符串。|
|    └AliBusinessType|String|typea|业务类型。|
|    └ConfigId|String|4125638|配置ID。|
|    └Status|String|success|配置状态。|
|  └IpAllowListConfig| | |IP白名单。|
|    └ConfigId|String|123|配置ID。|
|    └IpList|String|8.8.8.8|IP列表多个用逗号隔开。|
|    └IpAclXfwd|String|on| -   on优先使用xff头中的
-   off优先使用remote\_addr
-   all同时匹配

 |
|    └Status|String|success|配置状态。|

## 示例 {#section_m4b_h5f_vdb .section}

**请求示例**

```

http://cdn.aliyuncs.com?Action=DescribeDomainConfigs&DomainName=test.com
&ConfigList="cache_expired,cc,page_compress"&公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    
    {
    "DomainConfigs":{
    "AliBusinessConfig":{
    "AliBusinessType":"typea",
    "ConfigId":"4125638",
    "Status":"success"
    },
    "CacheExpiredConfigs":{
    "CacheExpiredConfig":[
    {
    "CacheContent":"jpeg",
    "CacheType":"suffix",
    "ConfigId":"604991",
    "Status":"testing",
    "TTL":"1000",
    "Weight":"1"
    },
    {
    "CacheContent":"jpg,png",
    "CacheType":"suffix",
    "ConfigId":"607216",
    "Status":"testing",
    "TTL":"600",
    "Weight":"99"
    }
    ]
    },
    "CcConfig":{
    "AllowIps":"1.2.3.4",
    "BlockIps":"3.4.5.6",
    "Enable":"on"
    },
    "DynamicConfigs":{
    "DynamicConfig":[{
    "ConfigId":"20",
    "DynamicCacheControl":"no-cache",
    "DynamicOrigin":"http",
    "StaticPath":"/to/no_dynamic_rou",
    "StaticType":"jpg",
    "StaticUri":"yyy/ggss/ccc/a.txt"
    }]
    },
    "ErrorPageConfig":{
    "CustomPageUrl":"http://promotion.alicdn.com/help/oss/error.html",
    "ErrorCode":"404",
    "PageType":"charity"
    },
    "GreenManagerConfig":{
    "ConfigId":"4047862",
    "Enabled":"off",
    "Status":"success"
    },
    "HttpErrorPageConfigs":{
    "HttpErrorPageConfig":[
    {
    "ErrorCode":"404",
    "PageUrl":"http://promotion.alicdn.com/help/oss/error.html"
    },
    {
    "ErrorCode":"501",
    "PageUrl":"http://test.com/501.html"
    },
    {
    "ErrorCode":"502",
    "PageUrl":"http://test.com/502.html"
    }
    ]
    },
    "HttpHeaderConfigs":{
    "HttpHeaderConfig":[
    {
    "ConfigId":"602016",
    "HeaderKey":"content-type",
    "HeaderValue":"application",
    "Status":"success"
    },
    {
    "ConfigId":"608841",
    "HeaderKey":"content-type",
    "HeaderValue":"app",
    "Status":"testing"
    },
    {
    "ConfigId":"602018",
    "HeaderKey":"cache-control",
    "HeaderValue":"application",
    "Status":"success"
    },
    {
    "ConfigId":"602021",
    "HeaderKey":"content-disposition",
    "HeaderValue":"application",
    "Status":"success"
    }
    ]
    },
    "HttpsOptionConfig":{
    "ConfigId":"3498758",
    "Http2":"off",
    "Status":"success"
    },
    "IgnoreQueryStringConfig":{
    "Enable":"on"
    },
    "L2OssKeyConfig":{
    "ConfigId":"3512607",
    "PrivateOssAuth":"on",
    "Status":"success"
    },
    "MacServiceConfig":{
    "AppList":"app,app2",
    "ConfigId":"3605171",
    "Enabled":"on",
    "Status":"success"
    },
    "NotifyUrlConfig":{
    "Enable":"on",
    "NotifyUrl":"http://test.com"
    },
    "OptimizeConfig":{
    "Enable":"off"
    },
    "PageCompressConfig":{
    "Enable":"off"
    },
    "RangeConfig":{
    "Enable":"on"
    },
    "RedirectTypeConfig":{
    "RedirectType":"Https"
    },
    "RefererConfig":{
    "AllowEmpty":"on",
    "ReferList":"www.aliyun.com",
    "ReferType":"block"
    },
    "RemoveQueryStringConfig":{
    "AliRemoveArgs":"time",
    "ConfigId":"1123"
    },
    "ReqAuthConfig":{
    "AuthType":"type_c",
    "Key1":"vadfawerq",
    "Key2":"Acbdert",
    "TimeOut":"2400"
    },
    "ReqHeaderConfigs":{
    "ReqHeaderConfig":[{
    "ConfigId":"123",
    "Key":"testKey",
    "Value":"testValue"
    }]
    },
    "SetVarsConfigs":{
    "SetVarsConfig":[
    {
    "ConfigId":"4125719",
    "Status":"success",
    "VarName":"typeb",
    "VarValue":"typeb"
    },
    {
    "ConfigId":"4125726",
    "Status":"success",
    "VarName":"typea",
    "VarValue":"typea"
    }
    ]
    },
    "SrcHostConfig":{
    "DomainName":"www.aliyun.com"
    },
    "VideoSeekConfig":{
    "Enable":"on"
    },
    "WafConfig":{
    "Enable":"off"
    }
    },
    "RequestId":"67E027D8-7A58-4599-B17A-63E9A54FC54F"
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



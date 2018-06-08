# DescribeDomainConfigs {#reference_vfx_sb2_vdb .reference}

Obtain the configuration of the specified CDN domain name.

## Request parameters {#section_o45_zrf_vdb .section}

|Name|Type|Required|Example values|Description|
|Action|String|Yes|DescribeDomainConfigs|The name of this interface. Value: DescribeDomainConfigs|
|DomainName|String|Yes|test.test.com|CDN domain name to be accessed.|
|ConfigList|String|No|cache\_expired|Configurations to be queried, separated by commas \(half width\). Currently, cache\_expired, cc, error\_page, http\_header, optimize, page\_compress, ignore\_query\_string, range, referer, req\_auth, src\_host, video\_seek, waf, notify\_url, and redirect\_type configurations can be queried. If this parameter is left blank, the system queries all configurations.|

## Return parameters {#section_tc5_ksf_vdb .section}

|Name|Type|Example values|Description|
|RequestId|String|67E027D8-7A58-4599-B17A-63E9A54FC54F|The request ID.|
|DomainConfigs| | |The corresponding configuration data.|
|  └CacheExpiredConfigs| | |File and path expiration configuration.|
|    └ConfigId|String|604991|Configuration ID.|
|    └CacheType|String|suffix|Suffix/path.|
|    └CacheContent|String|jpeg|File type/path.|
|    └TTL|String|1000| Cache time.  

 Unit: seconds.

 |
|    └Weight|String|1|SeqID.|
|    └Status|String|success|Configuration status.|
|  └ Httperrorpageconfigs| | |Error page redirection.|
|    └ConfigId|String|23|Configuration ID.|
|    └ErrorCode|String|501|Error code.|
|    └PageUrl|String|[http://test.com/501.html](http://test.com/501.html)|Redirection page.|
|    └Status|String|success|Configuration status.|
|  └HttpHeaderConfigs| | |Configure response header \(visible at the browser end\).|
|    └ConfigId|String|602016|Configuration ID.|
|    └HeaderKey|String|content-type|Response header supports parameters of any content.|
|    └HeaderValue|String|application|Response header supports parameters of any content, and to delete a header, enter null.|
|    └Status|String|success|Configuration status.|
|  └DynamicConfigs| | |Whole site acceleration configuration.|
|    └ConfigId|String|20|Configuration ID.|
|    └DynamicOrigin|String|http|Source route scheme.|
|    └StaticType|String|jpg| When the file suffix and configuration content completely match, the dynamic acceleration is closed, and suffixes are separated by space.

 Example: .jpg .txt .html.

 |
|    └StaticUri|String|yyy/ggss/ccc/a.txt| When URI and configuration content completely match, the dynamic acceleration is closed, and URIs are separated by space.

 Example: /1/2/3.jpg /a/b/4.js.

 |
|    └StaticPath|String|/to/no\_dynamic\_rou| When URI and configuration content are in regular match, the dynamic acceleration is closed. Regular matches are separated by space, and URIs completely matches \(^configuration content$\). If you want to absolutely close dynamic acceleration, use slash \(/\) or space.  

 Example: /1 .py.

 |
|Hu HU └ dynamiccachecontrol|String|no-cache| When Cache-Control content matches any rules of cofiguration, the dynamic acceleration is opened. And other configuration is not checked.

 Example: no-cache no-store.

 |
|    └Status|String|success|Configuration status.|
|  └ReqHeaderConfigs| | |Modify source custom header.|
|    └ConfigId|String|123|Configuration ID.|
|    └Key|String|testKey|Source header.|
|    └Value|String|testValue|Source header content, and to delete the header, enter null.|
|    └Status|String|success|Configuration status.|
|  └SetVarsConfigs| | |Varible configuration.|
|    └ConfigId|String|4125719|Configuration ID.|
|    └VarName|String|typeb|nginx variable that can be written already exists.|
|    └VarValue|String|typeb|Varible value, which can cite other varible.|
|    └Status|String|success|Configuration status.|
|  └CcConfig| | |Anti-cc attack.|
|    └ConfigId|String|123|Configuration ID.|
|    └Enable|String|on|Open or close anti-CC attack.|
|    └AllowIps|String|1.2.3.4|TMD anti-interception.|
|    └BlockIps|String|3.4.5.6|IP blacklist.|
|    └Status|String|success|Configuration status.|
|  └ErrorPageConfig| | |Error page redirection.|
|    └ConfigId|String|123|Configuration ID.|
|    └ErrorCode|String|404|Error code.|
|    └PageType|String|charity|Type.|
|    └CustomPageUrl|String|[http://promotion.alicdn.com/help/oss/error.html](http://promotion.alicdn.com/help/oss/error.html)|Redirection page.|
|    └Status|String|success|Configuration status.|
|  └OptimizeConfig| | |Page optimization acceleration.|
|    └ConfigId|String|123123|Configuration ID.|
|Hu HU └ Enable|String|off|Switch.|
|    └Status|String|success|Configuration status.|
|  └ Pagecompressconfig| | |Page Gzip optimization.|
|    └ConfigId|String|123|Configuration ID.|
|    └Enable|String|off|Switch.|
|    └Status|String|success|Configuration status.|
|  └ Ignorequerystringconfig| | |Ignore URL parameter \(retain\).|
|    └ConfigId|String|123|Configuration ID.|
|    └HashKeyArgs|String|time|Parameters list retained by Cached hashkey, separated by commas \(,\), and the content only supports 10 elements with 64 bits.|
|    └Enable|String|on|Cashed hashkey ignores all the parameters.|
|    └Status|String|success|Configuration status.|
|"Rangeconfig"| | |Range request function.|
|    └ConfigId|String|123|Configuration ID.|
|    └Enable|String|on|Switch.|
|    └Status|String|success|Configuration status.|
|  └RefererConfig| | |Referer blacklist and whitelist configuration.|
|Hu HU └ ConfigId|String|123|Configuration ID.|
|    └ReferType|String|block|Refer type.|
|    └ReferList|String|www.google.com| Refer domain name, separated by commas \(,\). The front and back ends does not include period \(.\).  Suffix match.

 Example: sina.com matches www.sina.com and www.ch.sina.com

 |
|    └AllowEmpty|String|on|Empty refer is allowed.|
|    └DisableAst|String|test|Close full stop \(.\) before domain name and use exact match.|
|    └Status|String|success|Configuration status.|
|  └ Reqauthconfig| | |Alibaba authentication.|
|    └ConfigId|String|123|Configuration ID.|
|    └AuthType|String|type\_c|Type.|
|    └Key1|String|vadfawerq|Authentication keyA.|
|    └Key2|String|Acbdert|Authentication keyB.|
|    └Status|String|success|Configuration status.|
|    └AliAuthWhiteList|String|test|Authentication whitelist.|
|    └AuthM3u8|String|on|Enable m3u8 content rewriting function: \(on|off\).|
|    └AuthAddr|String|[http://test.com/test](http://test.com/test)|Remote authentication server address URL.|
|    └AuthRemoteDesc|String|test|Module string.|
|    └TimeOut|String|2400|Custom authentication buffer time.|
|  └SrcHostConfig| | |Modify source Host header.|
|    └ConfigId|String|123|Configuration ID.|
|  └DomainName|String|www.aliyun.com|Source Host header content.|
|    └Status|String|success|Configuration status.|
|  └VideoSeekConfig| | |Video slice drag/drop switch.|
|    └ConfigId|String|123|Configuration ID.|
|    └Enable|String|on|Switch.|
|    └Status|String|success|Configuration status.|
|  └WafConfig| | |Anti-cross site scripting attack.|
|    └ConfigId|String|123|Configuration ID.|
|    └Enable|String|off|Switch.|
|    └Status|String|success|Configuration status.|
|  └NotifyUrlConfig| | |Live.|
|    └Enable|String|on|Switch.|
|    └NotifyUrl|String|[http://test.com](http://test.com/)|URL.|
|  └RedirectTypeConfig| | |Forced HTTP/HTTPS jump.|
|    └RedirectType|String|HTTPS|Forced jump.|
|  └ Forwardschemeconfig| | |Swift adaptive source.|
|    └ConfigId|String|123|Configuration ID.|
|    └Enable|String|on|Switch.|
|    └SchemeOrigin|String|http|Source site protocol \(http|https|follow\).|
|    └SchemeOriginPort|String|80.|Source site protocol port \(80|443|80:443\).|
|    └Status|String|success1|Configuration status.|
|  └RemoveQueryStringConfig| | |Ignore URL parameters \(Delete\).|
|    └AliRemoveArgs|String|time|Delete specified parameters. The remaining parameters are separated by space, and are part of URL args in hashkey.|
|    └ConfigId|String|1123|Configuration ID.|
|    └Status|String|success|Configuration status.|
|  └L2OssKeyConfig| | |L2 OSS source private key.|
|    └PrivateOssAuth|String|on|Whether or not to open the private OSS authentication function.|
|    └ConfigId|String|3512607|Configuration ID.|
|    └Status|String|success|Configuration status.|
|  └MacServiceConfig| | |Mobile acceleration.|
|    └AppList|String|app,app2|Applist.|
|    └Enabled|String|on|Switch.|
|    └ProcessResult|String|0| -   0: Configuration succeeds.
-   1: mobile acceleration SDK configuration and submission failed.
-   2: mobile acceleration scheduling node failed.
-   3: mobile acceleration node configuration failed.
-   4: mobile acceleration certificate generation failed.
-   5: system error.

 |
|    └ConfigId|String|3605171|Configuration ID.|
|    └Status|String|success|Configuration status.|
|  └GreenManagerConfig| | |Images porn detection.|
|    └Enabled|String|off|Switch.|
|    └ConfigId|String|4047862|Configuration ID.|
|    └Status|String|success|Configuration status.|
|  └HttpsOptionConfig| | |HTTPS basic parameters.|
|    └Http2|String|off|http2 switch.|
|    └ConfigId|String|3498758|Configuration ID.|
|    └Status|String|success|Configuration status.|
|  └AliBusinessConfig| | |Custom for specific users.|
|    └AliBusinessTable|String|abc|Module string.|
|    └AliBusinessType|String|Typea|Business type.|
|    └ConfigId|String|4125638|Configuration ID.|
|    └Status|String|success|Configuration status.|
|  └IpAllowListConfig| | |IP whitelist.|
|    └ConfigId|String|123|Configuration ID.|
|    └IpList|String|8.8.8.8|Multiple IP lists are separated by comma.|
|Hu HU └ ipaclxfwd|String|on| -   on: preferentially use the ip in xff header.
-   off: preferentially use remote\_addr.
-   all: both match.

 |
|    └Status|String|success|Configuration status.|

## Example {#section_m4b_h5f_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com?Action=DescribeDomainConfigs&DomainName=test.com
&ConfigList="cache_expired,cc,page_compress"&Public request parameter
```

**Normal return example**

-   JSON format

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
    TTL: 1000 ",
    "Weight":"1"
    },
    {
    "CacheContent":"jpg,png",
    "CacheType":"suffix",
    "ConfigId":"607216",
    "Status": "testing ",
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
    "Maid": "No-Cache ",
    "DynamicOrigin":"http",
    "Staticpath": "/to/no_dynamic_rou ",
    "Statictype": "jpg ",
    "StaticUri":"yyy/ggss/ccc/a.txt"
    }]
    },
    "ErrorPageConfig":{
    "CustomPageUrl":"http://promotion.alicdn.com/help/oss/error.html",
    "ErrorCode":"404",
    "PageType":"charity"
    },
    "GreenManagerConfig":{
    "Configid": 4047862 ",
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
    "Status": "success"
    },
    {
    "ConfigId":"608841",
    "HeaderKey":"content-type",
    "Headervalue": "app ",
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
    "Applist": "app, app2 ",
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
    "ReferList":"www.google.com",
    "ReferType":"block"
    },
    "RemoveQueryStringConfig":{
    "AliRemoveArgs":"time",
    "ConfigId":"1123"
    },
    "ReqAuthConfig":{
    "AuthType":"type_c",
    "Key1": "maid ",
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
    "Maid ":{
    "SetVarsConfig":[
    {
    "Configid": 4125719 ",
    "Status":"success",
    "VarName":"typeb",
    "Varvalue": "typeB"
    },
    {
    "Configid": 4125726 ",
    "Status":"success",
    "VarName":"typea",
    "Varvalue": "typea"
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


**Exception return example**

-   JSON format

    ```
    
    {
    "Code":"InternalError",
    "HostId":"cdn.aliyuncs.com",
    "Message":"The request processing has failed due to some unknown error.",
    "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    }
    ```



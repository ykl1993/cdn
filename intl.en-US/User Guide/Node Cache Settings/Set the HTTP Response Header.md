# Set the HTTP Response Header {#concept_qxw_zkd_xdb .concept}

## Introduction {#section_t35_fld_xdb .section}

You can set an HTTP Response Header. Eight HTTP response header parameters are available for customization. The parameters are as follows:

|Parameters|Description|
|:---------|:----------|
|Content-Type|Specifies a content type for the response returned to a client program.|
|Cache-control|Specifies a cache mechanism that is typically following the request/response process of a client program.|
|Content-Disposition|Specifies a default filename for activating the file download setting when a response is returned to a client program.|
|Content-language|Specifies a language in which a response is returned to a client program.|
|Expires|Specifies expiration time for the response returned to a client program.|
|Access-Control-Allow-Origin|Specifies an origin that is allowed to send cross-domain requests.|
|Access-Control-Allow-Methods| Specifies the allowed cross-domain request method.|
|Access-Control-Max-Age| Specifies the cache duration of the returned result for a pre-fetch request initiated by a client program for a particular resource.|
|Access-Control-Expose-Headers|Specify custom header information that is allowed to access|

## Attentions: {#section_lzt_fd2_xdb .section}

-   The HTTP response header setting will affect responses to client programs \(for example, browser\) for all resources under the CDN domain, but will not affect the behavior of the cache server.
-   Only the preceding HTTP header parameters are supported currently. If additional requirements for HTTP header settings are required, please submit a ticket to Alibaba Cloud technical support.
-   Access-Control-Allow-Origin can be set to `*`\(表示全部域名\)\(indicating all domains\) or to a complete domain name such as`www.aliyun.com`. Wildcard domain setting is not supported currently.

## Procedure {#section_kv5_hd2_xdb .section}

1.  CDN domain name overview page, select the domain name to go to the Domain Namespage, set HTTP header.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5149/3423_en-US.png)

2.  Click **Modify**, and you can manage the current http header policy list.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5149/3424_en-US.png)

3.  Click **Add** to add HTTP HEADER custom configurations.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5149/3425_en-US.png)



# Set the HTTP Response Header {#concept_qxw_zkd_xdb .concept}

## Introduction {#section_t35_fld_xdb .section}

HTTP headers \(fields\) are components of the header section of request and response messages in the Hypertext Transfer Protocol \(HTTP\). They define the operating parameters during the HTTP process. HTTP headers can be classified into general headers, request headers, response headers, and so on.

You can set an HTTP Response Header. The following HTTP response header parameters are available for customization:

|Parameters|Description|
|:---------|:----------|
|Content-Type|Specifies the content type of the client program's response object.|
|Cache-control|Specifies the caching policy that the client program is following when requesting and responding.|
|Content-Disposition|Specifies the default file name provided by the client program when it is willing to save the contents accessed by request as a file.|
|Content-language|Specifies the language of the client program's response object.|
|Expires|Specifies the expiration time of the client program's response object.|
|Access-Control-Allow-Origin|Specifies the allowed origin domain of cross-origin requests.|
|Access-Control-Allow-Methods| Specifies the allowed method of cross-origin requests.|
|Access-Control-Max-Age| Specifies the length of time the response result is cached for a pre-fetch request initiated by a client program for a particular resource.|
|Access-Control-Expose-Headers|Specifies the custom header information that is allowed to be accessed.|

## Note {#section_lzt_fd2_xdb .section}

-   The HTTP response header configurations will affect the response actions of all client programs of the resource under the CDN domain name, rather than the actions of the cache server.
-   For now, you can only customize the HTTP header. [Submit a ticket](https://workorder-intl.console.aliyun.com) if you have other custom requirements for HTTP header.
-   You can type in `*` \(indicating all domain names\) or a full domain name \(such as `www.aliyun.com`\) for the Access-Control-Allow-Origin parameter.
-   For now, you cannot set HTTP headers for an extensive domain name.

## Procedure {#section_kv5_hd2_xdb .section}

1.  Log on to the CDN console, then go to the Domain Names page. Choose a domain name, then click **Manage**.
2.  Go to **Caching Configuration** \> **HTTP Header**, then click **Modify** or **Delete** for a parameter. You can also click **Add**, and then choose the parameter and enter value to add a custom HTTP header parameter


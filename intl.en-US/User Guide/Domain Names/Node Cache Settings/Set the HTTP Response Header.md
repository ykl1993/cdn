# Set the HTTP Response Header {#concept_qxw_zkd_xdb .concept}

## Introduction {#section_t35_fld_xdb .section}

HTTP header \(fields\) are components of the header section of request and response messages in the Hypertext Transfer Protocol \(HTTP\). They define the operating parameters during HTTP process.

HTTPS headers can be classified into general headers, request headers, response headers, and so on. You can set HTTP response headers, adding more information on server and Request-URI. 9 types of HTTP response headers are available for option.

You can set an HTTP Response Header. Eight HTTP response header parameters are available for customization. The parameters are as follows:

|Parameters|Description|
|:---------|:----------|
|Content-Type|Specifies the content type of the client program's response object.|
|Cache-control|Specifies the caching policy that the client program is following when requesting and responding.|
|Content-Disposition|Specifies the default file name provided by the client program when it is willing to save the contents accessed by request as a file.|
|Content-language|Specifies the language of the client program's response object.|
|Expires|Specifies the expiration time of the client program's response object.|
|Access-Control-Allow-Origin|Specifies the allowed origin domain of cross-origin requests.|
|Access-Control-Allow-Methods| Specifies the allowed method of cross-origin requests.|
|Access-Control-Max-Age| Specifies the cache duration of the response result for a pre-fetch request initiated by a client program for a particular resource.|
|Access-Control-Expose-Headers|Specifies the custom header information that is allowed to access.|

## Note {#section_lzt_fd2_xdb .section}

-   The configuration of HTTP response header will affect the response actions of all resources' client program under the CDN domain name, rather than the actions of the cache server.
-   You can only customize HTTP header now. [Submit a ticket](https://workorder-intl.console.aliyun.com) if you have other custom requirements for HTTP header.
-   You can type in `*` \(indicating all domain names\) or full domain name \(such as `www.aliyun.com`\) for the parameter Access-Control-Allow-Origin.
-   Setting HTTP headers for an extensive domain name is not available now.

## Procedure {#section_kv5_hd2_xdb .section}

1.  Log on to the CDN console, enter the Domain Names page. Choose a domain name, then click **Manage**.
2.  Click **Modify** or **Delete** on a parameter in **Caching Configuration** \> **HTTP Header**.
3.  You can also click **Add**, and then choose the parameter and enter value to add a custom HTTP header parameter.


# Back-to-source of range {#concept_zrw_s1f_xdb .concept}

## Introduction {#section_prj_v1f_xdb .section}

-   The Back-to-source of Range function allows a client to notify an origin site server to return partial content within a specified range. It accelerates delivery of large files by reducing the consumption of back-to-source traffic and improving the resource response speed.
-   The origin site must support the range request, that is, the range field is included in the HTTP request header, and the origin site can respond to the correct 206 file slice.
-   When the Back-to-source of Range function is enabled, a parameter request can be returned to an origin site.  In this case, based on the Range parameter, the origin site   returns the file byte range.  and the CDN node returns the content in the byte range to the client.

    **Note:** For example, if a request sent from a client to a CDN node contains range:0-100, the range:0-100 parameter will also be contained in the request received on the origin site.  When the origin site returns the parameter content to the CDN node, the node returns the content in 101 bytes ranging from 0 to 100 to the client.

-   When the Back-to-source of Range is disabled, a CDN higher-level node requests an origin site for all files. However, the requested files will not be cached on the CDN node because a client will automatically disconnect HTTP links after receiving bytes specified by Range. This causes a low cache hit rate and large back-to-source traffic.

    **Note:** For example, if a request sent from a client to a CDN node contains range:0-100, the range:0-100 parameter will not be contained in the request received on the server. The origin site will return a complete file to the CDN node and the CDN node will return only 101 bytes to the client. However, the file cannot be cached on the CDN node because the link is disconnected.


## Attentions: {#section_yr2_1bf_xdb .section}

To use the Back-to-source of Range function, an origin site must support Range requests, meaning that the origin site must be able to return correct 206 Partial Content for an HTTP request header containing a Range field.

## Procedure {#section_cxc_bbf_xdb .section}

-   This function is optional and is disabled by default.
-   Configuration change.

Go to the CDN domain name management page, click **Configure**, select **Enable/Disable**Back-to-source of Range function.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5157/3510_en-US.png)


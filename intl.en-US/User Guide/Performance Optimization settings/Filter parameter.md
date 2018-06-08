# Filter parameter {#concept_l2f_zbm_xdb .concept}

## Introduction {#section_qvr_ccm_xdb .section}

-   When a URL request carrying ?  and request parameters are sent to a CDN node, the CDN node determines whether to send the request to the origin site.  If the Filter Parameter function is enabled, after the request arrives at the CDN node, the URL without parameters is intercepted and requested against the origin site.  Additionally, the CDN node retains only one copy.  If the Filter Parameter function is disabled, different copies are cached on the CDN node for different URLs.
-   An HTTP request typically contains the requisite parameters. If the content of a parameter has a low priority and the parameter overview file can be ignored, it recommended to enable the Filter Parameter function. This improves the file cache hit rate and the delivery efficiency.
-   If a parameter has important indicators \(for example, if it contains file version information\), we recommend that you disable this function.

**Note:** Example of use

-   For example, the `http://www.abc.com/a.jpg?x=1` URL request is sent to a CDN node.
-   If the Filter Parameter function is enabled, the CDN node initiates to the origin site the `http://www.abc.com/a.jpg`request \(ignore parameter x = 1\). After the origin site returns a response, the CDN node retains a copy. Then, the origin site continues to respond to the terminal `http://www.abc.com/a.jpg`. For all requests similar to  `http://www.abc.com/a.jpg?parameters`, the origin site responds to the CDN copy  `http://www.abc.com/a.jpg`.
-   If the Filter Parameter function is disabled, different copies are cached on the CDN node for different URLs.  For example: `http://www.abc.com/a.jpg?x=1` and `http://www.abc.com/a.jpg?x=2` respond to the response content of different parameter origin site.

## Attentions: {#section_m3c_qcm_xdb .section}

URL authentication has a higher priority than the Filter Parameter function. Because type A authentication information is contained in the parameter section of an HTTP request, the system first performs the authentication and then caches a copy on the CDN node after the authentication succeeds.

## Procedure {#section_mzs_rcm_xdb .section}

-   Applicable business type: All.

-   Configuration change: In the CDN domain name overview page, go to the Domain Names, select the domain name that you want to set up, and click**Configure**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5161/3729_en-US.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5161/3730_en-US.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5161/3731_en-US.png)



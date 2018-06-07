# Anti-leech {#concept_j3m_zh2_xdb .concept}

## Introduction {#section_v25_g32_xdb .section}

-   The anti-leech function is based on the HTTP referer mechanism where the referer, namely an HTTP header field, is used for source tracking, source recognition and processing. You can configure a referer  black list or whitelist to identify and filter visitors in order to limit access to your CDN resources.
-   Currently, the anti-leech function supports the black list or whitelist mechanism. After a visitor initiates a request for a resource, and the request arrives at a CDN node,  the CDN node filters the identity of the visitor based on the presets of the anti-leech black list or whitelist. If the identity complies with the rules, the visitor can access the requested resource; if the identity does not comply with the rules, the request is forbidden and a 403 response code is returned.

## Attentions: {#section_qxs_h32_xdb .section}

-   This function is optional and is disabled by default.
-   To enable this function, you can select Refer Blacklist or Refer Whitelist to edit. You can only select one of these options to edit.
-   A null Referer field can be used to access resources on a CDN node  \(that is, whether a web browser can use its URL to directly access resources on a target URL\).
-   After configuration, wildcard domain name support is added automatically. For example, if you enter a.com, the final configuration \* .a.com takes effect, and all sub-domain names take effect.

## Procedure {#section_ilp_j32_xdb .section}

Enter the CDN Domain Namespage, select the desired domain name and click **Configure**.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5151/3439_en-US.png)

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5151/3440_en-US.png)

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5151/3441_en-US.png)


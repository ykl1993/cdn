# Anti-leech {#concept_j3m_zh2_xdb .concept}

## Introduction {#section_v25_g32_xdb .section}

-   The anti-leech function is based on the HTTP referer mechanism where the referer, namely an HTTP header field, is used for source tracking, source recognition and processing. You can configure a referer black list or whitelist to identify and filter visitors in order to limit access to your CDN resources.
-   Currently, the anti-leech function supports the black list or whitelist mechanism. After a visitor initiates a request for a resource, and the request arrives at a CDN node, the CDN node filters the identity of the visitor based on the preset configuration of the anti-leech black list or whitelist.
    -   If the identity complies with the rules, the visitor can access the requested resource.
    -   If the identity does not comply with the rules, the request is forbidden and a 403 response code is returned.

## Procedure {#section_ilp_j32_xdb .section}

1.  Go to Domain Namespage, select the domain name, then click **Manage**.
2.  On **Resource Access Control** \> **Anti-leech**, click **Modify**.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5151/15350039337279_en-US.png)
3.  Choose**Blacklist** or **Whitelist**, and add the IP network segment in the box below.
4.  Click **Confirm**.

## Notes {#section_qxs_h32_xdb .section}

-   This function is optional and is disabled by default.
-   You can only select one of Refer Blacklist or Refer Whitelist to edit at the same time.
-   After configuration, wildcard domain name support is added automatically. For example, if you enter `a.com`, all sub-domain names under `*.a.com` take effect.
-   You can set a null Referer field to access resources on a CDN node \(that is, allowing to access the resource URL by typing the address in browser\).


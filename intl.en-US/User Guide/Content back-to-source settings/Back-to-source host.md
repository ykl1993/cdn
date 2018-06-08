# Back-to-source host {#concept_xwl_fdd_xdb .concept}

## Introduction {#section_y4g_hdd_xdb .section}

You can customize a Web server domain name that a CDN node accesses in the back-to-source process.

**Origin site**: the origin site determines which IP the request is returned to during back-to-source.

**Back-to-source host**: The back-to-source host determines which site on the IP to access when the request is returned to source.

-   Example 1: The origin site of the domain name is `www.a.com`, the back-to-source host is `www.b.com`. then the request is returned to the actual IP resolved through `www.a.com`   corresponding to the host site `www.b.com`.
-   Example 2: origin site is IP origin site `1.1.1.1`Back-to-source host is`www.b.com` then the request is actually returned to`www.b.com` of the host corresponding to `1.1.1.1`.

**Note:** Currently, sni back-to-source is not supported.

## Procedure {#section_tyd_5dd_xdb .section}

-   **Back-to-source host** is optional, and default value is:
    -   If the origin site is **IP**, the back-to-source host is CDN domain name by default.
    -   If the origin site is **OSS origin site**, back-to-source host is origin site domain nameby default.
-   The value options includeCDN domain name、origin site domain name and custom domain name.
-   Configuration change: got ot CDNDomain Names, select the desired domain name to go to management page, back-to-source configuration to modify the configuration of the back-to-source host.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13745/3355_en-US.png)



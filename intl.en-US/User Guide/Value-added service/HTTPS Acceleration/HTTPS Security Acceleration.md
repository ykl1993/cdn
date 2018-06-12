# HTTPS Security Acceleration {#concept_rns_qvk_xdb .concept}

## Features {#section_ynt_mnl_xdb .section}

-   HTTPS \(Hyper Text Transfer Protocol over Secure Socket Layer\) is an HTTP channel designed to ensure security, namely, the secure edition of HTTP. It encapsulates HTTP with the SSL/TLS protocol, so the foundation of HTTPS security is SSL/TLS.
-   Advantages of HTTPS acceleration:
    -   Key user information is encrypted during transmission, preventing leakage of sensitive information, such as session IDs or cookies, or other potential safety hazards;
    -   Integrity verification is performed on all data during transmission, protecting the DNS or content from being hijacked, tampered with, or suffering from other “man in the middle” \(MITM\) attacks. For more information, see Using HTTPS to Prevent Traffic Hijacking.
-   Alibaba Cloud CDN provides HTTPS secure acceleration. You only need to enable the secure acceleration mode and then upload the certificate and private key for the CDN domains. The service also supports viewing, disabling, enabling, and editing certificates. An uploaded user-defined only supports certificate in PEM format. For more information, see [Certificate format description and conversion method](intl.en-US/User Guide/Value-added service/HTTPS Acceleration/Certificate Format.md#).
-   You can go to[Alibaba Cloud SSL Certificates Service](https://yundun.console.aliyun.com)to apply for free certificate or buy advanced certificate.
-   If your certificate is configured correctly and enabled, both HTTP access and HTTPS access are supported. If the certificate does not match with the private key or is disabled, only HTTP access is supported.

**Note:** SNI back-to-origin is not supported.

## Function Diagram {#section_pcc_snl_xdb .section}

HTTPS enabled in the Alibaba Cloud CDN console can achieve HTTPS encryption requested between the user and the Alibaba Cloud CDN node. And the CDN node's request which returns to the origin site to obtain the resource is still performed as configured in your origin site. We recommend that you configure and enable HTTPS in your origin site to realize full link HTTPS encryption:

## Attentions: {#section_z5h_xnl_xdb .section}

Configuration

-   **HTTPS Secure Acceleration** is supported for the following business scenarios:
    -   Acceleration of images and small files
    -   Acceleration of large file downloads
    -   Acceleration of on-demand video/audio
    -   Acceleration of live streaming media
    -   Mobile acceleration is not supported.
-   HTTPS security for wildcard domain names is supported.
-   The options to :**Disable**and**Enable**are supported:
    -   Enable: Certificate modification is supported, both HTTP and HTTPS requests are supported by default, and **force redirect** is supported.
    -   Disable: No HTTPS requests are supported and no certificate/private key information will be retained. You must re-upload the certificate/private key to enable the certificate again.
-   You are allowed to view the certificate, but the certificate only. The private key information cannot be viewed because it is sensitive information. Make sure you keep the certificate information safe.
-   Modifications and edits can be made to the certificate. It takes up to 10 minutes for any modifications and edits to take effect, so proceed with caution.

Billing

HTTPS Secure Acceleration is a value-added offering. Once it is enabled, you are billed based on the number of HTTPS requests. For more information, see  [HTTPS price details](https://www.aliyun.com/price/product?spm=5176.doc27271.2.9.vAt4dL#/cdn/detail).

**Note:** The HTTPS cost is billed separately based on the number of requests, and is not included in the CDN traffic package. Ensure that you have adequate account balance before enabling HTTPS service, so as to avoid any arrears that may affect your CDN service.

Certificate

-   You must upload a certificate for the CDN domains with the** HTTPS secured acceleration** enabled, including the certificate and the private key, both in the PEM format.

    **Note:** CDN adopts the Tengine service which is based on Nginx. Therefore, only certificates that are readable by Nginx are supported, namely, PEM certificates. For more informatio, see[Certificate format and conversion method](intl.en-US/User Guide/Value-added service/HTTPS Acceleration/Certificate Format.md#).

-   Only SSL/TLS handshake with SNI information is supported.
-   The certificate and private key that you upload must match each other. Otherwise, the verification fails.
-   It takes 10 minutes for any certificate updates to take effect.
-   Private key with a password is not supported.

## Configuration guide {#section_p3r_l4l_xdb .section}

1.  Purchase a certificate To enable HTTPS Secure Acceleration, you must have a certificate associated with the CND domains. [You can purchase a certificate with Alibaba Cloud Certificates Service](https://yundun.console.aliyun.com).
2.  configure CDN domain name

    Log on to the[CDN console](https://cdn.console.aliyun.com), go to the Domain Names and select the desired domain name to go to the configuration page, HTTPS Settings, Modify Configuration

    Click **Modify Configuration**to perform the settings.

    1.  Click if**HTTPS Setting**is enabled. Click the **Modify Configuration**button to enter the setting page and click**Enable**.

        **Note:** HTTPS Secure Acceleration is a value-added offering. Once it is enabled, you are billed based on the number of HTTPS requests. For more information, see[Billing details](https://www.alibabacloud.com/zh/product/cdn?spm=a2796.7960336.224002.51.a9715179qFf1GW#pricing).

    2.  Select certificate:
        -   You can[quickly apply for free certificate or buy advanced certificate in Alibaba Cloud SSL certificate service](https://yundun.console.aliyun.com). For a certificate purchased with Alibaba Cloud Certificates Service, you can select to associate the CND domain by using the certificate name directly.
        -   You can use custom upload if no associated certificate is available in the certificate list. In this case, you must set the certificate name, and then upload the certificate information and the private key. This certificate is saved in Alibaba Cloud Certificates Service and can be viewed in the **My Certificates**section.
    3.  Only the PEM certificate format is supported. For more information, see [About Certificate Formats](intl.en-US/User Guide/Value-added service/HTTPS Acceleration/Certificate Format.md#).
    4.  **Force redirect** is supported: You can enable this function to force redirect users’ original request method.
        -   For example, when **Force HTTPS Redirect**is enabled and you initiate an HTTP request, the server returns a 302 redirect response and the original HTTP request is forcibly redirected to an HTTPS request.
        -   Default: supports both HTTP and HTTPS requests.
        -   Force HTTPS redirect: User requests are forcibly redirected to HTTPS requests.
        -   Force HTTP Redirect: User’s requests are forcibly redirected to HTTP requests.
3.  verify whether the certificate is effective

    After the certificate is set up and becomes effective \(about one hour after the HTTPS certificate is set up\), visit resources by means of HTTPS. If the green HTTPS mark appears in the browser, it indicates that a private connection is established with the website and HTTPS Secure Acceleration has taken effect.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5134/3701_en-US.png)



# TLS {#concept_qgv_rzc_rfb .concept}

本文档介绍了TLS功能及其操作步骤。

## 功能介绍 {#section_sgg_vzc_rfb .section}

TLS（Transport Layer Security）即安全传输层协议，在两个通信应用程序之间提供保密性和数据完整性。最典型的应用就是 HTTPS。HTTPS，即 HTTP over TLS，就是安全的 HTTP，运行在 HTTP 层之下，TCP 层之上，为 HTTP 层提供数据加解密服务。

目前，TLS 主要有4个版本：

-   TLSv1.0：RFC2246，1999年发布，基于 SSLv3.0，该版本易受各种攻击（如BEAST和POODLE），除此之外，支持较弱加密，对当今网络连接的安全已失去应有的保护效力。不符合 PCI DSS 合规判定标准。支持的主流浏览器： IE6+，Chrome 1+，Firefox 2+。
-   TLSv1.1：RFC4346，2006年发布，修复 TLSv1.0 若干漏洞。支持的主流浏览器：IE11+，Chrome22+，Firefox24+，Safri7+。
-   TLSv1.2：RFC5246，2008年发布，目前广泛使用的版本。支持的主流浏览器：IE11+，Chrome30+，Firefox27+，Safri7+。
-   TLSv1.3：RFC8446，2018年发布，最新的 TLS 版本，支持0-RTT模式（更快），只支持完全前向安全性密钥交换算法（更安全）。支持的主流浏览器：Chrome 70+，Firefox 63+。

**说明：** 目前TLSv1.0、TLSv1.1和TLSv1.2版本默认开启。

## 操作步骤 {#section_emh_yzc_rfb .section}

**说明：** 请首先配置HTTPS证书，然后才可以开启TLS功能。

1.  登录[CDN控制台](https://cdn.console.aliyun.com/)。
2.  在左侧导航栏，单击**域名管理**。
3.  在准备配置的域名后，单击**管理**。
4.  在左侧导航栏，单击**HTTPS设置**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41679/154174957021599_zh-CN.png)

5.  在**TLS版本控制**栏，根据您的需要，开启或关闭对应的TLS版本。


# HSTS {#concept_dzm_5bd_rfb .concept}

本文档介绍了HSTS功能的原理、使用场景和阿里云控制台的操作步骤。

## 功能介绍 {#section_dqb_xbd_rfb .section}

HSTS \(HTTP Strict Transport Security\)，RFC6797，其作用是强制客户端（如浏览器）使用 HTTPS 与服务器创建连接。

## 使用场景 {#section_a5t_ybd_rfb .section}

当您网站全站使用 HTTPS后，必须要将所有 HTTP 请求 301/302 重定向到 HTTPS。如果您从浏览器输入 HTTP 链接，或在他处点击了 HTTP 链接，则服务器则将该 HTTP 请求 301/302 重定向到 HTTPS。但是这个过程可能被劫持，导致重定向后的请求没有到期服务器，这个问题可以通过 HSTS 来解决。

HSTS 是一个响应头： Strict-Transport-Security: max-age=expireTime \[; includeSubDomains\] \[; preload\] ，各参数说明如下：

-   max-age：单位是秒。
-   Strict-Transport-Security： 在浏览器缓存的时间，浏览器处理域名的 HTTP 访问时，若该域名的 Strict-Transport-Security 没有过期，则在浏览器内部做一次 307 重定向到 HTTPS，从而避免浏览器和服务器之间 301/302 重定向被劫持的风险。
-   includeSubDomains，可选参数，如果指定这个参数，表明这个域名所有子域名也适用上面的规则。
-   preload，可选参数，支持 preload 列表。

**说明：** 

-   HSTS 生效前仍然需要第一次 301/302 重定向到 HTTPS；
-   HSTS 响应头在 HTTPS 访问的响应中有效，在 HTTP 访问的响应中无效；
-   仅对 443 端口有效，对其他端口无效；
-   仅对域名有效，对 IP 无效；
-   启用 HSTS 之后，一旦网站证书错误，在缓存时间。

## 操作步骤 {#section_emh_yzc_rfb .section}

**说明：** 请首先配置HTTPS证书，然后才可以开启TLS功能。

1.  登录[CDN控制台](https://cdn.console.aliyun.com/)。
2.  在左侧导航栏，单击**域名管理**。
3.  在准备配置的域名后，单击**管理**。
4.  在左侧导航栏，单击**HTTPS设置**。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41680/154174960121598_zh-CN.png)
5.  在**HTST**栏，单击**修改配置**。完成配置即可。


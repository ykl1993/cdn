# 回源SNI {#concept_wb3_ndh_chb .concept}

您可以通过本文档，了解回源SNI的工作原理和应用场景，并借此判断是否需要设置回源SNI功能。

## 功能介绍 {#section_lls_bbd_dhb .section}

什么是SNI？

服务器名称指示 Server Name Indication（SNI）是一个扩展的传输层安全性协议 Transport Layer Security（TLS）。在该协议下，握手过程开始时，客户端会告诉它正在连接的那台服务器即将要连接的主机名称，以允许该服务器在相同的IP地址和TCP端口号上呈现多个证书，即一台服务器可以为多个域名提供服务。因此，同一个IP地址上提供的多个安全的HTTPS网站（或其他任何基于TLS的服务），不需要使用相同的证书。

但是，一台服务器使用单个IP提供多个域名的HTTPS服务时，访问服务器的请求就必须要携带SNI信息。因为，只有SNI指明所请求的具体域名，才能让服务器正确地返回对应域名的证书。

什么时候需要设置**回源SNI**？

如果您的源站服务器是上述的“单个IP提供多个域名的HTTPS服务”的情形，且您已经为您的CDN设置了以443端口回源（CDN节点以HTTPS协议访问您的服务器），您就需要设置回源SNI，指明所请求的具体域名。这样CDN节点以HTTPS协议回源访问您的服务器时，服务器才会正确地返回对应的证书。

**说明：** 如果您的源站是阿里云OSS的，则无需设置回源SNI。

## 工作原理 {#section_nsf_kbd_dhb .section}

回源SNI的工作原理如下图所示：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138897/155375859040953_zh-CN.png)

## 操作步骤 {#section_hpn_pbd_dhb .section}

1.  登录[CDN控制台](https://cdn.console.aliyun.com)，并单击**域名管理**。
2.  选择您要配置SNI的域名，单击该域名右侧的**管理**。
3.  单击**回源配置**，在**回源SNI**区域框单击**修改配置**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138897/155375859040954_zh-CN.png)

4.  打开**回源SNI**开关，并在下框内填入您服务器源站提供服务的具体域名，单击**确认**，完成开启SNI功能。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138897/155375859141376_zh-CN.png)



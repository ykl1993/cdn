# 回源SNI {#concept_wb3_ndh_chb .concept}

本文档通过对SNI的应用场景和工作原理的介绍，让您了解是否需要设置回源SNI功能。同时，还提供了具体的操作步骤。

## 功能介绍 {#section_lls_bbd_dhb .section}

随着现代服务器对虚拟主机的支持，一台服务器可以为多个域名提供服务，但是一台服务器使用单个IP提供多个域名的HTTPS服务时，访问服务器的请求就必须要携带SNI（Server Name Indication）信息，SNI指明所请求的具体域名，才能让服务器正确地返回对应域名的证书。

如果您的源站服务器是上述的“单个IP提供多个域名的HTTPS服务”的情形，且您在CDN设置了以443端口回源（CDN节点以HTTPS协议访问您的服务器），您就需要设置回源SNI，指明所请求的具体域名。这样CDN节点以HTTPS协议回源访问您的服务器时，服务器才会正确地返回对应的证书。

**说明：** 如果您的源站是阿里云OSS的，则无需设置回源SNI。

## 示意图 {#section_nsf_kbd_dhb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138897/155291412340953_zh-CN.png)

## 操作步骤 {#section_hpn_pbd_dhb .section}

1.  登录[CDN控制台](https://cdn.console.aliyun.com)，并单击**域名管理**。
2.  选择您要配置SNI的域名，单击该域名右侧的**管理**。
3.  单击**回源配置**，在**回源SNI**区域框单击**修改配置**。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138897/155291412340954_zh-CN.png)
4.  填入您服务器源站里提供服务的具体域名，单击**确认**，完成开启SNI功能。


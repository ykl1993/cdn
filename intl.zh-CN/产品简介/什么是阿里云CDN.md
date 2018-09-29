# 什么是阿里云CDN {#concept_aml_tlg_tdb .concept}

阿里云内容分发网络（Alibaba Cloud Content Delivery Network，简称CDN）将您源站资源缓存至阿里云遍布全球的加速节点上。当终端用户请求访问和获取这些资源时，无需回源，系统将就近调用CDN节点上已经缓存的资源。

在不同区域、不同场景下使用CDN加速您网站内容的分发，将有效分担源站压力，避免网络拥塞，提升用户访问资源的速度和体验。您可以参考[快速入门](../../../../intl.zh-CN/快速入门/快速入门.md#)快速接入阿里云CDN。

## 工作原理 {#section_qry_wz2_h2b .section}

通过以下案例，您可以清楚地了解CDN的工作原理。

假设您的源站域名为 `www.a.com`。接入 CDN 开始使用加速服务后，当您的终端用户（北京）发起 HTTP 请求时，实际的处理流程如下：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5098/15382038524886_zh-CN.png)

1.  终端用户（北京） 向 `www.a.com`下的某资源发起请求，会先向 LDNS 发起域名解析请求。
2.  当 LDNS 解析 `www.a.com` 时，会发现已经配置了 CNAME `www.a.tbcdn.com`。
3.  解析请求会发送至阿里云DNS调度系统，并为请求分配最佳节点 IP。
4.  LDNS 获取 DNS 返回的解析 IP。
5.  用户获取解析 IP。
6.  用户向获取的 IP 发起对该资源的访问请求。
    -   若该 IP 对应的节点已经缓存了该资源，则会将数据直接返回给用户（如图中步骤7、8），此时请求结束。
    -   若该节点未缓存该资源，则节点会向业务源站发起对该资源的请求。获取资源后，结合用户自定义配置的缓存策略（可参考产品文档中的[缓存配置](../../../../intl.zh-CN/用户指南/域名管理/节点缓存设置/缓存配置.md#)），将资源缓存至节点（如图：北京节点），并返回给用户，此时请求结束。

## 相关概念 {#section_gh2_by2_l2b .section}

-   CNAME：即别名\( Canonical Name \)，可以用来把一个域名解析到另一个域名。

-   [回源HOST](../../../../intl.zh-CN/用户指南/域名管理/内容回源设置/回源HOST.md#)：使用回源HOST，您可以自定义CDN节点回源时所需访问的具体服务器域名。

-   [协议回源](../../../../intl.zh-CN/用户指南/域名管理/内容回源设置/协议跟随回源.md#)：开启该功能后，回源使用协议和客户端访问资源的协议保持一致。

-   [过滤参数](../../../../intl.zh-CN/用户指南/域名管理/性能优化设置/过滤参数.md#)：URL请求中，如果携带“？” （半角）和参数，则请求到CDN节点时，CDN节点在收到该请求后是否将该带参数的请求URL请求回源站。


## 使用CDN {#section_i4g_cnf_l2b .section}

您可以查看[CDN学习路径](https://www.alibabacloud.com/zh/getting-started/learningpath/cdn)，快速了解并上手CDN。

您可以登录[CDN控制台](../../../../intl.zh-CN/用户指南/新控制台说明.md#)，了解并使用了CDN的[全部功能](../../../../intl.zh-CN/用户指南/CDN功能列表.md#)。

您还可以使用CDN的[API](../../../../intl.zh-CN/旧版API 参考/简介.md#)，更灵活地帮助您的业务。

## CDN定价 {#section_c3q_dnf_l2b .section}

CDN的[定价策略](../../../../intl.zh-CN/产品定价/计费方式/计费概述.md#)：基础服务和 增值服务。其中，基础服务可以按流量或带宽两种方式计算。

更多CDN定价策略，请参考[产品价格](https://www.aliyun.com/price/product)。

## 相关服务 {#section_lpx_g3f_l2b .section}

您可以使用[全站加速](https://www.alibabacloud.com/help/zh/product/64812.htm)区分动静态资源，并实现动静态资源分别加速。

您可以在[对象存储OSS](../../../../intl.zh-CN/产品简介/什么是对象存储 OSS.md#)中使用CDN加速，提高网站访问速度，有效降低OSS的外网流量费用。

您可以在[视频直播](https://www.alibabacloud.com/help/zh/product/29949.htm)中应用CDN，实现媒资存储、切片转码、访问鉴权、内容分发加速一体化解决方案。

您可以借助[阿里云云解析](https://www.alibabacloud.com/help/zh/product/34269.htm)提供的强大稳定的解析调度入口，确保顺畅的访问体验。

您可以借助[云服务器ECS](../../../../intl.zh-CN/产品简介/什么是云服务器ECS.md#)提高网站可用性，保护服务器源站信息，降低带宽使用成本。

您可以将[负载均衡](../../../../intl.zh-CN/产品简介/什么是负载均衡.md#)服务器的IP地址设置为回源地址，降低回源带宽压力。


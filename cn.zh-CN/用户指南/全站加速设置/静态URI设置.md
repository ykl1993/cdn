# 静态URI设置 {#concept_ckd_31y_wdb .concept}

## 功能介绍 {#section_bjr_mby_wdb .section}

全站加速默认为纯动态加速，即所有资源请求都使用动态加速，通过最优路由回源获取资源。因此静态资源也不会被边缘节点缓存。可通过配置指定静态文件的URI，以区分动静态资源，达到静态资源使用边缘缓存，动态资源用动态加速的最优方案。

## 配置引导 {#section_ukj_nby_wdb .section}

选择**域名管理** \> **选择域名进入域名配置页面** \> **动静态加速规则设置：** 

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5167/3270_zh-CN.png)

选择**静态URI设置**，指定静态URI：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5167/3271_zh-CN.png)

静态URI的资源将使用静态资源加速，缓存在边缘节点上，供用户就近获取。


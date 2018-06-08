# range回源 {#concept_zrw_s1f_xdb .concept}

## 功能介绍 {#section_prj_v1f_xdb .section}

-   Range回源是指客户端通知源站服务器只返回部分内容，以及部分内容的范围。这对于较大文件的分发加速有很大帮助，开启Range回源功能，可以减少回源流量消耗，并且提升资源响应时间。
-   需要源站支持range请求,即对于http请求头中包含 Range 字段,源站能够响应正确的206文件分片
-   开启Range回源，则该参数可以请求回源站。此时源站需要依据 Range 的参数，响应文件的字节范围。同时CDN节点也会向客户端响应相应字节范围的内容。

    **说明：** 例如：客户端向CDN请求中含有range:0-100，则源站端收到的请求中也会含有range：0-100这个参数。并且源站响应给CDN节点，然后CDN节点响应给客户端的就是范围是0-100的一共101个字节内容。

-   关闭Range回源，CDN上层节点会向源站请求全部的文件，并且由于客户端会在收到Range定义的字节后自动断开http链接，请求的文件没有缓存到CDN节点上。最终导致缓存的命中率较低，并且回源流量较大。

    **说明：** 例如：客户端向CDN请求中含有range：0-100，则server端收到的请求中没有range这个参数。源站响应给CDN节点完整文件，但是CDN节点响应给客户端的就是101个字节，但是由于连接断开了，会导致该文件没有缓存到CDN节点上。


## 注意事项 {#section_yr2_1bf_xdb .section}

需要源站支持range请求,即对于http请求头中包含 Range 字段,源站能够响应正确的206文件分片。

## 配置引导 {#section_cxc_bbf_xdb .section}

-   可选配置项，默认不开启。
-   变更配置。

进入CDN域名管理页面，单击**配置**，选择 **开启/关闭**Range回源功能。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5157/3510_zh-CN.png)


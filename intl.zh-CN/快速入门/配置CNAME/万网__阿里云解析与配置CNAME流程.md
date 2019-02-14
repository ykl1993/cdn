# 万网/阿里云解析与配置CNAME流程 {#concept_uwr_kbw_tdb .concept}

您在CDN中添加自己的域名后，阿里云CDN会给您分配对应的CNAME地址。如果您想启用CDN加速服务，需要将加速域名指向CNAME地址。这样访问加速域名的请求才能转发到 CDN节点上，达到加速效果。本文档以您的域名在阿里云解析（原万网）为例。

## 1. 获取加速域名的CNAME地址 {#section_ey5_p4c_5db .section}

**a.** 登录[CDN控制台](https://cdn.console.aliyun.com)，单击**域名管理**。

**b.**复制加速域名对应的CNAME值。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5113/15501332456056_zh-CN.png)

## 2. 添加CNAME记录 {#section_gy5_p4c_5db .section}

**a.**登录 [域名解析控制台](https://dc.console.aliyun.com/dns/?spm=5176.200001.0.0.pbY4Je)。

**b.**在域名列表中找到您加速域名对应的主域名，进入**解析设置**页。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5113/15501332456057_zh-CN.png)

**c.**单击**添加解析**，添加CNAME记录：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5113/15501332456058_zh-CN.png)

-   记录类型请选择为`CNAME`；
-   主机记录即加速域名的前缀，例如：

    |如果您的加速域名为...|主机记录为...|
    |:-----------|:-------|
    |`testcdn.aliyun.com`|`testcdn`|
    |`www.aliyun.com`|`www`|
    |`aliyun.com`|`@`|
    |`*.aliyun.com`|`*`|

-   记录值填写为步骤1复制的CNAME值；
-   解析线路和TTL保持默认值即可:

**d.**单击**确认**，配置CNAME完毕。CNAME配置生效后，CDN服务也会立即生效。

**说明：** 

-   CNAME配置生效时间：新增CNAME记录会实时生效，而修改CNAME记录需要最多72小时生效时间。
-   配置完CNAME后，由于状态更新约有10分钟延迟，阿里云CDN控制台的域名列表页可能仍提示**未配置CNAME**，请忽略。

## 如何验证CNAME配置是否已生效？ {#section_ny5_p4c_5db .section}

配置CNAME后，不同的DNS服务商CNAME配置生效的时间也不同。您可以`ping`或`dig`您所添加的加速域名，如果被转向`*.*kunlun*.com`，即表示CNAME配置已经生效，CDN功能也已生效。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5113/15501332456060_zh-CN.png)


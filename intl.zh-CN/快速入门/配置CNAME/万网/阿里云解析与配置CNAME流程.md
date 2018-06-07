# 万网/阿里云解析与配置CNAME流程 {#concept_uwr_kbw_tdb .concept}

要启用CDN加速服务，需要将您的 加速域名 指向 阿里云CDN分配的CNAME地址，这样访问加速域名的请求才能转发到 CDN节点 上，达到加速效果。本文档以您的域名在 阿里云解析（原万网）为例（文末附DNSPod、新网的配置流程）：

## 1. 获取加速域名的CNAME值 {#section_ey5_p4c_5db .section}

在CDN控制台**域名管理**的域名列表中复制加速域名对应的CNAME值：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5113/6056_zh-CN.png)

## 2. 添加CNAME记录 {#section_gy5_p4c_5db .section}

前往 万网/阿里云解析 的 [域名解析控制台](https://dc.console.aliyun.com/dns/?spm=5176.200001.0.0.pbY4Je)。在域名列表中找到您加速域名对应的主域名，进入**解析设置**页：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5113/6057_zh-CN.png)

选择**添加解析**，添加CNAME记录：

-   记录类型请选择为`CNAME`；
-   主机记录即加速域名的前缀：
    -   例如您的加速域名为`testcdn.aliyun.com`，前缀就是`testcdn`；
    -   加速域名为`www.aliyun.com`，前缀为`www`
    -   加速域名为`aliyun.com`，前缀为`@`
    -   泛域名`*.aliyun.com`，前缀为`*`
-   记录值填写为步骤1复制的CNAME值；
-   解析线路和TTL保持默认值即可:

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5113/6059_zh-CN.png)

点击**确认**，配置CNAME完毕。CNAME配置生效后，CDN服务也会立即生效。

-   CNAME配置生效时间：新增CNAME记录会实时生效，而修改CNAME记录需要最多72小时生效时间。
-   添加时如遇添加冲突，可考虑换一个加速域名，或参考 [解析记录互斥规则](https://help.aliyun.com/knowledge_detail/39787.html)自行调整冲突的记录。
-   配置完CNAME后，由于状态更新约有10分钟延迟，阿里云CDN控制台的域名列表页可能仍提示**未配置CNAME**，请忽略即可。

## 如何验证CNAME配置是否已生效？ {#section_ny5_p4c_5db .section}

配置CNAME后，不同的DNS服务商CNAME配置生效的时间也不同。您可以`ping`或`dig`您所添加的加速域名，如果被转向`*.*kunlun*.com`，即表示CNAME配置已经生效，CDN功能也已生效:

 

另外我们还提供域名在DNSPod、新网解析的 配置CNAME示例：[DNSPod/腾讯云解析 配置流程](https://help.aliyun.com/document_detail/27145.html)、[新网 配置流程](https://help.aliyun.com/document_detail/27146.html)。


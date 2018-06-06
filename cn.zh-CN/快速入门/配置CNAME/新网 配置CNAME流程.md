# 新网 配置CNAME流程 {#concept_rp4_qxd_zdb .concept}

要启用CDN加速服务，需要将 您的加速域名 指向 CDN节点的CNAME地址，这样访问加速域名的请求才能转发到CDN节点上，达到加速效果。本文档以您的域名在新网为例。

## 操作步骤 {#section_ep1_3h2_zdb .section}

1.  获取加速域名的CNAME值。

    在CDN控制台 **域名管理**的域名列表中复制加速域名对应的CNAME值：

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5115/4708_zh-CN.png)

2.  添加CNAME记录。

    前往 新网的域名解析控制台, 进入对应域名的域名解析页，选择**添加新的别名**：记录类型选择为**CNAME**；主机记录即加速域名的前缀（例如要添加`testcdn.aliyun.com`，前缀就是`testcdn`）；记录值填写为步骤1复制的CNAME值；解析线路和TTL 默认值即可。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5115/4709_zh-CN.png)

    填写完单击 **提交**，配置CNAME完毕。CNAME配置生效后，CDN服务也会立即生效。

    **说明：** 

    -   CNAME配置生效时间：新增CNAME记录会实时生效，而修改CNAME记录需要最多72小时生效时间。
    -   添加时如遇添加冲突，可考虑换一个加速域名，或参考 [解析记录互斥规则](https://help.aliyun.com/knowledge_detail/39787.html) 调整记录。
    -   配置完CNAME后，由于状态更新约有10分钟延迟，阿里云CDN控制台的域名列表可能仍提示 **未配置CNAME**，请忽略即可。

## 如何验证CNAME配置是否已生效？ {#section_qp5_zh2_zdb .section}

配置CNAME后，不同的DNS服务商CNAME生效的时间也不同。您可以`ping`或`dig`您所添加的加速域名，如果被转向`*.*kunlun*.com`，即表示CNAME配置已经生效，CDN功能也已生效：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5115/4710_zh-CN.png)


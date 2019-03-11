# DNSPod 配置CNAME流程 {#concept_uwr_kbw_tdb .concept}

要启用CDN加速服务，需要将您的加速域名 指向 CDN节点的CNAME地址，这样访问加速域名的请求才能转发到CDN节点上，达到加速效果。本文档以您域名在腾讯云配置（原DNSPod）CNAME为例：

## 1. 获取加速域名的CNAME值 {#section_ey5_p4c_5db .section}

在CDN控制台**域名管理** 的域名列表中复制加速域名对应的CNAME值：

![](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/27144/intl_zh/1517386480121/6.png)

## 2. 添加CNAME记录 {#section_gy5_p4c_5db .section}

1.  登录DNSPod（腾讯云）的**域名解析控制台**。
2.  在对应域名的域名解析页，选择**添加记录**。
3.  进行相关配置。

    -   记录类型：选择**CNAME**。
    -   主机记录：即加速域名的前缀。例如：您的加速域名为`testcdn.aliyun.com`，那么前缀为`testcdn`。
    -   记录值：填写为步骤1复制的CNAME值。
    -   解析线路：默认值。
    -   TTL：默认值。
    ![](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/27145/cn_zh/1511682064316/5.png)

4.  单击**保存** ，配置CNAME完毕。CNAME配置生效后，CDN服务立即生效。
    -   CNAME配置生效时间：新增CNAME记录会实时生效，而修改CNAME记录需要最多72小时生效时间。
    -   添加时如遇添加冲突，可考虑换一个加速域名，或参考 [解析记录互斥规则](https://help.aliyun.com/knowledge_detail/39787.html) 调整记录。
    -   配置完CNAME后，由于状态更新约有10分钟延迟，阿里云CDN控制台的域名列表可能仍提示 未配置CNAME，请忽略即可。

## 如何验证CNAME配置是否已生效？ {#section_n5l_m1f_zdb .section}

配置CNAME后，不同的DNS服务商CNAME生效的时间也不同。您可以`ping`或`dig`您所添加的加速域名，如果被转向`*.*kunlun*.com`，即表示CNAME配置已经生效，CDN功能也已生效:

![](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/27112/cn_zh/1511517154079/77.png)


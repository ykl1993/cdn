# 回源HOST {#concept_epk_z1d_xdb .concept}

使用回源HOST，您可以自定义CDN节点回源时需要访问的具体服务器域名。可选域名类型包括：加速域名、源站域名或自定义域名。

**说明：** 如果您的一个IP源站绑定了多个域名或站点，就需要指定**回源HOST**回到的具体域名，否则回源会失败。

回源HOST的默认值为：

-   如果源站是**IP**类型，回源HOST默认为加速域名。
-   如果源站是 **OSS源站**类型，回源HOST默认为源站域名。

源站和回源HOST的区别：

-   源站： 源站决定了回源时，请求到的具体IP。
-   回源HOST：回源HOST决定了回源请求访问到该IP上的具体站点。

**说明：** 目前不支持SNI回源。

## 操作步骤 {#section_tk3_dbd_xdb .section}

1.  进入CDN域名管理页，选择域名，单击**管理**。
2.  单击内容回源。
3.  在**回源HOST**项，单击**修改配置**。
4.  开启**回源HOST**，并选择**域名类型**。单击**确定**，配置成功。
5.  ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5145/15513298643347_zh-CN.png)

## 示例 {#section_ids_1sd_l2b .section}

例一

如果您的源站是域名源站`www.a.com`，且将回源HOST设置为`www.b.com`， 则实际回源的是 `www.a.com`解析到的IP站点`www.b.com`。

例二

如果您的源站是IP源站`1.1.1.1` ，且将回源HOST设置为`www.b.com`，则实际回源的是`1.1.1.1`对应的主机上的站点`www.b.com`。


# 回源HOST {#concept_epk_z1d_xdb .concept}

## 功能介绍 {#section_qtb_dbd_xdb .section}

自定义在CDN节点回源时所需访问的具体域名（如果您 一个IP源站绑定了多个**域名/站点**的时候，就需设置**回源Host**指定回到具体哪个域名，否则会回源失败）。

-   **回源host**为可选配置项，默认值为：
    -   如果源站是**IP**类型，回源host默认加速域名。
    -   如果源站是 **OSS源站**类型，回源host默认是源站域名。
-   可选项分别是：加速域名、源站域名、自定义域名。

**说明：** 目前不支持sni 回源。

## 配置引导 {#section_tk3_dbd_xdb .section}

变更配置：进入CDN域名管理页，选择域名进入配置页面，回源设置，可修改回源host的配置。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5145/3347_zh-CN.png)

源站和回源host的区别（一个IP/主机是能绑定 多个域名/站点的，因此需要通过设置回源Host指定回源时回到哪个域名/站点）：

-   源站： 源站决定了回源时，请求到哪个IP。
-   回源host：回源host决定回源请求访问到该IP上的哪个站点。（如果您 一个IP源站 绑定了 多个域名/站点时，就需设置 **回源Host**指定回源到具体哪个域名，否则会回源失败）。

**说明：** 

-   例一：源站是域名源站为`www.a.com`回源host设置为`www.b.com`， 那么实际回源是请到m `www.a.com`解析到的IP上对应的具体的站点：`www.b.com`。
-   例二：源站是IP源站为`1.1.1.1` 回源host设置为`www.b.com`那么实际回源的是`1.1.1.1`上对应的具体站点：`www.b.com`


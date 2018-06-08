# 回源HOST {#concept_xwl_fdd_xdb .concept}

## 功能介绍 {#section_y4g_hdd_xdb .section}

自定义在CDN节点回源过程中所需访问的WEB服务器域名。

**源站**： 源站决定了回源时，请求到哪个IP。

**回源host**：回源host决定回源请求访问到该IP上的哪个站点。

-   例一：源站是域名源站为`www.a.com` 回源host为`www.b.com`。 那么实际回源是请求到`www.a.com` 解析到的IP，对应的主机上的站点`www.b.com`。
-   例二：源站是IP源站为`1.1.1.1`回源host为`www.b.com` 那么实际回源的是`1.1.1.1`对应的主机上的 站点`www.b.com`。

**说明：** 目前不支持sni 回源。

## 配置引导 {#section_tyd_5dd_xdb .section}

-   **回源host**为可选配置项，默认值为：
    -   如果源站是**IP**类型，回源host默认加速域名。
    -   如果源站是**OSS源站**类型，回源host默认是源站域名。
-   可选项分别是：加速域名、源站域名、自定义域名。
-   变更配置：进入CDN域名管理页，选择域名进入配置页面，回源设置，可修改回源host的配置。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13745/3355_zh-CN.png)



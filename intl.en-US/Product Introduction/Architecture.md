# Architecture {#concept_mw2_3mg_tdb .concept}

Key components

-   LVS performs Layer-4 server load balancing.
    -   Dr mode
    -   Dual-LVS performs active-active mutual backup.
    -   WRR is the algorithm used for server load balancing.
-   Tengine performs Layer-7 server load balancing.
    -   The Alibaba Cloud high-performance HTTP servers developed on Nginx are open-source. For more details, refer to the official website.[http://tengine.taobao.org](http://tengine.taobao.org/)
    -   Proactive health checks
    -   SPDY v3 support
-   Swift performs HTTP caching
    -   High-performance cache
    -   Disk \(SSD/SATA\)

Architecture diagram![](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/27105/cn_zh/1464580038618/architecture-001.png)


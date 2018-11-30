# CDN API概述 {#reference_ckk_xml_vdb .reference}

本文档介绍了阿里云CDN的各API名称。您可以分别点击链接查看各API接口的具体参数。

## 服务操作接口 {#section_tsp_qnl_vdb .section}

|API|描述|
|:--|:-|
|[OpenCdnService](intl.zh-CN/旧版API 参考/服务操作接口/开通CDN.md)|开通CDN服务|
|[DescribeCdnService](intl.zh-CN/旧版API 参考/服务操作接口/查询CDN状态.md)|查询CDN服务状态。包括当前计费类型，服务开通时间，下次生效的计费类型，当前业务状态等|
|[ModifyCdnService](intl.zh-CN/旧版API 参考/服务操作接口/变更计费类型.md)|变更CDN服务的计费类型|

## 刷新预热接口 {#section_tzc_vnl_vdb .section}

|API|描述|
|:--|:-|
|[RefreshObjectCaches](intl.zh-CN/旧版API 参考/刷新预热接口/刷新缓存.md)|刷新节点上的文件内容，支持批量|
|[PushObjectCache](intl.zh-CN/旧版API 参考/刷新预热接口/预热.md)|将源站的内容主动预热到L2 Cache节点上，用户首次访问可直接命中缓存，缓解源站压力，支持批量|
|[DescribeRefreshTasks](intl.zh-CN/旧版API 参考/刷新预热接口/查询刷新和预热状态.md)|查询预热刷新状态，是否在全网生效|
|[DescribeRefreshQuota](intl.zh-CN/旧版API 参考/刷新预热接口/查询刷新预热次数限制和余量.md)|查询预热刷新操作余量|

## 日志信息接口 {#section_c3h_xnl_vdb .section}

|API|描述|
|:--|:-|
|[DescribeCdnDomainLogs](intl.zh-CN/旧版API 参考/日志信息接口/下载域名访问日志.md)|获取指定域名的原始访问日志的下载地址|
|[DescribeCustomLogConfig](intl.zh-CN/旧版API 参考/日志信息接口/根据configId查询自定义日志配置信息.md)|根据configId查询自定义日志配置详细信息|
|[DescribeDomainCustomLogConfig](intl.zh-CN/旧版API 参考/日志信息接口/获取域名自定义日志格式配置信息.md)|获取域名自定义日志格式配置信息|
|[DescribeUserCustomLogConfig](intl.zh-CN/旧版API 参考/日志信息接口/获取所有自定义日志配置信息.md)|获取用户所有自定义日志配置信息|
|[ListDomainsByLogConfigId](intl.zh-CN/旧版API 参考/日志信息接口/查询自定义日志格式的域名列表.md)|查询应用某自定义日志格式的所有域名列表|
|[ModifyDomainCustomLogConfig](intl.zh-CN/旧版API 参考/日志信息接口/修改域名所属日志自定义日志配置信息.md)|修改域名所属日志自定义日志配置信息|
|[ModifyUserCustomLogConfig](intl.zh-CN/旧版API 参考/日志信息接口/修改自定义日志配置信息.md)|修改用户下自定义日志配置信息|

## 配置操作接口 {#section_lqd_5nl_vdb .section}

|API|描述|
|:--|:-|
|[DescribeDomainConfigs](intl.zh-CN/旧版API 参考/配置操作接口/查询域名配置.md)|查询域名配置|
|[SetOptimizeConfig](intl.zh-CN/旧版API 参考/配置操作接口/设置页面优化.md)|设置页面优化|
|[SetPageCompressConfig](intl.zh-CN/旧版API 参考/配置操作接口/设置智能压缩.md)|设置智能压缩|
|[SetIgnoreQueryStringConfig](intl.zh-CN/旧版API 参考/配置操作接口/设置过滤参数.md)|设置过滤参数|
|[SetRangeConfig](intl.zh-CN/旧版API 参考/配置操作接口/设置Range回源.md)|设置Range回源|
|[SetVideoSeekConfig](intl.zh-CN/旧版API 参考/配置操作接口/设置拖拽播放.md)|设置拖拽播放|
|[SetSourceHostConfig](intl.zh-CN/旧版API 参考/配置操作接口/设置回源HOST.md)|设置回源host|
|[SetErrorPageConfig](intl.zh-CN/旧版API 参考/配置操作接口/设置404页面.md)|设置404页面|
|[SetForceRedirectConfig](intl.zh-CN/旧版API 参考/配置操作接口/设置强制跳转.md)|设置强制跳转|
|[SetRefererConfig](intl.zh-CN/旧版API 参考/配置操作接口/设置防盗链.md)|设置防盗链|
|[SetFileCacheExpiredConfig](intl.zh-CN/旧版API 参考/配置操作接口/设置文件类型缓存策略.md)|设置文件类型缓存策略|
|[SetPathCacheExpiredConfig](intl.zh-CN/旧版API 参考/配置操作接口/设置路径缓存策略.md)|设置路径缓存策略|
|[ModifyFileCacheExpiredConfig](intl.zh-CN/旧版API 参考/配置操作接口/修改文件类型缓存策略.md)|修改文件类型缓存策略|
|[ModifyPathCacheExpiredConfig](intl.zh-CN/旧版API 参考/配置操作接口/修改路径缓存策略.md)|修改路径缓存策略|
|[DeleteCacheExpiredConfig](intl.zh-CN/旧版API 参考/配置操作接口/删除缓存策略.md)|删除缓存配置|
|[SetReqAuthConfig](intl.zh-CN/旧版API 参考/配置操作接口/设置鉴权.md)|设置鉴权|
|[SetHttpHeaderConfig](intl.zh-CN/旧版API 参考/配置操作接口/设置HTTP头信息.md)|设置HTTP头信息|
|[ModifyHttpHeaderConfig](intl.zh-CN/旧版API 参考/配置操作接口/修改HTTP头信息.md)|修改HTTP头信息|
|[DeleteHttpHeaderConfig](intl.zh-CN/旧版API 参考/配置操作接口/删除HTTP头信息.md)|删除HTTP头信息|
|[SetDomainServerCertificate](intl.zh-CN/旧版API 参考/配置操作接口/设置证书.md)|配置证书|
|[SetIpBlackListConfig](intl.zh-CN/旧版API 参考/配置操作接口/设置IP黑名单.md)|设置加速域名的IP黑名单|

## 域名操作接口 {#section_iv2_tnl_vdb .section}

|API|描述|
|:--|:-|
|[AddCdnDomain](intl.zh-CN/旧版API 参考/域名操作接口/添加加速域名.md)|添加加速域名，一次只能提交一个加速域名|
|[DescribeUserDomains](intl.zh-CN/旧版API 参考/域名操作接口/查询域名列表.md)|查询用户名下所有的域名与状态|
|[DescribeCdnDomainDetail](intl.zh-CN/旧版API 参考/域名操作接口/查询域名信息.md)|获取指定加速域名配置的基本信息|
|[ModifyCdnDomain](intl.zh-CN/旧版API 参考/域名操作接口/修改源站信息.md)|修改加速域名，目前支持修改源站|
|[StartCdnDomain](intl.zh-CN/旧版API 参考/域名操作接口/启用已停用的域名.md)|启用状态为“停用”的加速域名，将DomainStatus变更为online|
|[StopCdnDomain](intl.zh-CN/旧版API 参考/域名操作接口/停用某加速域名.md)|停用某个加速域名，将DomainStatus变更为offline|
|[DeleteCdnDomain](intl.zh-CN/旧版API 参考/域名操作接口/删除加速域名.md)|【慎用】删除当前加速域名，每次只能提交一个加速域名|
|[DescribeDomainsBySource](intl.zh-CN/旧版API 参考/域名操作接口/根据源站查域名.md)|根据源站查询对应的域名信息|

## 辅助工具接口 {#section_ttd_ynl_vdb .section}

|API|描述|
|:--|:-|
|[DescribeIpInfo](intl.zh-CN/旧版API 参考/辅助工具接口/查询IP归属.md)|验证指定的IP是否为阿里云CDN节点的IP地址|

## 资源监控接口 {#section_mn2_wnl_vdb .section}

|API|Description|
|:--|:----------|
|[DescribeDomainBpsData](intl.zh-CN/旧版API 参考/资源监控接口/查询域名的带宽监测数据.md)|获取加速域名的网络带宽监控数据，单位：bit/second|
|[DescribeDomainFlowData](intl.zh-CN/旧版API 参考/资源监控接口/查询流量监控数据.md)|获取加速域名的网络流量监控数据，单位：byte|
|[DescribeDomainSrcBpsData](intl.zh-CN/旧版API 参考/资源监控接口/查询回源带宽监控数据.md)|获取加速域名的回源带宽监控数据，单位：bit/second|
|[DescribeDomainSrcFlowData](intl.zh-CN/旧版API 参考/资源监控接口/查询回源流量监控数据.md)|获取加速域名的回源流量监控数据，单位：bit|
|[DescribeDomainHitRateData](intl.zh-CN/旧版API 参考/资源监控接口/查询字节命中率.md)|获取加速域名的字节命中率（命中字节百分比）|
|[DescribeDomainReqHitRateData](intl.zh-CN/旧版API 参考/资源监控接口/查询请求命中率.md)|获取加速域名的请求命中率（命中请求百分比）|
|[DescribeDomainQpsData](intl.zh-CN/旧版API 参考/资源监控接口/查询域名的每秒访问次数QPS.md)|获取加速域名的每秒访问次数QPS|
|[DescribeDomainHttpCodeData](intl.zh-CN/旧版API 参考/资源监控接口/查询域名HTTP返回码占比数据.md)|获取加速域名最小5分钟粒度的HTTP返回码占比数据|
|[DescribeDomainsUsageByDay](intl.zh-CN/旧版API 参考/资源监控接口/查询域名的天粒度监控统计数据.md)|获取加速域名天粒度监控统计数据|
|[DescribeTopDomainsByFlow](intl.zh-CN/旧版API 参考/资源监控接口/查询按流量排名的域名列表.md)|获取用户按流量排名的域名|
|[DescribeDomainPvData](intl.zh-CN/旧版API 参考/资源监控接口/查询域名的PV页面访问统计.md)|获取加速域名最小1小时粒度的PV页面访问统计|
|[DescribeDomainUvData](intl.zh-CN/旧版API 参考/资源监控接口/查询域名的UV页面独立访问统计数据.md)|获取加速域名最小1小时粒度的UV页面独立访问统计|
|[DescribeDomainRegionData](intl.zh-CN/旧版API 参考/资源监控接口/查询域名的用户区域分布数据.md)|获取加速域名天粒度的用户区域分布数据统计|
|[DescribeDomainISPData](intl.zh-CN/旧版API 参考/资源监控接口/查询域名的用户运营商数据.md)|获取加速域名天粒度的用户运营商分布数据统计|
|[DescribeDomainTopUrlVisit](intl.zh-CN/旧版API 参考/资源监控接口/查询域名某天的热门URL列表.md)|获取加速域名某天内的热门URL列表|
|[DescribeDomainTopReferVisit](intl.zh-CN/旧版API 参考/资源监控接口/查询域名某天的热门页面引用次数排名.md)|获取加速域名某天的热门页面引用次数排名|
|[DescribeDomainFileSizeProportionData](intl.zh-CN/旧版API 参考/资源监控接口/查询域名的文件大小占比统计数据.md)|获取加速域名最小1小时粒度的文件大小占比统计|
|[DescribeCdnRegionAndIsp](intl.zh-CN/旧版API 参考/资源监控接口/查询区域和运营商列表.md)|获取区域和运营商列表|
|[DescribeDomainBpsDataByTimeStamp](intl.zh-CN/旧版API 参考/资源监控接口/查询域名某时刻Locate和Isp的带宽数据.md)|获取加速域名的在某个时刻不同Locate和Isp上的带宽数据，单位 bit/second|
|[DescribeDomainMax95BpsData](intl.zh-CN/旧版API 参考/资源监控接口/查询域名的95带宽峰值监测数据.md)|获取加速域名95带宽峰值监控数据，单位：bit/second|
|[DescribeDomainPathData](intl.zh-CN/旧版API 参考/资源监控接口/查询域名路径级别的监控数据.md)|获取加速域名路径级别的5分钟维度的监控数据，包括流量和访问次数|
|[DescribeL2VipsByDomain](intl.zh-CN/旧版API 参考/资源监控接口/根据域名查询L2节点的vip列表.md)|按域名查询L2节点vip列表。配置白名单后才可以生效|
|[DescribeDomainRealTimeBpsData](intl.zh-CN/旧版API 参考/资源监控接口/获取域名1分钟粒度带宽数据.md)|获取域名1分钟粒度带宽数据|
|[DescribeDomainRealTimeByteHitRateData](intl.zh-CN/旧版API 参考/资源监控接口/获取域名1分钟粒度字节命中率数据.md)|获取域名1分钟粒度字节命中率数据|
|[DescribeDomainRealTimeQpsData](intl.zh-CN/旧版API 参考/资源监控接口/获取域名1分钟粒度每秒访问次数数据.md)|获取域名1分钟粒度每秒访问次数数据|
|[DescribeDomainRealTimeReqHitRateData](intl.zh-CN/旧版API 参考/资源监控接口/获取域名1分钟粒度请求命中率数据.md)|获取域名1分钟粒度请求命中率数据|
|[DescribeDomainSlowRatio](intl.zh-CN/旧版API 参考/资源监控接口/查询视频加速域名的慢速比数据.md)|获取视频加速域名5分钟维度的慢速比数据|

|API|描述|
|:--|:-|
|[DescribeDomainFlowData](intl.zh-CN/旧版API 参考/资源监控接口/查询流量监控数据.md)|网络流量信息|
|[DescribeDomainSrcBpsData](intl.zh-CN/旧版API 参考/资源监控接口/查询回源带宽监控数据.md)|回源带宽信息|
|[DescribeDomainSrcFlowData](intl.zh-CN/旧版API 参考/资源监控接口/查询回源流量监控数据.md)|回源流量信息|
|[DescribeDomainHitRateData](intl.zh-CN/旧版API 参考/资源监控接口/查询字节命中率.md)|缓存字节命中率信息|
|[DescribeDomainReqHitRateData](intl.zh-CN/旧版API 参考/资源监控接口/查询请求命中率.md)|缓存请求命中率信息|
|[DescribeDomainQpsData](intl.zh-CN/旧版API 参考/资源监控接口/查询域名的每秒访问次数QPS.md)|每秒访问次数信息|
|[DescribeDomainHttpCodeData](intl.zh-CN/旧版API 参考/资源监控接口/查询域名HTTP返回码占比数据.md)|响应码占比信息|
|[DescribeDomainsUsageByDay](intl.zh-CN/旧版API 参考/资源监控接口/查询域名的天粒度监控统计数据.md)|天粒度资源使用信息|
|[DescribeTopDomainsByFlow](intl.zh-CN/旧版API 参考/资源监控接口/查询按流量排名的域名列表.md)|天粒度按流量域名排名|
|[DescribeDomainPvData](intl.zh-CN/旧版API 参考/资源监控接口/查询域名的PV页面访问统计.md)|pv趋势数据|
|[DescribeDomainUvData](intl.zh-CN/旧版API 参考/资源监控接口/查询域名的UV页面独立访问统计数据.md)|uv趋势数据|
|[DescribeDomainRegionData](intl.zh-CN/旧版API 参考/资源监控接口/查询域名的用户区域分布数据.md)|用户区域占比|
|[DescribeDomainISPData](intl.zh-CN/旧版API 参考/资源监控接口/查询域名的用户运营商数据.md)|运营商占比|
|[DescribeDomainTopUrlVisit](intl.zh-CN/旧版API 参考/资源监控接口/查询域名某天的热门URL列表.md)|热门url访问统计|
|[DescribeDomainTopReferVisit](intl.zh-CN/旧版API 参考/资源监控接口/查询域名某天的热门页面引用次数排名.md)|热门refer统计|
|[DescribeDomainFileSizeProportionData](intl.zh-CN/旧版API 参考/资源监控接口/查询域名的文件大小占比统计数据.md)|文件访问占比|
|[DescribeDomainBpsDataByTimeStamp](intl.zh-CN/旧版API 参考/资源监控接口/查询域名某时刻Locate和Isp的带宽数据.md)|获取某时刻带宽数据，支持地区或者运营商筛选条件|
|[DescribeDomainBpsDataByTimeStamp](intl.zh-CN/旧版API 参考/资源监控接口/查询区域和运营商列表.md)|获取区域和运营商列表|
|[DescribeL2VipsByDomain](intl.zh-CN/旧版API 参考/资源监控接口/根据域名查询L2节点的vip列表.md)|查询L2节点的vip列表|


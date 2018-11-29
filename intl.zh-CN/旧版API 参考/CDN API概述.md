# CDN API概述 {#reference_ckk_xml_vdb .reference}

## 服务操作接口 {#section_tsp_qnl_vdb .section}

|API|描述|
|:--|:-|
|[OpenCdnService](ZH-CN_TP_5191.dita)|开通CDN服务|
|[DescribeCdnService](ZH-CN_TP_5192.dita)|查询CDN服务状态。包括当前计费类型，服务开通时间，下次生效的计费类型，当前业务状态等|
|[ModifyCdnService](ZH-CN_TP_5193.dita)|变更CDN服务的计费类型|

## 域名操作接口 {#section_iv2_tnl_vdb .section}

|API|描述|
|:--|:-|
|[DescribeUserDomains](ZH-CN_TP_5196.dita)|查询用户名下所有的域名与状态|
|[DescribeCdnDomainDetail](ZH-CN_TP_5197.dita)|获取指定加速域名配置的基本信息|
|[AddCdnDomain](ZH-CN_TP_5195.dita)|添加加速域名，一次只能提交一个加速域名|
|[StartCdnDomain](ZH-CN_TP_5199.dita)|启用状态为“停用”的加速域名，将DomainStatus变更为online|
|[StopCdnDomain](ZH-CN_TP_5200.dita)|停用某个加速域名，将DomainStatus变更为offline|
|[DeleteCdnDomain](ZH-CN_TP_5201.dita)|【慎用】删除当前加速域名，每次只能提交一个加速域名|
|[DescribeDomainsBySource](ZH-CN_TP_5202.dita)|根据源站查询对应的域名信息|

## 域名配置接口 {#section_lqd_5nl_vdb .section}

|API|描述|
|:--|:-|
|[DescribeDomainConfigs](ZH-CN_TP_5209.dita)|查询域名配置|
|[SetOptimizeConfig](ZH-CN_TP_5210.dita)|设置页面优化|
|[SetPageCompressConfig](ZH-CN_TP_5211.dita)|设置智能压缩|
|[SetIgnoreQueryStringConfig](ZH-CN_TP_5212.dita)|设置过滤参数|
|[SetRangeConfig](ZH-CN_TP_5213.dita)|设置Range回源|
|[SetVideoSeekConfig](ZH-CN_TP_5214.dita)|设置拖拽播放|
|[SetSourceHostConfig](ZH-CN_TP_5215.dita)|设置回源host|
|[SetErrorPageConfig](ZH-CN_TP_5216.dita)|设置404页面|
|[SetForceRedirectConfig](ZH-CN_TP_5217.dita)|设置强制跳转|
|[SetRefererConfig](ZH-CN_TP_5218.dita)|设置防盗链|
|[SetFileCacheExpiredConfig](ZH-CN_TP_5219.dita)|设置文件类型缓存策略|
|[SetPathCacheExpiredConfig](ZH-CN_TP_5220.dita)|设置路径缓存策略|
|[ModifyFileCacheExpiredConfig](ZH-CN_TP_5221.dita)|修改文件类型缓存策略|
|[ModifyPathCacheExpiredConfig](ZH-CN_TP_5222.dita)|修改路径缓存策略|
|[DeleteCacheExpiredConfig](ZH-CN_TP_5223.dita)|删除缓存配置|
|[SetReqAuthConfig](ZH-CN_TP_5224.dita)|设置鉴权|
|[SetHttpHeaderConfig](ZH-CN_TP_5225.dita)|设置HTTP头信息|
|[ModifyHttpHeaderConfig](ZH-CN_TP_5226.dita)|修改HTTP头信息|
|[DeleteHttpHeaderConfig](ZH-CN_TP_5227.dita)|删除HTTP头信息|
|[SetDomainServerCertificate](ZH-CN_TP_5228.dita)|配置证书|

## 刷新预热接口 {#section_tzc_vnl_vdb .section}

|API|描述|
|:--|:-|
|[RefreshObjectCaches](ZH-CN_TP_5204.dita)|刷新节点上的文件内容，支持批量|
|[PushObjectCache](ZH-CN_TP_5205.dita)|将源站的内容主动预热到L2 Cache节点上，用户首次访问可直接命中缓存，缓解源站压力，支持批量|
|[DescribeRefreshTasks](ZH-CN_TP_5206.dita)|查询预热刷新状态，是否在全网生效|
|[DescribeRefreshQuota](ZH-CN_TP_5207.dita)|查询预热刷新操作余量|

## 资源监控接口 {#section_mn2_wnl_vdb .section}

|API|描述|
|:--|:-|
|[DescribeDomainFlowData](ZH-CN_TP_5232.dita)|网络流量信息|
|[DescribeDomainSrcBpsData](ZH-CN_TP_5233.dita)|回源带宽信息|
|[DescribeDomainSrcFlowData](ZH-CN_TP_5234.dita)|回源流量信息|
|[DescribeDomainHitRateData](ZH-CN_TP_5235.dita)|缓存字节命中率信息|
|[DescribeDomainReqHitRateData](ZH-CN_TP_5236.dita)|缓存请求命中率信息|
|[DescribeDomainQpsData](ZH-CN_TP_5237.dita)|每秒访问次数信息|
|[DescribeDomainHttpCodeData](ZH-CN_TP_5238.dita)|响应码占比信息|
|[DescribeDomainsUsageByDay](ZH-CN_TP_5239.dita)|天粒度资源使用信息|
|[DescribeTopDomainsByFlow](ZH-CN_TP_5240.dita)|天粒度按流量域名排名|
|[DescribeDomainPvData](ZH-CN_TP_5241.dita)|pv趋势数据|
|[DescribeDomainUvData](ZH-CN_TP_5242.dita)|uv趋势数据|
|[DescribeDomainRegionData](ZH-CN_TP_5243.dita)|用户区域占比|
|[DescribeDomainISPData](ZH-CN_TP_5244.dita)|运营商占比|
|[DescribeDomainTopUrlVisit](ZH-CN_TP_5245.dita)|热门url访问统计|
|[DescribeDomainTopReferVisit](ZH-CN_TP_5246.dita)|热门refer统计|
|[DescribeDomainFileSizeProportionData](ZH-CN_TP_5247.dita)|文件访问占比|
|[DescribeDomainBpsDataByTimeStamp](ZH-CN_TP_5249.dita)|获取某时刻带宽数据，支持地区或者运营商筛选条件|
|[DescribeDomainBpsDataByTimeStamp](ZH-CN_TP_5248.dita)|获取区域和运营商列表|
|[DescribeL2VipsByDomain](ZH-CN_TP_5252.dita)|查询L2节点的vip列表|

## 日志信息接口 {#section_c3h_xnl_vdb .section}

|API|描述|
|:--|:-|
|[DescribeCdnDomainLogs](ZH-CN_TP_5263.dita)|获取指定域名的原始访问日志的下载地址。|

## 辅助工具接口 {#section_ttd_ynl_vdb .section}

|API|描述|
|:--|:-|
|[DescribeIpInfo](ZH-CN_TP_5271.dita)|验证指定的IP是否为阿里云CDN节点的IP地址。|


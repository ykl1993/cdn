# CDN API概述 {#reference_ckk_xml_vdb .reference}

## 服务操作接口 {#section_tsp_qnl_vdb .section}

|API|描述|
|:--|:-|
|[OpenCdnService](https://help.aliyun.com/document_detail/27157.html?spm=a2c4g.11186623.2.4.vqQvrL)|开通CDN服务|
|[DescribeCdnService](https://help.aliyun.com/document_detail/27158.html?spm=a2c4g.11186623.2.5.vqQvrL)|查询CDN服务状态。包括当前计费类型，服务开通时间，下次生效的计费类型，当前业务状态等|
|[ModifyCdnService](https://help.aliyun.com/document_detail/27159.html?spm=a2c4g.11186623.2.6.vqQvrL)|变更CDN服务的计费类型|

## 域名操作接口 {#section_iv2_tnl_vdb .section}

|API|描述|
|:--|:-|
|[DescribeUserDomains](https://help.aliyun.com/document_detail/27162.html?spm=a2c4g.11186623.2.7.vqQvrL)|查询用户名下所有的域名与状态|
|[DescribeCdnDomainDetail](https://help.aliyun.com/document_detail/27163.html?spm=a2c4g.11186623.2.8.vqQvrL)|获取指定加速域名配置的基本信息|
|[AddCdnDomain](https://help.aliyun.com/document_detail/27161.html?spm=a2c4g.11186623.2.9.vqQvrL)|添加加速域名，一次只能提交一个加速域名|
|[StartCdnDomain](https://help.aliyun.com/document_detail/27165.html?spm=a2c4g.11186623.2.10.vqQvrL)|启用状态为“停用”的加速域名，将DomainStatus变更为online|
|[StopCdnDomain](https://help.aliyun.com/document_detail/27166.html?spm=a2c4g.11186623.2.11.vqQvrL)|停用某个加速域名，将DomainStatus变更为offline|
|[DeleteCdnDomain](https://help.aliyun.com/document_detail/27167.html?spm=a2c4g.11186623.2.12.vqQvrL)|【慎用】删除当前加速域名，每次只能提交一个加速域名|
|[DescribeDomainsBySource](https://help.aliyun.com/document_detail/50453.html?spm=a2c4g.11186623.2.13.vqQvrL)|根据源站查询对应的域名信息|

## 域名配置接口 {#section_lqd_5nl_vdb .section}

|API|描述|
|:--|:-|
|[DescribeDomainConfigs](https://help.aliyun.com/document_detail/27169.html?spm=a2c4g.11186623.2.14.vqQvrL)|查询域名配置|
|[SetOptimizeConfig](https://help.aliyun.com/document_detail/27170.html?spm=a2c4g.11186623.2.15.vqQvrL)|设置页面优化|
|[SetPageCompressConfig](https://help.aliyun.com/document_detail/27171.html?spm=a2c4g.11186623.2.16.vqQvrL)|设置智能压缩|
|[SetIgnoreQueryStringConfig](https://help.aliyun.com/document_detail/27172.html?spm=a2c4g.11186623.2.17.vqQvrL)|设置过滤参数|
|[SetRangeConfig](https://help.aliyun.com/document_detail/27173.html?spm=a2c4g.11186623.2.18.vqQvrL)|设置Range回源|
|[SetVideoSeekConfig](https://help.aliyun.com/document_detail/27174.html?spm=a2c4g.11186623.2.19.vqQvrL)|设置拖拽播放|
|[SetSourceHostConfig](https://help.aliyun.com/document_detail/27175.html?spm=a2c4g.11186623.2.20.vqQvrL)|设置回源host|
|[SetErrorPageConfig](https://help.aliyun.com/document_detail/27176.html?spm=a2c4g.11186623.2.21.vqQvrL)|设置404页面|
|[SetForceRedirectConfig](https://help.aliyun.com/document_detail/27177.html?spm=a2c4g.11186623.2.22.vqQvrL)|设置强制跳转|
|[SetRefererConfig](https://help.aliyun.com/document_detail/27178.html?spm=a2c4g.11186623.2.23.vqQvrL)|设置防盗链|
|[SetFileCacheExpiredConfig](https://help.aliyun.com/document_detail/27179.html?spm=a2c4g.11186623.2.24.vqQvrL)|设置文件类型缓存策略|
|[SetPathCacheExpiredConfig](https://help.aliyun.com/document_detail/27180.html?spm=a2c4g.11186623.2.25.vqQvrL)|设置路径缓存策略|
|[ModifyFileCacheExpiredConfig](https://help.aliyun.com/document_detail/27181.html?spm=a2c4g.11186623.2.26.vqQvrL)|修改文件类型缓存策略|
|[ModifyPathCacheExpiredConfig](https://help.aliyun.com/document_detail/27182.html?spm=a2c4g.11186623.2.27.vqQvrL)|修改路径缓存策略|
|[DeleteCacheExpiredConfig](https://help.aliyun.com/document_detail/27183.html?spm=a2c4g.11186623.2.28.vqQvrL)|删除缓存配置|
|[SetReqAuthConfig](https://help.aliyun.com/document_detail/27184.html?spm=a2c4g.11186623.2.29.vqQvrL)|设置鉴权|
|[SetHttpHeaderConfig](https://help.aliyun.com/document_detail/27185.html?spm=a2c4g.11186623.2.30.vqQvrL)|设置HTTP头信息|
|[ModifyHttpHeaderConfig](https://help.aliyun.com/document_detail/27186.html?spm=a2c4g.11186623.2.31.vqQvrL)|修改HTTP头信息|
|[DeleteHttpHeaderConfig](https://help.aliyun.com/document_detail/27187.html?spm=a2c4g.11186623.2.32.vqQvrL)|删除HTTP头信息|
|[SetDomainServerCertificate](https://help.aliyun.com/document_detail/45014.html?spm=a2c4g.11186623.2.33.vqQvrL)|配置证书|

## 刷新预热接口 {#section_tzc_vnl_vdb .section}

|API|描述|
|:--|:-|
|[RefreshObjectCaches](https://help.aliyun.com/document_detail/27200.html?spm=a2c4g.11186623.2.34.vqQvrL)|刷新节点上的文件内容，支持批量|
|[PushObjectCache](https://help.aliyun.com/document_detail/27201.html?spm=a2c4g.11186623.2.35.vqQvrL)|将源站的内容主动预热到L2 Cache节点上，用户首次访问可直接命中缓存，缓解源站压力，支持批量|
|[DescribeRefreshTasks](https://help.aliyun.com/document_detail/27202.html?spm=a2c4g.11186623.2.36.vqQvrL)|查询预热刷新状态，是否在全网生效|
|[DescribeRefreshQuota](https://help.aliyun.com/document_detail/27203.html?spm=a2c4g.11186623.2.37.vqQvrL)|查询预热刷新操作余量|

## 资源监控接口 {#section_mn2_wnl_vdb .section}

|API|描述|
|:--|:-|
|[DescribeDomainFlowData](https://help.aliyun.com/document_detail/27206.html?spm=a2c4g.11186623.2.39.vqQvrL)|网络流量信息|
|[DescribeDomainSrcBpsData](https://help.aliyun.com/document_detail/27207.html?spm=a2c4g.11186623.2.40.vqQvrL)|回源带宽信息|
|[DescribeDomainSrcFlowData](https://help.aliyun.com/document_detail/27208.html?spm=a2c4g.11186623.2.41.vqQvrL)|回源流量信息|
|[DescribeDomainHitRateData](https://help.aliyun.com/document_detail/27209.html?spm=a2c4g.11186623.2.42.vqQvrL)|缓存字节命中率信息|
|[DescribeDomainReqHitRateData](https://help.aliyun.com/document_detail/27210.html?spm=a2c4g.11186623.2.43.vqQvrL)|缓存请求命中率信息|
|[DescribeDomainQpsData](https://help.aliyun.com/document_detail/27211.html?spm=a2c4g.11186623.2.44.vqQvrL)|每秒访问次数信息|
|[DescribeDomainHttpCodeData](https://help.aliyun.com/document_detail/27212.html?spm=a2c4g.11186623.2.45.vqQvrL)|响应码占比信息|
|[DescribeDomainsUsageByDay](https://help.aliyun.com/document_detail/27213.html?spm=a2c4g.11186623.2.46.vqQvrL)|天粒度资源使用信息|
|[DescribeTopDomainsByFlow](https://help.aliyun.com/document_detail/27214.html?spm=a2c4g.11186623.2.47.vqQvrL)|天粒度按流量域名排名|
|[DescribeDomainPvData](https://help.aliyun.com/document_detail/27215.html?spm=a2c4g.11186623.2.48.vqQvrL)|pv趋势数据|
|[DescribeDomainUvData](https://help.aliyun.com/document_detail/27216.html?spm=a2c4g.11186623.2.49.vqQvrL)|uv趋势数据|
|[DescribeDomainRegionData](https://help.aliyun.com/document_detail/27217.html?spm=a2c4g.11186623.2.50.vqQvrL)|用户区域占比|
|[DescribeDomainISPData](https://help.aliyun.com/document_detail/27218.html?spm=a2c4g.11186623.2.51.vqQvrL)|运营商占比|
|[DescribeDomainTopUrlVisit](https://help.aliyun.com/document_detail/27219.html?spm=a2c4g.11186623.2.52.vqQvrL)|热门url访问统计|
|[DescribeDomainTopReferVisit](https://help.aliyun.com/document_detail/27220.html?spm=a2c4g.11186623.2.53.vqQvrL)|热门refer统计|
|[DescribeDomainFileSizeProportionData](https://help.aliyun.com/document_detail/27221.html?spm=a2c4g.11186623.2.54.vqQvrL)|文件访问占比|
|[DescribeDomainBpsDataByTimeStamp](https://help.aliyun.com/document_detail/43473.html?spm=a2c4g.11186623.2.55.vqQvrL)|获取某时刻带宽数据，支持地区或者运营商筛选条件|
|[DescribeDomainBpsDataByTimeStamp](https://help.aliyun.com/document_detail/43474.html?spm=a2c4g.11186623.2.56.vqQvrL)|获取区域和运营商列表|
|[DescribeL2VipsByDomain](https://help.aliyun.com/document_detail/48769.html?spm=a2c4g.11186623.2.58.vqQvrL)|查询L2节点的vip列表|

## 日志信息接口 {#section_c3h_xnl_vdb .section}

|API|描述|
|:--|:-|
|[DescribeCdnDomainLogs](https://help.aliyun.com/document_detail/27224.html?spm=a2c4g.11186623.2.59.vqQvrL)|获取指定域名的原始访问日志的下载地址。|

## 辅助工具接口 {#section_ttd_ynl_vdb .section}

|API|描述|
|:--|:-|
|[DescribeIpInfo](https://help.aliyun.com/document_detail/27226.html?spm=a2c4g.11186623.2.60.vqQvrL)|验证指定的IP是否为阿里云CDN节点的IP地址。|


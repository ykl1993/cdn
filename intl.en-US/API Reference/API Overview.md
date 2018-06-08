# API Overview {#reference_ckk_xml_vdb .reference}

## Service operation interface {#section_tsp_qnl_vdb .section}

|API|Description|
|:--|:----------|
|[OpenCdnService](https://help.aliyun.com/document_detail/27157.html?spm=a2c4g.11186623.2.4.vqQvrL)|Activates the CDN service.|
|[DescribeCdnService](https://help.aliyun.com/document_detail/27158.html?spm=a2c4g.11186623.2.5.vqQvrL)|Queries the CDN service status. This includes Includes Current billing type, service opening time, next effective billing type, current business status, etc.|
|[ModifyCdnService](https://help.aliyun.com/document_detail/27159.html?spm=a2c4g.11186623.2.6.vqQvrL)|Changes the CDN service billing type.|

## Domain name operation interface {#section_iv2_tnl_vdb .section}

|API|Description|
|:--|:----------|
|[DescribeUserDomains](https://help.aliyun.com/document_detail/27162.html?spm=a2c4g.11186623.2.7.vqQvrL)|Queries all domain names and statuses under a user name.|
|[DescribeCdnDomainDetail](https://help.aliyun.com/document_detail/27163.html?spm=a2c4g.11186623.2.8.vqQvrL)|Obtains the basic information for the specified CDN domain configuration.|
|[AddCdnDomain](https://help.aliyun.com/document_detail/27161.html?spm=a2c4g.11186623.2.9.vqQvrL)|Adds CDN domains. At one time, only one CDN can be submitted.|
|[StartCdnDomain](https://help.aliyun.com/document_detail/27165.html?spm=a2c4g.11186623.2.10.vqQvrL)|Enables an accelerated domain name with a status of "disabled" and changes the domainstatus to online|
|[StopCdnDomain](https://help.aliyun.com/document_detail/27166.html?spm=a2c4g.11186623.2.11.vqQvrL)|Deactivates a CDN domain by changing the “DomainStatus” to “offline”.|
|[DeleteCdnDomain](https://help.aliyun.com/document_detail/27167.html?spm=a2c4g.11186623.2.12.vqQvrL)|\[USE WITH CAUTION\] Deletes the current CDN domain. Only one CDN domain can be submitted at a time.|
|[DescribeDomainsBySource](https://help.aliyun.com/document_detail/50453.html?spm=a2c4g.11186623.2.13.vqQvrL)|Query the corresponding domain name information based on the source station|

## Domain name configuration interface {#section_lqd_5nl_vdb .section}

|API|Description|
|:--|:----------|
|[DescribeDomainConfigs](https://help.aliyun.com/document_detail/27169.html?spm=a2c4g.11186623.2.14.vqQvrL)|Queryies domain name configuration|
|[Setoptimizeconfig](https://help.aliyun.com/document_detail/27170.html?spm=a2c4g.11186623.2.15.vqQvrL)|Configures page optimization parameters.|
|[SetPageCompressConfig](https://help.aliyun.com/document_detail/27171.html?spm=a2c4g.11186623.2.16.vqQvrL)|Configures smart compression parameters.|
|[SetIgnoreQueryStringConfig](https://help.aliyun.com/document_detail/27172.html?spm=a2c4g.11186623.2.17.vqQvrL)|Configure filter parameters|
|[SetRangeConfig](https://help.aliyun.com/document_detail/27173.html?spm=a2c4g.11186623.2.18.vqQvrL)|Configures Back-to-source of range.|
|[SetVideoSeekConfig](https://help.aliyun.com/document_detail/27174.html?spm=a2c4g.11186623.2.19.vqQvrL)|Configures Drag/Drop playback.|
|[Setsourcehostconfig](https://help.aliyun.com/document_detail/27175.html?spm=a2c4g.11186623.2.20.vqQvrL)|Set back-to-source host|
|[SetErrorPageConfig](https://help.aliyun.com/document_detail/27176.html?spm=a2c4g.11186623.2.21.vqQvrL)|Set the 404 page.|
|[Setforceredirectconfig](https://help.aliyun.com/document_detail/27177.html?spm=a2c4g.11186623.2.22.vqQvrL)|Set the force redirect method, and currently support HTTP and HTTPS force redirects.|
|[SetRefererConfig](https://help.aliyun.com/document_detail/27178.html?spm=a2c4g.11186623.2.23.vqQvrL)|Set Anti-leech.|
|[SetFileCacheExpiredConfig](https://help.aliyun.com/document_detail/27179.html?spm=a2c4g.11186623.2.24.vqQvrL)|Set file expiration configuration.|
|[SetPathCacheExpiredConfig](https://help.aliyun.com/document_detail/27180.html?spm=a2c4g.11186623.2.25.vqQvrL)|Modify directory expiration configuration.|
|[ModifyFileCacheExpiredConfig](https://help.aliyun.com/document_detail/27181.html?spm=a2c4g.11186623.2.26.vqQvrL)|Modify file expiration settings.|
|[ModifyPathCacheExpiredConfig](https://help.aliyun.com/document_detail/27182.html?spm=a2c4g.11186623.2.27.vqQvrL)|Modify the path Cache Policy|
|[DeleteCacheExpiredConfig](https://help.aliyun.com/document_detail/27183.html?spm=a2c4g.11186623.2.28.vqQvrL)|Delete a custom cache policy.|
|[SetReqAuthConfig](https://help.aliyun.com/document_detail/27184.html?spm=a2c4g.11186623.2.29.vqQvrL)|Set CDN domain access authentication configuration.|
|[Sethttpheaderconfig](https://help.aliyun.com/document_detail/27185.html?spm=a2c4g.11186623.2.30.vqQvrL)|Set custom HTTP headers.|
|[ModifyHttpHeaderConfig](https://help.aliyun.com/document_detail/27186.html?spm=a2c4g.11186623.2.31.vqQvrL)|Modify custom HTTP headers.|
|[DeleteHttpHeaderConfig](https://help.aliyun.com/document_detail/27187.html?spm=a2c4g.11186623.2.32.vqQvrL)|Delete the Referer anti-leech configuration of a CDN domain.|
|[SetDomainServerCertificate](https://help.aliyun.com/document_detail/45014.html?spm=a2c4g.11186623.2.33.vqQvrL)|Set whether to enable the certificate function under a domain name and modify certificate information.|

## Refresh and push interface {#section_tzc_vnl_vdb .section}

|API|Description|
|:--|:----------|
|[Refreshobjectcaches](https://help.aliyun.com/document_detail/27200.html?spm=a2c4g.11186623.2.34.vqQvrL)|Refreshes the file content on a node. Refreshes the specified URL content to the Cache node.|
|[PushObjectCache](https://help.aliyun.com/document_detail/27201.html?spm=a2c4g.11186623.2.35.vqQvrL)|Actively pushes content from the origin site to the L2 Cache node. Upon first access, users can directly hit cache so as to relieve pressure on the origin site.|
|[Describerefreshtasks](https://help.aliyun.com/document_detail/27202.html?spm=a2c4g.11186623.2.36.vqQvrL)|Queries whether or not cache push or refresh statuses have taken effect for the whole site.|
|[DescribeRefreshQuota](https://help.aliyun.com/document_detail/27203.html?spm=a2c4g.11186623.2.37.vqQvrL)|Query preheating refresh operation margin|

## Resource monitoring interface {#section_mn2_wnl_vdb .section}

|API|Description|
|:--|:----------|
|[DescribeDomainBpsData](https://help.aliyun.com/document_detail/27205.html?spm=a2c4g.11186623.2.38.vqQvrL)|Network bandwidth information|
|[DescribeDomainFlowData](https://help.aliyun.com/document_detail/27206.html?spm=a2c4g.11186623.2.39.vqQvrL)|Obtain the network traffic metric data of a CDN domain. The unit is bytes.|
|[DescribeDomainSrcBpsData](https://help.aliyun.com/document_detail/27207.html?spm=a2c4g.11186623.2.40.vqQvrL)|Obtain the back-to-source bandwidth metric data of CDN domains. The unit is bit/second.|
|[DescribeDomainSrcFlowData](https://help.aliyun.com/document_detail/27208.html?spm=a2c4g.11186623.2.41.vqQvrL)|Obtain the back-to-source traffic metric data on a CDN domain in bits.|
|[DescribeDomainHitRateData](https://help.aliyun.com/document_detail/27209.html?spm=a2c4g.11186623.2.42.vqQvrL)|Obtain the bytes hit rate \(percentage of hit bytes\) of CDN domains.|
|[DescribeDomainReqHitRateData](https://help.aliyun.com/document_detail/27210.html?spm=a2c4g.11186623.2.43.vqQvrL)|Obtain the request hit rate \(percentage of hit requests\) of CDN domain names.|
|[DescribeDomainQpsData](https://help.aliyun.com/document_detail/27211.html?spm=a2c4g.11186623.2.44.vqQvrL)|Obtain the times of access to a CDN domain per second. The value is expressed in QPS.|
|[DescribeDomainHttpCodeData](https://help.aliyun.com/document_detail/27212.html?spm=a2c4g.11186623.2.45.vqQvrL)|Obtain the HTTP return code proportion of CDN domains. The minimum granularity is 5 minutes.|
|[DescribeDomainsUsageByDay](https://help.aliyun.com/document_detail/27213.html?spm=a2c4g.11186623.2.46.vqQvrL)|Obtain the per-day monitoring statistics on a CDN domain.|
|[DescribeTopDomainsByFlow](https://help.aliyun.com/document_detail/27214.html?spm=a2c4g.11186623.2.47.vqQvrL)|Obtain the domain names that are ranked by traffic.|
|[DescribeDomainPvData](https://help.aliyun.com/document_detail/27215.html?spm=a2c4g.11186623.2.48.vqQvrL)|Obtain the PV page access statistics. The minimum granularity is 1 hour.|
|[DescribeDomainUvData](https://help.aliyun.com/document_detail/27216.html?spm=a2c4g.11186623.2.49.vqQvrL)|Obtain the independent UV page access statistics of a CDN domain. The minimum granularity is 1 hour.|
|[DescribeDomainRegionData](https://help.aliyun.com/document_detail/27217.html?spm=a2c4g.11186623.2.50.vqQvrL)|Obtain the regional user distribution of CDN domains with day granularity.|
|[DescribeDomainISPData](https://help.aliyun.com/document_detail/27218.html?spm=a2c4g.11186623.2.51.vqQvrL)|Obtain the distribution of users and carriers of CDN domain names with day granularity.|
|[Describedomaintopurlvisit](https://help.aliyun.com/document_detail/27219.html?spm=a2c4g.11186623.2.52.vqQvrL)|Obtain the popular URL list for a CDN domain name on a specific day.|
|[DescribeDomainTopReferVisit](https://help.aliyun.com/document_detail/27220.html?spm=a2c4g.11186623.2.53.vqQvrL)|Obtain the reference times ranking of popular pages for a CDN domain name on a specific day.|
|[DescribeDomainFileSizeProportionData](https://help.aliyun.com/document_detail/27221.html?spm=a2c4g.11186623.2.54.vqQvrL)|Obtain the file size shares of a CDN domain name. The minimum granularity is 1 hour.|
|[DescribeDomainBpsDataByTimeStamp](https://help.aliyun.com/document_detail/43473.html?spm=a2c4g.11186623.2.55.vqQvrL)|Obtain the bandwidth data of a CDN domain name on different locations and ISPs at specific time. The unit is bit/second.|
|[DescribeDomainBpsDataByTimeStamp](https://help.aliyun.com/document_detail/43474.html?spm=a2c4g.11186623.2.56.vqQvrL)|Obtain the bandwidth data of a CDN domain name on different locations and ISPs at specific time. The unit is bit/second.|
|[DescribeRangeDataByLocateAndIspService](https://help.aliyun.com/document_detail/44723.html?spm=a2c4g.11186623.2.57.vqQvrL)| Not opened currently|
|[DescribeL2VipsByDomain](https://help.aliyun.com/document_detail/48769.html?spm=a2c4g.11186623.2.58.vqQvrL)|Query the virtual IP address list of an L2 node by the domain name. This interface takes effect after a whitelist is configured.|

## Log Information Interface {#section_c3h_xnl_vdb .section}

|API|Description|
|:--|:----------|
|[DescribeCdnDomainLogs](https://help.aliyun.com/document_detail/27224.html?spm=a2c4g.11186623.2.59.vqQvrL)|Obtains the download address for the original access log of the specified domain name.|

## Verifies IP interface {#section_ttd_ynl_vdb .section}

|API|Description|
|:--|:----------|
|[DescribeIpInfo](https://help.aliyun.com/document_detail/27226.html?spm=a2c4g.11186623.2.60.vqQvrL)|Verifies whether the specified IP address is the IP address of an Alibaba Cloud CDN node.|


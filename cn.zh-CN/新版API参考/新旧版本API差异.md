# 新旧版本API差异 {#concept_o23_yby_pgb .concept}

本文档介绍了CDN新旧两个版本API接口的差异。

旧版API文档请参阅[旧版API参考](../../../../../cn.zh-CN/API参考/API概述.md)。

**说明：** 旧版API后期将不再维护，请您使用新版API。

## 涉及变更的接口 {#section_y4r_f5m_qgb .section}

|旧版接口名|变更详情|
|:----|:---|
|`DescribeDomainFlowData`|变成`DescribeDomainTrafficData`|
| -   `DescribeDomainBpsData`
-   `DescribeDomainHitRateData`
-   `DescribeDomainHttpCodeData`
-   `DescribeDomainQpsData`
-   `DescribeDomainTrafficData`

 | -   时间格式变更，YYYY-MM-DDThh:mmZ =\> YYYY-MM-DDThh:mm:ssZ。
-   去掉fixTimeGap和timeMerge参数。
-   去掉动态和静态数据。

 |
|`AddCdnDomain`| -   去掉`SourceType`、`SourcePort`、`Priorities`、`Region`入参

 |
|`ModifyCdnDomain`| -   去掉`SourceType`、`SourcePort`、`Priorities`参数。
-   `Sources`参数，格式改为： \[\{"content":"1.1.1.1","type":"ipaddr","priority":"20","port":80\}\]

 |
|`DescribeCdnDomainDetail`| -   去掉`SourceType`、`Sources`、`SourcePort`、`Region`出参.
-   补充`Description`、`Scope`、`CertificateName`出参说明

 |
|`DescribeDomainBpsData`| -   最多可获取最近90天的数据 =\> 最多可获取90天的数据。
-   去掉`DomainType`入参。
-   入参`Interval`说明：支持300, 3600, 14400, 28800和86400秒。不传和传的值不支持时，默认值300秒 =\> 支持60，300，3600，86400秒。不传和传的值不支持时，时间跨度不超过3天，默认值300秒；超过3天默认值3600秒，超过30天默认值86400秒。
-   补充`LocationNameEn`、`IspNameEn`出参说明。
-   去掉`SupplyBpsDatas出`参说明。

 |
|`DescribeCdnDomainLogs`| -   时间格式变更YYYY-MM-DDThh:mmZ -\> YYYY-MM-DDThh:mm:ssZ。
-   去掉`LogDay`入参。
-   出参模型调整，详情请见[下方](#no8)。

 |
|`DeleteSpecificConfig`|`FunctionName`参数必填 =\> 去掉`FunctionName`参数。|
|`DescribeDomainAverageResponseTime`|时间格式变更，YYYY-MM-DDThh:mmZ =\> YYYY-MM-DDThh:mm:ssZ。|
|`DescribeUserDomains`| -   去掉`SourceType`出参。
-   去掉`Sources`入参。
-   出参`Sources`格式调整。

 |
|`DescribeDomainRegionData`| -   时间格式变更，YYYY-MM-DDThh:mmZ =\> YYYY-MM-DDThh:mm:ssZ。
-   最多可获取最近90天的数据 =\> 最多可获取90天的数据。
-   去掉`ByteHitRate`、`ReqErrRate`、`ReqHitRate`出参（`jing`接口无此信息返回）。

 |
|`DescribeExtensiveDomainData`| -   时间格式变更，YYYY-MM-DDThh:mmZ =\> YYYY-MM-DDThh:mm:ssZ。
-   去掉`ExtensiveDomain`入参泛域名格式是否合法。
-   去掉只能查询最近90天内的数据校验。
-   不支持不传时间默认时间范围的查询，起止时间改成必传。

 |
|`DescribeDomainBpsDataByTimeStamp`|时间格式变更，YYYY-MM-DDThh:mmZ =\> YYYY-MM-DDThh:mm:ssZ。|
| -   `DescribeDomainFileSizeProportion`
-   `DescribeDomainPvData`
-   `DataDescribeDomainUvData`

 | -   时间格式变更，YYYY-MM-DDThh:mmZ =\> YYYY-MM-DDThh:mm:ssZ。
-   入参`DomainName`改成必传。

 |
| -   `DescribeDomainMax95BpsData`
-   `DescribeDomainsUsageByDay`
-   `DescribeDomainReqHitRateData`
-   `DescribeTopDomainsByFlow`

 | -   时间格式变更，YYYY-MM-DDThh:mmZ =\> YYYY-MM-DDThh:mm:ssZ。
-   最多可获取最近90天的数据 =\> 最多可获取90天的数据。

 |
| -   `DescribeDomainTopReferVisit`
-   `DescribeDomainTopUrlVisit`

 |入参`DomainName`改成必传。|
|`DescribeDomainHttpsData`| -   去掉`DomainType`、`TimeMerge`、`Cls`、`FixTimeGap`入参。
-   时间格式变更，YYYY-MM-DDThh:mmZ =\> YYYY-MM-DDThh:mm:ssZ。
-   最多可获取最近90天的数据 =\> 最多可获取90天的数据。
-   去掉动态、静态数据的出参。

 |
| -   `SetPageCompressConfig`
-   `SetIgnoreQueryStringConfig`
-   `SetVideoSeekConfig`
-   `SetOptimizeConfig`
-   `SetRemoveQueryStringConfig`

 |参数值从`On/Off`改为`on/off`。|
|`SetFileCacheExpiredConfig`|去掉参数Weight。|
|`SetIpBlackListConfig`|不支持设置空值。|
|`DeleteCacheExpiredConfig`|去掉必填参数`CacheType`。|

```
{
      "RequestId": "1805F349-0A2B-41D9-B4AD-33632AFC27F1",
      "DomainLogModel": {
        "DomainName": "gc.ggter.com",
        "DomainLogDetails": {
          "DomainLogDetail": [
            {
              "EndTime": "2015-05-23T04:00:00Z",
              "LogName": "gc.ggter.com_2015_05_23_1100_1200.gz",
              "LogPath": "cdnlog.cn-hangzhou.oss.aliyun-inc.com/gc.ggter.com/2015_05_23/gc.ggter.com_2015_05_23_1100_1200.gz?OSSAccessKeyId\u003d3xmgf7JheOfOTUTf\u0026Expires\u003d1432539994\u0026Signature\u003d7Ly4ccKN3afzAGYyWDbxBcOcn2I%3D",
              "LogSize": 257,
              "StartTime": "2015-05-23T03:00:00Z"
            }
          ]
        }
      },
      "PageNumber": 1,
        "TotalCount": 3,
        "PageSize": 100
    }
    --------->
    {
        "RequestId": "077D0284-F041-4A41-A932-B48377FDAA25",
        "DomainLogDetails": {
            "DomainLogDetail": [
                {
                    "LogInfos": {
                        "LogInfoDetail": [
                            {
                                "LogName": "test1.test.com_2018_03_25_180000_190000.gz",
                                "LogPath": "cdnlog2.aliyuncs.com/test1.test.com/2018_03_25/test1.test.com_2018_03_25_180000_190000.gz?Expires=1522659931&OSSAccessKeyId=LTAIstjGueo4ZEuA&Signature=suZFyJHoD3RzZqK%2Bcu6P4VaNAVI%3D",
                                "EndTime": "1521975600",
                                "StartTime": "1521972000",
                                "LogSize": 2645401
                            }
                        ]
                    },
                    "LogCount": 20,
                    "PageInfos": {
                        "PageNumber": 1,
                        "PageSize": 20,
                        "Total": 20
                    },
                    "DomainName": "test1.test.com"
                }
            ]
        }
    }
```

## 新增接口 {#section_crb_k5m_qgb .section}

以下接口为新增接口：`DescribeCdnUserQuota`、`DescribeCdnUserResourcePackage`、`DescribeCdnCertificateList`。

## 未涉及变更的接口 {#section_jvs_mtm_qgb .section}

以下接口均未有变更：`StartCdnDomain`、`StopCdnDomain`、`DeleteCdnDomain`、`PushObjectCache`、`RefreshObjectCaches`、`PreloadObjectCaches`、`PurgeObjectCaches`、 `OpenCdnService`、`ModifyCdnService`、`BlockObjectCaches`、`DescribeUserConfigs`、 `DescribeCdnService`、`DescribeCdnTypes`、`SetDomainServerCertificate`、`DescribeDomainCertificateInfo`、 `BatchDeleteCdnDomainConfig`、`BatchStartCdnDomain`、`BatchStopCdnDomain`、`SetRangeConfig`、`SetUserAgentAcessRestriction`、 `BatchSetCdnDomainConfig`、`SetL2OssKeyConfig`、`SetForwardSchemeConfig`、`SetPathCacheExpiredConfig`、`SetForceRedirectConfig`、`SetReqAuthConfig`、 `SetErrorPageConfig`、`SetIpAllowListConfig`、`SetDomainGreenManagerConfig`、`SetHttpErrorPageConfig`、 `SetCcConfig`、`SetHttpsOptionConfig`、`SetSourceHostConfig`、`SetRemoteReqAuthConfig`、 `SetUserGreenManagerConfig`、`SetHttpHeaderConfig`、`SetRefererConfig`、`SetReqHeaderConfig`、 `ModifyFileCacheExpiredConfig`、`ModifyPathCacheExpiredConfig`、`ModifyHttpHeaderConfig`和`DeleteHttpHeaderConfig`。


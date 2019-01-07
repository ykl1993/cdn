# DescribeCdnDomainLogs {#reference_srr_cyc_5db .reference}

Obtain the download address for the original access log of the specified domain name.

**Note:** Log content is retained for a maximum of 1 month.

## Request parameters {#section_rxs_wnz_5db .section}

|Parameters|Type|Required|Example values|Description|
|:---------|:---|:-------|:-------------|:----------|
|Action|String|Yes|DescribeCdnDomainLogs| The name of this interface. Value: 

 DescribeCdnDomainLogs

 |
|DomainName|String|Yes|www.yourdomain.com| Domain name \(only supports single query\).

 |
|EndTime|String|No|2017-12-22T08:00:00:00Z| -   End time must be later than start time.
-   The time interval between start time and end time does not exceed one year.
-   The date format adopts ISO8601 notation and uses the UTC time.
-   Example: 2016-10-20T04:00:00Z.

 |
|LogDay|String|No|2015-05-24| The day when the log is obtained.

-   Format: yyyy-MM-dd.
-   You can specify one of LogDay, StartTime and EndTime.
-   Default: Same day

 |
|PageNumber|Long|No|2| The page number.

 Range value: any integer larger than 1.

 |
|PageSize|Long|No|300| Page size.

-   Maximum value: 1000
-   Range value: any integer between 1 and 1000.
-   Default value: 300

 |
|StartTime|String|No|2017-12-21T08:00:00:00Z| Start time when the log is obtained.

-   The date format adopts ISO8601 notation and uses the UTC time.
-   Example: 2016-10-20T04:00:00Z.

 |

## Return Parameters {#section_vkr_f4z_5db .section}

|Parameters|Type|Example values|Description|
|:---------|:---|:-------------|:----------|
|PageNumber|Long|1| The page where the data returns.

 |
|PageSize|Long|100| The entire page size.

 |
|TotalCount|Long|3| Total number of bars.

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8| The ID of the request.

 |
|DomainLogModel| | | Log model.

 |
|└DomainName|String|gc.ggter.com| Domain name.

 |
|└DomainLogDetails| | | The data made up by multiple DomainLogDetail.

 |
|└LogPath|String|Cdnlog.cn-hangzhou.oss.aliyun-inc.com/gc.ggter.com/2015\_05\_23/gc.ggter.com\_2015\_05\_23\_1100\_1200.gz? OSSAccessKeyId\\u003d3xmgf7JheOfOTUTf\\u0026Expires\\u003d1432539994\\u0026Signature\\u003d7Ly4ccKN3afzAGYyWDbxBcOcn2I%3D| The log path.

 |
|└StartTime|String|2017-12-21T08:00:00:00Z| Start time.

 |
|└EndTime|String|Tes 22t08: 00: 00: 00Z| End Time.

 |
|└LogSize|Long|257| The log size.

 |
|└LogName|String|gc.ggter.com\_2015\_05\_23\_1100\_1200.gz| The log name.

 |

## Examples {#section_fb4_44z_5db .section}

**Request example**

```
https://cdn.aliyuncs.com?Action=DescribeCdnDomainLogs&DomainName=gc.ggter.com&LogDay=2015-05-24&public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "DomainLogModel":{
            "DomainLogDetails":{
                "DomainLogDetail":[
                    
                        "EndTime":"2015-05-23T04:00:00Z",
                        "LogName":"gc.ggter.com_2015_05_23_1100_1200.gz",
                        "LogPath":"cdnlog.cn-hangzhou.oss.aliyun-inc.com/gc.ggter.com/2015_05_23/gc.ggter.com_2015_05_23_1100_1200.gz? Ossaccesskeyid = 3xmgf7JheOfOTUTf & Expires = 1432539994 & Signature = 7Ly4ccKN3afzAGYyWDbxBcOcn2I % 3D ",
                        "LogSize":257,
                        "StartTime":"2015-05-23T03:00:00Z"
                    
                    
                        "EndTime":"2015-05-23T08:00:00Z",
                        "LOGNAME": "maid ",
                        "LogPath":"cdnlog.cn-hangzhou.oss.aliyun-inc.com/gc.ggter.com/2015_05_23/gc.ggter.com_2015_05_23_1500_1600.gz? OSSAccessKeyId=3xmgf7JheOfOTUTf&Expires=1432539994&Signature=dMv7VqPqZHXVbKPmorGIvylC66c%3D",
                        "LogSize":194,
                        "StartTime":"2015-05-23T07:00:00Z"
                    
                    
                        "EndTime":"2015-05-23T14:00:00Z",
                        "LogName":"gc.ggter.com_2015_05_23_2100_2200.gz",
                        "LogPath":"cdnlog.cn-hangzhou.oss.aliyun-inc.com/gc.ggter.com/2015_05_23/gc.ggter.com_2015_05_23_2100_2200.gz? OSSAccessKeyId=3xmgf7JheOfOTUTf&Expires=1432539994&Signature=FpSQCbgNcxCBYIxKVoKC8mGghUQ%3D",
                        "LogSize":258,
                        "StartTime":"2015-05-23T13:00:00Z"
                    }
                ]
            },
          
        },
        "RequestId":"1805F349-0A2B-41D9-B4AD-33632AFC27F1",
    "PageNumber": 1, 
      "TotalCount": 3, 
      "PageSize": 100 
    }
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message:" The request processing has failed due to some unknown error .",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```



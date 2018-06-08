# DescribeDomainsUsageByDay {#reference_p5q_dvm_vdb .reference}

Obtain the per-day monitoring statistics on a CDN domain.

-   When StartTime and EndTime are not specified, the interface reads data from the past 7 days by default. Query by specified start time and end time is supported. The two parameters must be both specified.
-   The system supports query of only one domain name or all domain names belonging to the current user.
-   Data from the past 90 days can be obtained at most.

## Request parameters {#section_zyh_vvm_vdb .section}

|Parameters|Type|Required| Example values|Description|
|Action|String|Yes|DescribeDomainsUsageByDay|The name of this interface. Value: DescribeDomainsUsageByDay|
|DomainName|String|No|www.yourdomain.com|CDN domain name to be queried. This parameter supports only one domain name. If this parameter is left blank, all domain names belonging to the current user are queried.|
|EndTime|String|No|2017-12-22T08:00:00:00Z| -   The end time must be later than the start time.
-   Beijing Time is adopted.
-   Format: YYYY-MM-DD.

 |
|StartTime|String|No|2017-12-21T08:00:00:00Z| -   Start time of data query.
-   Beijing Time is adopted.
-   Format: YYYY-MM-DD.

 |

## Return parameters {#section_jgt_1wm_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|C88EF8ED-72F0-45EA-9E86-95114E224FC5|The ID of the request.|
|DomainName|String|test.com|CDN domain name information.|
|DataInterval|String|86400|Interval of each record. The value is invariably set to 1 day.|
|StartTime|String|2015-12-01|Start time.|
|EndTime|String|2015-12-02|End time.|
|UsageByDays| | |Statistics during each interval.|
|  └TimeStamp|String|2017-12-22T08:00:00:00Z|Start time of a time slice.|
|  └BytesHitRate|String|97.46250599529726|Hit rate.|
|  └Qps|String|7.466354166666667|Access volume per second.|
|  └RequestHitRate|String|70.24770071912111|Request hit rate.|
|  └MaxBps|String|1.050307709E8|Peak bandwidth.|
|  └MaxBpsTime|String|2015-12-01|Time of peak bandwidth.|
|  └MaxSrcBps|String|2015-12-01 22: 30|Back-to-source peak bandwidth.|
|  └TotalAccess|String|645093|Total access volume.|
|  └MaxSrcBpsTime|String|2015-12-01 22:30|Time of back-to-source peak bandwidth.|
|  └TotalTraffic|String|564300099309|Total traffic.|
|UsageTotal| | |Summarized data.|
|  └BytesHitRate|String|97.03110726801242|Hit rate.|
|  └RequestHitRate|String|69.92610837438424|Request hit rate.|
|  └MaxBps|String|1.0747912780000001E8|Peak bandwidth.|
|  └MaxBpsTime|String|2015-12-02 23:55|Time of peak bandwidth.|
|  └MaxSrcBps|String|2015-12-02 17:20|Back-to-source peak bandwidth.|
|  └TotalAccess|String|1319500|Total access volume.|
|  └MaxSrcBpsTime|String|2015-12-02 17:20|Time of back-to-source peak bandwidth.|
|  └TotalTraffic|String|1117711832100|Total traffic.|

## Examples {#section_zmh_wnf_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com?Action=DescribeDomainsUsageByDay&DomainName=test.com
&StartTime=2015-11-29
&EndTime=2015-11-30
&public request parameter
```

**Normal return example**

**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```



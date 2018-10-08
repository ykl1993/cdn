# DescribeDomainMax95BpsData {#reference_in2_bgn_vdb .reference}

Obtain the 95th percentile bandwidth metric data of CDN domain names. Unit: bit/second. Unit: bit/second.

-   When StartTime and EndTime are not specified, the system reads data from the past 24 hours by default. Query by specified start time and end time is also supported. The two parameters must be both specified.
-   Batch domain name query is supported. Multiple domain names are separated by commas \(half width\).
-   Data from the past 90 days can be obtained at most.

## Request parameters {#section_kcl_5hn_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|DescribeDomainMax95BpsData|The system sets parameters. Value: DescribeDomainMax95BpsData|
|DomainName|String|No|www.yourdomain.com| If the parameter is left blank, the system returns the combined data of all CDN domain names by default.

 -   You can enter CDN domain names to be queried.
-   Batch domain name query is supported. Multiple domain names are separated by commas \(half width\).

 |
|EndTime|String|No|2017-12-22T08:00:00:00Z| -   The end time must be later than the start time.
-   The date format adopts ISO8601 notation and uses the UTC time.
-   Format: YYYY-MM-DDThh:mmZ.

 |
|StartTime|String|No|2017-12-21T08:00:00:00Z| Gets the starting point of the data.

 -   The date format adopts ISO8601 notation and uses the UTC time.
-   Format: YYYY-MM-DDThh:mmZ.
-   Minimum data granularity: 5 minutes.
-   If this parameter is left blank, data from the past 24 hours is read by default.

 |

## Return parameters {#section_as2_b3n_vdb .section}

|Parameters|Type|Example values|Description|
|DomainName|String|test.com|CDN domain name information.|
|StartTime|String|2015-12-10T20:00Z|Start time.|
|EndTime|String|2015-12-10T21:00Z|End time.|
|Max95Bps|String|16777590.28|95th percentile bandwidth.|
|DomesticMax95Bps|String|16777590.28|95th percentile bandwidth in China.|
|OverseasMax95Bps|String|0|95th percentile bandwidth outside China.|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The request ID.|

## Examples {#section_uz2_x1n_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com?Action=DescribeDomainMax95BpsData&DomainName=test.com
&StartTime=2015-12-10T20:00Z
&EndTime=2015-12-10T21:00Z
&public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "DomainName":"test.com",
        "DomesticMax95Bps":"16777590.28",
        "EndTime":"2015-12-10T21:00Z",
        "Max95Bps":"16777590.28",
        "OverseasMax95Bps":"0",
        "RequestId":"3C6CCEC4-6B88-4D4A-93E4-D47B3D92CF8F",
        "StartTime":"2015-12-10T20:00Z"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```



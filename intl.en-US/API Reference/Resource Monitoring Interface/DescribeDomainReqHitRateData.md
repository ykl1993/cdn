# DescribeDomainReqHitRateData {#reference_x2l_hsm_vdb .reference}

Obtains the request hit rate \(percentage of hit requests\) of CDN domains.

-   When StartTime and EndTime are not specified, the system reads data from the past 24 hours by default. Query by specified start time and end time is also supported. The two parameters must be both specified.
-   Batch domain name query is supported. Multiple domain names are separated by commas \(half width\).
-   Data from the past 90 days can be obtained at most.

## Request parameters {#section_ijs_nsm_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|DescribeDomainReqHitRateData|The name of this interface. Value: DescribeDomainReqHitRateData|
|DomainName|String|No|www.yourdomain.com|CDN domain to be queried. This parameter can be set to support only one domain name. If this parameter is left blank, the system queries all domain names.|
|EndTime|String|No|2017-12-22T08:00:00:00Z| -   The end time must be later than the start time.
-   The date format adopts ISO8601 notation and uses the UTC time.
-   Format: YYYY-MM-DDThh:mmZ.

 |
|Interval|String|No|300| -   Time granularity of data query.
-   300s, 3600s, 14400s, 28800s and 86400s are supported.
-   When the parameter is left blank or when the value is not supported, the default value 300 seconds is used.

 |
|StartTime|String|No|2017-12-21T08:00:00:00Z| -   Start time of data query.
-   The date format adopts ISO8601 notation and uses the UTC time.
-   Format: YYYY-MM-DDThh:mmZ
-   Minimum data granularity: 5 minutes.
-   If this parameter is unspecified, data from the past 24 hours is read by default.

 |

## Return parameters {#section_sb5_wsm_vdb .section}

|Parameters|Type|Example values|Description|
|DomainName|String|test.com| CDN domain name information.|
|DataInterval|String|300|Interval of each record. The unit is seconds.|
|StartTime|String|2015-12-10T20:00Z|Start time.|
|EndTime|String|2015-12-10T21:00Z|End time.|
|ReqHitRateInterval| | |Bytes hit rate during each interval.|
|  └TimeStamp|String|2017-12-22T08:00:00:00Z|Start time of a time slice|
|  └Value|String|100.0|Detailed usage data.|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|Request ID.|

## Example {#section_zmh_wnf_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com?Action=DescribeDomainReqHitRateData&DomainName=test.com
&StartTime=2015-12-10T20:00Z
&EndTime=2015-12-10T21:00Z
&public request parameter
```

**Normal return example**

-   JSON format

    ```
    {
        "DataInterval":"300",
        "DomainName":"test.com",
        "EndTime":"2015-12-10T21:00Z",
        "ReqHitRateInterval":{
            "DataModule":[
                {
                    "TimeStamp":"2015-12-10T21:00:00Z",
                    "Value":"100.0"
                },
                {
                    "TimeStamp":"2015-12-10T20:35:00Z",
                    "Value":"100.0"
                },
                {
                    "TimeStamp":"2015-12-10T20:50:00Z",
                    "Value":"99.99932881437826"
                },
                {
                    "TimeStamp":"2015-12-10T20:05:00Z",
                    "Value":"100.0"
                },
                {
                    "TimeStamp":"2015-12-10T20:10:00Z",
                    "Value":"100.0"
                },
                {
                    "TimeStamp":"2015-12-10T20:55:00Z",
                    "Value":"100.0"
                },
                {
                    "TimeStamp":"2015-12-10T20:30:00Z",
                    "Value":"100.0"
                },
                {
                    "TimeStamp":"2015-12-10T20:25:00Z",
                    "Value":"100.0"
                },
                {
                    "TimeStamp":"2015-12-10T20:00:00Z",
                    "Value":"100.0"
                },
                {
                    "TimeStamp":"2015-12-10T20:40:00Z",
                    "Value":"100.0"
                },
                {
                    "TimeStamp":"2015-12-10T20:15:00Z",
                    "Value":"100.0"
                },
                {
                    "TimeStamp":"2015-12-10T20:45:00Z",
                    "Value":"100.0"
                },
                {
                    "TimeStamp":"2015-12-10T20:20:00Z",
                    "Value":"100.0"
                }
            ]
        },
        "RequestId":"5ADA5190-EE5B-4EF2-BE00-DC441B8D81DD",
        "StartTime":"2015-12-10T20:00Z"
    }
    ```


**Exception return example**

-   JSON format

    ```
    {
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    }
    ```



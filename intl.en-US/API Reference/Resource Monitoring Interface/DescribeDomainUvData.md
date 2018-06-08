# DescribeDomainUvData {#reference_ubn_cym_vdb .reference}

Obtain the independent UV page access statistics of a CDN domain. The minimum granularity is 1 hour.

-   When StartTime and EndTime are not specified, the system reads data from the past 24 hours by default. Query by specified start time and end time is also supported. The two parameters must be both specified.
-   The system supports query of only one domain name or all domain names belonging to the current user.
-   Data from the past 90 days can be obtained at most.

## Request parameters {#section_oth_3ym_vdb .section}

|Name|Type|Required|Example values|Description|
|Action|String|Yes|DescribeDomainUvData|The name of this interface.  Value: DescribeDomainUvData|
|DomainName|String|No|test.test.com|CDN domain name to be queried. This parameter can be set to support only one domain name. If this parameter is left blank, all domain names belonging to the current user are queried.|
|EndTime|String|No|2015-11-29| -   The end time must be later than the start time.
-   The date format adopts ISO8601 notation and uses the UTC time.
-   Format: YYYY-MM-DDThh:mmZ.

 |
|StartTime|String|No|2015-11-29| Start time of data query.

 -   The date format adopts ISO8601 notation and uses the UTC time.
-   Format: YYYY-MM-DDThh:mmZ
-   The minimum data granularity is 1 hour.
-   If this parameter is left blank, data from the past 24 hours is read by default.

 |

## Return parameters {#section_j5s_nym_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|E9D3257A-1B7C-414C-90C1-8D07AC47BCAC|The ID of the request.|
|DomainName|String|ttest.test.com|CDN domain name to be quuried.|
|DataInterval|String|3600|Time interval.|
|StartTime|String|2015-11-30|Start time of data query.|
|EndTime|String|2015-11-30|End time of data query.|
|UvDataInterval| | |Data.|
|  └TimeStamp|String|2015-11-29T20:00:00Z|Time stamp.|
|  └Value|String|318|UV.|

## Examples {#section_zmh_wnf_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com?Action=DescribeDomainUvData&DomainName=test.com
&StartTime=2015-11-29
&EndTime=2015-11-30
&public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "DataInterval":"3600",
        "DomainName":"test.com",
        "EndTime":"2015-11-30",
        "RequestId":"E9D3257A-1B7C-414C-90C1-8D07AC47BCAC",
        "StartTime":"2015-11-29",
        "UvDataInterval":{
            "UsageData":[
                
                    "TimeStamp":"2015-11-29T20:00:00Z",
                    "Value":"318"
                
                
                    "TimeStamp":"2015-11-29T18:00:00Z",
                    "Value":"318"
                
                
                    "TimeStamp":"2015-11-29T03:00:00Z",
                    "Value":"329"
                
                
                    "TimeStamp":"2015-11-29T21:00:00Z",
                    "Value":"316"
                
                
                    "TimeStamp":"2015-11-29T07:00:00Z",
                    "Value":"319"
                
                
                    "TimeStamp":"2015-11-29T00:00:00Z",
                    "Value":"326"
                
                
                    "TimeStamp":"2015-11-29T11:00:00Z",
                    "Value":"321"
                
                
                    "TimeStamp":"2015-11-29T10:00:00Z",
                    "Value":"313"
                
                
                    "TimeStamp":"2015-11-29T08:00:00Z",
                    "Value":"331"
                
                
                    "TimeStamp":"2015-11-29T01:00:00Z",
                    "Value":"324"
                
                
                    "TimeStamp":"2015-11-29T04:00:00Z",
                    "Value":"330"
                
                
                    "TimeStamp":"2015-11-29T14:00:00Z",
                    "Value":"335"
                
                
                    "TimeStamp":"2015-11-29T12:00:00Z",
                    "Value":"318"
                
                
                    "TimeStamp":"2015-11-29T23:00:00Z",
                    "Value":"310"
                
                
                    "TimeStamp":"2015-11-29T17:00:00Z",
                    "Value":"309"
                
                
                    "TimeStamp":"2015-11-29T22:00:00Z",
                    "Value":"320"
                
                
                    "TimeStamp":"2015-11-29T16:00:00Z",
                    "Value":"309"
                
                
                    "TimeStamp":"2015-11-29T02:00:00Z",
                    "Value":"317"
                
                
                    "TimeStamp":"2015-11-29T06:00:00Z",
                    "Value":"309"
                
                
                    "TimeStamp":"2015-11-29T19:00:00Z",
                    "Value":"308"
                
                
                    "TimeStamp":"2015-11-29T13:00:00Z",
                    "Value":"347"
                
                
                    "TimeStamp":"2015-11-29T15:00:00Z",
                    "Value":"341"
                
                
                    "TimeStamp":"2015-11-29T05:00:00Z",
                    "Value":"347"
                
                
                    "TimeStamp":"2015-11-29T09:00:00Z",
                    "Value":"312"
                
            
        
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```



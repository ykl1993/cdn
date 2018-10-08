# DescribeDomainPvData {#reference_tvd_lxm_vdb .reference}

Obtain the PV page access statistics. The minimum granularity is 1 hour.

-   When StartTime and EndTime are not specified, the system reads data from the past 24 hours by default. Query by specified start time and end time is also supported. The two parameters must be both specified.
-   The system supports query of only one domain name or all domain names belonging to the current user.
-   Data from the past 90 days can be obtained at most.

## Request parameters {#section_o2w_qxm_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|DescribeDomainPvData|The name of this interface. Value: DescribeDomainPvData|
|DomainName|String|No|test.test.com|CDN domain name to be queried. This parameter can be set to support only one domain name. If this parameter is left blank, all domain names belonging to the current user are queried.|
|EndTime|String|No|2015-11-29| -   The end time must be later than the start time.
-   The date format adopts ISO8601 notation and uses the UTC time.
-   Format: YYYY-MM-DDThh:mmZ.

 |
|StartTime|String|No|2015-11-28| -   Start time of data query.
-   The date format adopts ISO8601 notation and uses the UTC time.
-   Format: YYYY-MM-DDThh:mmZ.
-   The minimum data granularity is 1 hour.
-   If this parameter is left blank, data from the past 24 hours is read by default.

 |

## Return parameters {#section_sg3_wxm_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|BCD7D917-76F1-442F-BB75-C810DE34C761|The ID of the request.|
|DomainName|String|test.test.com|CDN domain name.|
|DataInterval|String|3600|Time interval.|
|StartTime|String|2015-11-28| Start time of data query. 

 The date format adopts ISO8601 notation and uses the UTC time.

 |
|EndTime|String|2015-11-29|End time of data query.|
|PvDataInterval| | |Data.|
|  └TimeStamp|String|2015-11-28T03:00:00Z|Time stamp.|
|  └Value|String|9292|Value.|

## Examples {#section_zmh_wnf_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com?Action=DescribeDomainPvData&DomainName=test.com
&StartTime=2015-11-28
&EndTime=2015-11-29
&public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "DataInterval":"3600",
        "DomainName":"test.com",
        "EndTime":"2015-11-29",
        "PvDataInterval":{
            "UsageData":[
                
                    "TimeStamp":"2015-11-28T03:00:00Z",
                    "Value":"9292"
                
                
                    "TimeStamp":"2015-11-28T23:00:00Z",
                    "Value":"9239"
                
                
                    "TimeStamp":"2015-11-28T07:00:00Z",
                    "Value":"9464"
                
                
                    "TimeStamp":"2015-11-28T12:00:00Z",
                    "Value":"9379"
                
                
                    "TimeStamp":"2015-11-28T22:00:00Z",
                    "Value":"9243"
                
                
                    "TimeStamp":"2015-11-28T10:00:00Z",
                    "Value":"10063"
                
                
                    "TimeStamp":"2015-11-28T15:00:00Z",
                    "Value":"9068"
                
                
                    "TimeStamp":"2015-11-28T14:00:00Z",
                    "Value":"9353"
                
                
                    "TimeStamp":"2015-11-28T04:00:00Z",
                    "Value":"9513"
                
                
                    "TimeStamp":"2015-11-28T02:00:00Z",
                    "Value":"9377"
                
                
                    "TimeStamp":"2015-11-28T08:00:00Z",
                    "Value":"9579"
                
                
                    "TimeStamp":"2015-11-28T20:00:00Z",
                    "Value":"9109"
                
                
                    "TimeStamp":"2015-11-28T09:00:00Z",
                    "Value":"10631"
                
                
                    "TimeStamp":"2015-11-28T06:00:00Z",
                    "Value":"9587"
                
                
                    "TimeStamp":"2015-11-28T01:00:00Z",
                    "Value":"9108"
                
                
                    "TimeStamp":"2015-11-28T16:00:00Z",
                    "Value":"9454"
                
                
                    "TimeStamp":"2015-11-28T21:00:00Z",
                    "Value":"9285"
                
                
                    "TimeStamp":"2015-11-28T19:00:00Z",
                    "Value":"9059"
                
                
                    "TimeStamp":"2015-11-28T00:00:00Z",
                    "Value":"9470"
                
                
                    "TimeStamp":"2015-11-28T05:00:00Z",
                    "Value":"11830"
                
                
                    "TimeStamp":"2015-11-28T13:00:00Z",
                    "Value":"9992"
                
                
                    "TimeStamp":"2015-11-28T17:00:00Z",
                    "Value":"9529"
                
                
                    "TimeStamp":"2015-11-28T18:00:00Z",
                    "Value":"9203"
                
                
                    "TimeStamp":"2015-11-28T11:00:00Z",
                    "Value":"9604"
                
            
        
        "RequestId":"BCD7D917-76F1-442F-BB75-C810DE34C761",
        "StartTime":"2015-11-28"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```



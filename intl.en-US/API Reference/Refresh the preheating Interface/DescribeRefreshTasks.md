# DescribeRefreshTasks {#reference_fx1_lrz_5db .reference}

Query whether or not refresh and push status have taken effect for the whole site.

-   Support task ID query and URL query.
-   If neither the taskid nor objectpath are specified, it will query the first page of data \(20 items\) within past 3 days by default.
-   A taskid and objectpath can be specified at the same time, with a logical relationship of AND.
-   Only the data within the past 3 days can be queried.

## Request parameters {#section_tbg_trz_5db .section}

|Parameters|Type|Required|Example values|Description|
|:---------|:---|:-------|:-------------|:----------|
|Action|String|Yes|DescribeRefreshTasks| The name of this interface.  Value:

 DescribeRefreshTasks

 |
|DomainName|String|No|www.yourdomain.com| The domain name.

 |
|EndTime|String|No|2017-12-22T08:00:00:00Z| The end time, the format is 2017-01-01T12:12:20Z.

 |
|ObjectPath|String|No|[http://aaa.com/1.txt](http://aaa.com/1.txt)| Query through an object path with exact match.

 |
|ObjectType|String|No|file| The task type.

-   file
-   path
-   preload

When the DomainName or TaskStatus is specified, the task type is required.

 |
|PageNumber|Integer|No|1| Page number.

 Value range: 1~100000Scope of value: 1 ~ 100000

 |
|PageSize|Integer|No|20| Paging size. Maximum: 50.

 Value range: random integer between 1 and 50.

 Default value: 20

 |
|ResourceGroupId|String|No|Your maid|The resource group ID.|
|StartTime|String|No|2017-12-21T08:00:00:00Z| The start time, the format is 2017-01-01T12:12:20Z.

 |
|Status|String|No|Complete| The task status.

-   Complete
-   Refreshing
-   Failed

 |
|TaskId|String|No|1234321| Query refresh status by task ID.

 |

## Return Parameters {#section_svv_htz_5db .section}

|Parameters|Type|Example values|Description|
|:---------|:---|:-------------|:----------|
|Tasks| | | The task list consisting of TaskItem.

 |
|└TaskId|String|704225667| The task ID.

 |
|└ObjectPath|String|[http://aaa.com/1.txt](http://aaa.com/1.txt)| Refresh the object path.

 |
| └Status|String|Complete| Status. Value:

-   Complete
-   Refreshing
-   Failed
-   Pending

 |
|└Process|String|100%| Process percentage.

 |
|  └ ObjectType|String|File| Task type.

-   file
-   path
-   preload

 |
|└ CreationTime|String|2014-11-27T08: 23: 22Z| Task object creation time, in UTC time.

 |
| └Description|String|Internal Error| Returned error description when push and refresh failed, currently including three errors:

-   Internal Error
-   Origin timeout
-   Origin Return StatusCode 5XX

 |
|PageSize|Long|1| The whole page size.

 |
|Pagenumber|Long|10| The page number.

 |
|TotalCount|Long|2| The total number of items.

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8| The ID of the request. 

 |

## Examples {#section_ugl_x5z_5db .section}

**Request example**

```
https://cdn.aliyuncs.com?&Action=DescribeRefreshTasks&ObjectPath=&PageNumber=1&PageSize=10&Public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "PageNumber": 1,
        "PageSize": 10,
        "RequestId":"174F6032-AA26-470D-B90E-36F0EB205BEE",
        "Tasks":{
            "CDNTask":[
                
                    "CreationTime": "2018-01-10T09:48:29Z",
                    "ObjectPath":"http://aaa.com/1.txt",
                    "ObjectType":"file",
                    "Process":"100%",
                    "Status":"Complete",
                    "TaskId":"704225667"
                
                
                    "CreationTime": "2018-01-10T09:48:29Z",
                    "Objectpath": "maid ",
                    "ObjectType":"file",
                    "Process":"100%",
                    "Status":"Complete",
                    "TaskId":"704222904"
                
            
        
        "TotalCount":2
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```



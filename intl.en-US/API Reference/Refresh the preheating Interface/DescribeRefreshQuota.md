# DescribeRefreshQuota {#reference_snj_mvz_5db .reference}

The maximum number of times of refreshing \(including pushing\) URLs and directories.

The remaining number of times of refreshing \(including pushing\) URLs and directories on the current day.

Restrictions:

-   Refresh and pushing interfaces include RefreshObjectCaches and PushObjectCache 

## Request parameters {#section_nrf_vvz_5db .section}

|Parameters|Type|Required|Instance Value|Description|
|:---------|:---|:-------|:-------------|:----------|
|Action|String|Yes|DescribeRefreshQuota| The name of this interface. Value: 

 DescribeRefreshQuota

 |

## Returns Parameters {#section_mtw_cwz_5db .section}

|Parameters|Type|Example values|Description|
|:---------|:---|:-------------|:----------|
|RequestId|String|42E0554B-80F4-4921-AED6-ACFB22CAAAD0| The ID of the request.

 |
|UrlQuota|String|2000| Maximum number of times of refreshing URLs.

 |
|DirQuota|String|100| Maximum number of times of refreshing directories.

 |
|UrlRemain|String|1996| Remaining number of times of refreshing URLs on the current day.

 |
|DirRemain|String|99| The amount of directory refresh remaining on the day.

 |
|Remaining number of times of refreshing directories on the current day|String|500|The maximum number of times of refreshing on the current day.|
|PreloadRemain|String|400|The remaining number of times of refreshing on the current day.|
|BlockQuota|String|300|The maximum number of times of block.|
|blockRemain|String|200|The remaining number of times of block.|

## Examples {#section_mdj_rwz_5db .section}

**Request example**

```
http://cdn.aliyuncs.com?Action=DescribeRefreshQuota&Public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "Dirquota": 100 ",
        "Dirremain": "99 ",
        "PreloadQuota":"500",
        "PreloadRemain":"400",
        "RequestId":"42E0554B-80F4-4921-AED6-ACFB22CAAAD0",
        "UrlQuota":"2000",
        "UrlRemain":"1996"
    
    ```


**Exception return format**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```



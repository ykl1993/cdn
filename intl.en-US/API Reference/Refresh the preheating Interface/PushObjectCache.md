# PushObjectCache {#reference_xv3_mpz_5db .reference}

Actively push content from the source site to the L2 Cache node. Upon first access, users can directly hit cache so as to relieve pressure on the source site.

Support post request, and the form is used for parameters.

Restrictions:

-   For a single ID, a daily maximum of cache push and refresh requests which can be submitted are as follows: URLs: 2,000.

    **Note:** Directory-level cache pushing is currently not supported.

-   Cache refresh and push interfaces include the  RefreshObjectCaches  and PushObjectCache.

## Request parameters {#section_t2d_2qz_5db .section}

|Parameters|Type|Required|Example Value|Description|
|:---------|:---|:-------|:------------|:----------|
|Action|String|Yes|PushObjectCache| The name of this interface. Value: 

 PushObjectCacheValue:

 |
|ObjectPath|String|Yes|Abc.com/image/1.png| Input example: bc.com/image/1.png, multiple URLs are separated by line break \(\\n or \\r\\n\).

 |

## Return parameters {#section_pvn_qqz_5db .section}

|Parameters|Type|Example values|Description|
|:---------|:---|:-------------|:----------|
|PushTaskId|String|95248880| The ID returned by the pushing task, multiple task IDs are separated by comma \(Half angle\).

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8| The ID of the request.

 |

## Examples {#section_add_xqz_5db .section}

**Request example**

```
https://cdn.aliyuncs.com?&Action=PushObjectCache&ObjectPath=test.test.com/test.txt&ObjectType=File&Public Request Parameter
```

**Normal return example**

-   JSON format

    ```
    
        "PushTaskId":"95248880",
        "RequestId":"E5BD4B50-7A02-493A-AE0B-97B9024B4135"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```



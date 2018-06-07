# Cache refresh {#reference_srr_cyc_5db .reference}

Update the file content on the node.

-   Update the cache node with the specified URL content, URL can be updated in batches.
-   Support post request, and the form is used for parameters.

Restrictions:

-   For a single ID, a daily maximum of cache push and refresh requests which can be submitted are as follows:
    -   URLs: 2,000.
    -   Directories: 100.
-   Cache refresh and push interfaces include the RefreshObjectCaches and PushObjectCache .

## Request Parameters {#section_rxs_wnz_5db .section}

|Parameters|Type|Required|Example values|Description|
|:---------|:---|:-------|:-------------|:----------|
|Action|String|Yes|RefreshObjectCaches| The name of this interface.  Value: 

 RefreshObjectCaches

 |
|ObjectPath|String|Yes|abc.com/image/1.png| Input example: abc.com/image/1.png, multiple URLs are required to be separated by line break \(\\n or \\r\\n\).

 |
|ObjectType|String|No|File| Optional, the refresh type. The value can be File or Directory.

 Default value: File.

 |

## Return Parameters {#section_vkr_f4z_5db .section}

|Parameters|Type|Example values|Description|
|:---------|:---|:-------------|:----------|
|Refreshtaskid|String|704222904| Refresh returned task ID, multiple task IDs are separated by comma \(Half angle\).

 |
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8| The ID of the request.

 |

## Examples {#section_fb4_44z_5db .section}

**Request example**

```
https://cdn.aliyuncs.com?&Action=RefreshObjectCaches&ObjectPath=test.test.com/test.txt&ObjectType=File&Public request parameter
```

**Example of normal return**

-   JSON format

    ```
    
        "RefreshTaskId":"704222904",
        "RequestId":"D61E4801-EAFF-4A63-AAE1-FBF6CE1CFD1C"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```



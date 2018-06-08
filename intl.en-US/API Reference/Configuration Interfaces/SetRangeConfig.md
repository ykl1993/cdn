# SetRangeConfig {#reference_h13_2yf_vdb .reference}

Set the range back-to-source function.

**Note:** To use the range back-to-source function, ensure that the source site supports range requests, indicating that the source site must be able to return correct 206 file slice for an HTTP request header containing a range field.

## Request parameters {#section_slq_3yf_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|SetRangeConfig|The name of this interface.  Value: SetRangeConfig|
|DomainName|String|Yes|www.macaron.org.cn|The accelerated domain name to turn on this feature.|
|Enable|字符串|Yes|On| Configure the range back to the source feature to turn on or off.

 Values: On, off

 |

## Response parameters {#section_xbc_lyf_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|Request ID|

## Examples {#section_pg5_myf_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com/?Action=SetRangeConfig
&Enable=on
&DomainName=www.macaron.org.cn
&Public request parameter
```

**Normal return example**

-   JSON format

    ```
    
        "RequestId":"04F0F334-1335-436C-A1D7-6C044FE73368"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    
    ```



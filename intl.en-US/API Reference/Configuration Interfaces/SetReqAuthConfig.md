# SetReqAuthConfig {#reference_y2t_lxg_vdb .reference}

Set CDN domain access authentication configuration.

-   [URL authentication](../../../../reseller.en-US/User Guide/Domain Names/Access Control Settings/Authentication configuration.md#).
-   Sample authentication code for python version.

## Request parameters {#section_gvp_cgl_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|SetReqAuthConfig|The name of this interface.  Value: SetReqAuthConfig|
|AuthType|String|Yes|no\_auth| Authorization type. Value:

 -   “no\_auth”: disabled
-   “type\_a”: Method A  
-   “type\_b”: Method B 
-   “type\_c”: Method C 
-   “type\_d”: Method D 
-   ”type\_e”: Method E 

 |
|DomainName|String|Yes|www.yourdomain.com|Your CDN domain name.|
|AuthRemoteDesc|String|No|aaa|Module string.|
|Key1|String|No|fd8eqw3Q|Main authentication key, consisting of upper and lowercase letters and numbers. The length is 1 to 64 characters.|
|Key2|String|No|v83ka2np|Standby authentication Key, consisting of upper and lowercase letters and numbers. The length is 1 to 64 characters.|
|TimeOut|String|No|2400|Effective time. Enter numbers.|

## Return parameters {#section_pkl_kgl_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|Request ID|

## Examples {#section_g1p_gcg_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com/?Action=SetReqAuthConfig
&DomainName=www.macaron.org.cn
&AuthType=type_a
&Key1=fd8eqw3Q
&Key2=v83ka2np
&TimeOut=2400
&public request parameter
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



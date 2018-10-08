# SetDynamicConfig {#reference_k2m_z25_vdb .reference}

Set the cache rules of Dynamic Route for Content Delivery Network \(DCDN\).

## Request parameters {#section_cmm_kh5_vdb .section}

|Parameters|Type|Required|Example values|Description|
|Action|String|Yes|Setdynamicconfig|The name of this interface. Value: SetDynamicConfig|
|DomainName|String|Yes|www.yourdomain.com|Your CDN domain name.|
|DynamicCacheControl|String|No|no-cache| Special header settings.

 -   Depending on the cache-control field in the Header, select whether to accelerate dynamically. Multiple are separated by spaces.
-   Example: no-cache no-store private

 |
|DynamicOrigin|String|No|http| Back-to-source routing scheme, supporting http, https, and follow.

 When left blank, the default value is http.

 |
|StaticPath|String|No|/Img| Static acceleration PATH. Multiple are separated by spaces.

 Example: \#path:/path/to/no\_dynamic\_route/.*.one*

 |
|StaticType|String|No|jpg| Static acceleration file suffix.

 Example:  ..\(jpg¦htmp¦txt\)$

 |
|StaticUri|String|No|/img/a.jpg| Static acceleration URI. Multiple are separated by spaces.

 Example: \#uri:/yyy/gggsssssssss/cxxxxxcc/a.txt

 |

## Return parameters {#section_bc2_nh5_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|Request ID|

## Examples {#section_sz4_ctt_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com/?Action=SetDynamicConfig
&DomainName=www.macaron.org.cn
&StaticType=. *\.(jpg|htmp|txt)$
&StaticUri=/ya/bc
&public request parameters
```

**Normal return example**

-   JSON format

    ```
    {
        "RequestId":"04F0F334-1335-436C-A1D7-6C044FE73368"
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



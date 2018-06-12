# Set up all-station accelerated cache rules {#reference_k2m_z25_vdb .reference}

All stations are accelerated to cache the configuration of the rule.

## Request parameters {#section_cmm_kh5_vdb .section}

|Name|Type|Must I choose?|Instance Value|Description|
|Action|String|Yes|Setdynamicconfig|The system sets parameters. Value: setdynamicconfig|
|Domainname|String|Yes.|www.yourdomain.com|Your accelerated domain name.|
|Dynamiccachecontrol|String|No|No-Cache| Special header settings.

 -   Depending on the cache-control field in the header, select whether to accelerate dynamically. Multiple spaces are separated.
-   Example: No-Cache no-store private

 |
|Dynamic Origin|String|No|HTTP| Backsource routing scheme, which supports HTTP, https, and follow.

 When not filled, the default is HTTP 

 |
|Staticpath|String|No|/Img| Static acceleration path  Multiple spaces are separated.

 Example: \# path:/path/to/FIG/.. One

 |
|Statictype|String|No|JPG| Static acceleration file suffix.

 For example:... \(JPG ¦ htmp ¦ txt\) $

 |
|Statici|String|No|/Img/a.jpg| Static accelerated Uris. Multiple spaces are separated.

 Example: \# URI:/YYY/FIG/maid/a.txt

 |

## Response parameters {#section_bc2_nh5_vdb .section}

|Parameters|Type|Example values|Description|
|RequestID|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|Request ID|

## Examples {#section_sz4_ctt_vdb .section}

**Request example**

```

Http://cdn.aliyuncs.com /? Action = setdynamicconfig
& Domainname = maid
& Statictype =. * \. (JPG | html dp | txt) $
& Statici =/Ya/BC
&CommonParameters
```

**Example of normal return**

-   JSON format

    ```
    
        "Requestid": "maid"
    
    ```


**Exception return example**

-   JSON format

    ```
    
        "Code": "internalerror ",
        "Hostid": "maid ",
        "Message:" The request processing has failed due to some unknown error .",
        "Requestid": "maid"
    
    ```



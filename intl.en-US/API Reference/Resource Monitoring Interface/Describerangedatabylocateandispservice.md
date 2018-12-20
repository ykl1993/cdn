# Describerangedatabylocateandispservice {#reference_uq1_x4n_vdb .reference}

Gets bandwidth data on different locates and ISPs for an accelerated domain name at a certain time, in the following units: bit/second.

-   Batch domain name queries are not supported.
-   The time is accurate to 5 minutes of granularity.

## Request parameters {#section_dqg_dpn_vdb .section}

|Name|Type|Must I choose?|Instance Value|Description|
|Action|String|Yes|Describerangedatabylocateandispservice|The system sets parameters. Value: Describerangedatabylocateandispservice|
|Endtime|String|Yes.|Tes 22t08: 00: 00: 00Z| End Time.

 -   Date is in ISO8601 format, and must use UTC time.
-   Format: YYYY-MM-DDThh:mmZ.

 |
|StartTime|String|Yes.|2016-08-01T22: 00Z| Start time.

 -   The date format follows the iso8601 representation and uses UTC time.
-   Format: yyyy-mm-ddthh: mmz.
-   The minimum data granularity is 5 minutes.

 |
|Domainnames|String|No|Abc.com|The domain name to query cannot be empty.|
|Ispnames|String|No|Unicom, Telecom| You need to query the target ISP list, separated by ',', and cannot be empty.

 The ISP name is obtained via the maid interface.

 |
|Locationnames|String|No|Liaoning, Guangxi| You need to query the target area list, separated by ',' and cannot be empty.

 The location name is obtained through the maid interface.

 |

## Response parameters {#section_pwk_bns_vdb .section}

|Parameters|Type|Example values|Description|
|RequestId|String|16A96B9A-F203-4EC5-8E43-CB92E68F4CD8|The ID of the request.|
|Jsonresult|String|\{1505973300: \{Sudan: \{Other: \{http\_codes ": \{"000": 0, "200": 6, "400": 0 \}, "RT": 4183, "Bandwidth": 46639, "avg\_speed": 7773, "PV": 6, "hit\_rate": 0.93, "request\_hit\_rate ": 0.66 \}\}\}\}|Returns result in JSON format.|

## Examples {#section_uz2_x1n_vdb .section}

**Request example**

```

Http://cdn.aliyuncs.com? Action = fig & domainnames = abc.com
& Locationnames = liaining, Guangxi
& Ispnames = Unicom, Telecom
& StartTime = 2016-08-01T22: 00Z
& Endtime = MAID: 00Z
&CommonParameters
```

**Example of normal return**

**Exception return example**

-   JSON format

    ```
    
        "Code": "internalerror ",
        "Hostid": "maid ",
        "Message:" The request processing has failed due to some unknown error .",
        "Requestid": "maid"
    
    ```



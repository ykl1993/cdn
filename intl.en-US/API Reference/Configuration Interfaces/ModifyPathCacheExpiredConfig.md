# ModifyPathCacheExpiredConfig {#reference_rc4_pgg_vdb .reference}

You can modify the path cache policy by this interface.

## Request parameters {#section_rqy_fhg_vdb .section}

|Parameter |Type|Required|Description|
|:---------|:---|:-------|:----------|
|Action|String|Yes|The name of this interface. Value: ModifyPathCacheExpiredConfig|
|Domainname|String|Yes|Your CDN domain name.|
|ConfigID|String|Yes|Configuration ID to be modified|
|CacheContent|String|Yes|Path|
|TTL|String|Yes| Cache time \(unit: second\).|
|Weight|String|No|Weight of the configuration. The value range is 1 ~ 99. A larger value indicates a higher priority.  The default value is 1.|

## Response parameters {#section_sf5_xhg_vdb .section}

|Parameters|Type|Description|
|:---------|:---|:----------|
|RequestID|String|Request ID of the task|

## Example  {#section_g1p_gcg_vdb .section}

**Request example**

```

http://cdn.aliyuncs.com/?Action=ModifyPathCacheExpiredConfig
&CacheContent=%2Fstatic%2Fhtml%2F
&DomainName=www.macaron.org.cn
&TTL=600
&Weight=50
&ConfigID=905535
&Public request parameter
```

**Response example**

JSON format

```

    "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368"

```

XML format

```

AED00EC1-32A8-4D48-BEB9-BD782AF3C6BD

```

## Error codes {#section_c2n_b3g_vdb .section}

Error codes specific to this interface are as follows. For more error codes, see [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).

|Error code|Error message|HTTP status code |Meaning|
|:---------|:------------|:----------------|:------|
|InvalidCacheContent.Malformed|The specified value of parameter CacheContent is malformed.|400|The specified CacheContent value is invalid because it is in incorrect format.|
|InvalidWeight.ValueNotSupported|The specified value of parameter Weight is not supported.|400|The specified Weightis invalid because it is out of the valid range.|


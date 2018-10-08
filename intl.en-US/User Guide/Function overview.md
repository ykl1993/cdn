# Function overview {#concept_tvm_vhx_wdb .concept}

## HTTPS secure acceleration {#section_l1w_tlx_wdb .section}

|Function|Description|Default |
|:-------|:----------|:-------|
|[HTTPS secure acceleration](reseller.en-US/User Guide/Domain Names/HTTPS Acceleration/HTTPS Secure Acceleration.md#)|Provides a full link HTTPS secure acceleration scheme, just upload the CDN domain name certificate/private key after you activate secure acceleration mode, and supports viewing, disabling, enabling, editing of certificates.|Disabled|
|[Force redirect](reseller.en-US/User Guide/Domain Names/HTTPS Acceleration/Force Redirect.md#)|When the "HTTPS secure acceleration" is enabled, the CDN domain name supports custom settings, and redirect the user's original request in a forcible way. |Disabled|

## Back-to-source settings {#section_rq4_5lx_wdb .section}

|Function|Description|Default |
|:-------|:----------|:-------|
|[Back-to-source  host](reseller.en-US/User Guide/Domain Names/Content back-to-source settings/Back-to-source host.md#)|Specifies the host domain name that a CDN node accesses in the back-to-source process. Three options are available: CDN domain name, original site domain name, and custom domain name.|CDN domain name|
|[Back-to-source with the same protocol](reseller.en-US/User Guide/Domain Names/Content back-to-source settings/Back-to-origin with the Same Protocol.md#)|Back-to-source requests for resources use exactly the same protocol as used by the client to request the resources.|Disabled|

## Cache settings {#section_j4q_5lx_wdb .section}

|Function|Description|Default  |
|:-------|:----------|:--------|
|[Cache expiration time](reseller.en-US/User Guide/Domain Names/Node Cache Settings/Cache Configuration.md#)|Customizes cache expiration rules for specified resources.|Disabled|
|[Setting the HTTP Request Header](reseller.en-US/User Guide/Domain Names/Node Cache Settings/Set the HTTP Response Header.md#)|Sets an HTTP request header. Nine parameters are currently available for HTTP request header customization.|Disabled|
|[Custom 404 page](reseller.en-US/User Guide/Domain Names/Node Cache Settings/Customize the 404 page.md#)|Available in three options: default 404, public welfare 404, custom 404|Default 404 page|

## Access control {#section_vc4_cmx_wdb .section}

|Function|Description|Default  |
|:-------|:----------|:--------|
|[Anti-leech](reseller.en-US/User Guide/Domain Names/Access Control Settings/Anti-leech.md#)|Configures a referer blacklist or whitelist to identify and filter visitors.|Disabled|
|[URL authentication](reseller.en-US//URL authentication.md#)|Uses URL authentication methods to protect resources on an origin site.|Disabled|
|[IP blacklist](reseller.en-US/User Guide/Domain Names/Access Control Settings/IP Blacklist and Whitelist.md#)|Configures the access IP blacklist to identify and filter visitors. |Disabled|

## Performance optimization {#section_ev4_cmx_wdb .section}

|Function|Description|Default |
|:-------|:----------|:-------|
|[Page optimization](reseller.en-US/User Guide/Domain Names/Performance Optimization settings/Page Optimization.md#)|Compresses and removes useless blank lines and carriage return characters to effectively reduce the page size.|Disabled|
|[Smart compression](reseller.en-US/User Guide/Domain Names/Performance Optimization settings/Smart Compression.md#)|Supports smart compression for content in multiple formats to effectively reduce the size of user transmitted content.|Disabled|
|[Filter parameter](reseller.en-US/User Guide/Domain Names/Performance Optimization settings/Filter Parameter.md#)|Removes parameters after ? in a URL request   during the back-to-source process.|Disabled|

## Video-related settings {#section_is2_hmx_wdb .section}

|Function|Description|Default |
|:-------|:----------|:-------|
|[Back-to-source of range](reseller.en-US/User Guide/Domain Names/Video Service Configuration/Back-to-origin of range.md#)|Allows a user to notify an origin site server to return partial content within a specified range. This function helps with accelerated delivery of large files.|Disabled|
|[Drag/drop playback](reseller.en-US/User Guide/Domain Names/Video Service Configuration/Drag/Drop Playback.md#)|Enables random drag or drop playback in a video or audio on-demand scenario.|Disabled|
|[Notify\_URL](reseller.en-US/User Guide/Domain Names/Video Service Configuration/Notify_URl Setting.md#)| 【Applicable to Live】Real-time information callback of stream status, promptly notifies users about the operation results of streaming or stream disconnection.|Disabled|

## Other settings {#section_ihf_hmx_wdb .section}

|Function|Description|Default |
|:-------|:----------|:-------|
|[Set httpDNS](reseller.en-US/User Guide/Set httpDNS.md#)|Provides a DNS service by using the HTTP protocol to directly access the server of Alibaba Cloud CDN.|Disabled|


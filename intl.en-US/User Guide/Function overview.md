# Function overview {#concept_tvm_vhx_wdb .concept}

## HTTPS secure acceleration {#section_l1w_tlx_wdb .section}

|Function|Description|Default |
|:-------|:----------|:-------|
|[HTTPS secure acceleration](intl.en-US/User Guide/Value-added service/HTTPS Acceleration/HTTPS Security Acceleration.md#)|Provides a full link HTTPS secure acceleration scheme, just upload the CDN domain name certificate/private key after you activate secure acceleration mode, and supports viewing, disabling, enabling, editing of certificates.|Disabled|
|[Force redirect](intl.en-US/User Guide/Value-added service/HTTPS Acceleration/Force Redirect.md#)|When the "HTTPS secure acceleration" is enabled, the CDN domain name supports custom settings, and redirect the user's original request in a forcible way. |Disabled|

## Back-to-source settings {#section_rq4_5lx_wdb .section}

|Function|Description|Default |
|:-------|:----------|:-------|
|[Back-to-source  host](intl.en-US/User Guide/Content back-to-source settings/Back-to-source host.md#)|Specifies the host domain name that a CDN node accesses in the back-to-source process. Three options are available: CDN domain name, original site domain name, and custom domain name.|CDN domain name|
|[Back-to-source with the same protocol](intl.en-US/User Guide/Content back-to-source settings/Back-to-source with the same protocol.md#)|Back-to-source requests for resources use exactly the same protocol as used by the client to request the resources.|Disabled|

## Cache settings {#section_j4q_5lx_wdb .section}

|Function|Description|Default  |
|:-------|:----------|:--------|
|[Cache expiration time](intl.en-US/User Guide/Node Cache Settings/Cache policy configuration.md#)|Customizes cache expiration rules for specified resources.|Disabled|
|[Setting the HTTP Request Header](intl.en-US/User Guide/Node Cache Settings/Set the HTTP Response Header.md#)|Sets an HTTP request header. Nine parameters are currently available for HTTP request header customization.|Disabled|
|[Custom 404 page](intl.en-US/User Guide/Node Cache Settings/Customize the 404 page.md#)|Available in three options: default 404, public welfare 404, custom 404|Default 404 page|

## Access control {#section_vc4_cmx_wdb .section}

|Function|Description|Default  |
|:-------|:----------|:--------|
|[Anti-leech](intl.en-US/User Guide/Access Control Settings/Anti-leech.md#)|Configures a referer blacklist or whitelist to identify and filter visitors.|Disabled|
|[URL authentication](intl.en-US/User Guide/Access Control Settings/URL authentication.md#)|Uses URL authentication methods to protect resources on an origin site.|Disabled|
|[IP blacklist](intl.en-US/User Guide/Access Control Settings/IP blacklist.md#)|Configures the access IP blacklist to identify and filter visitors. |Disabled|

## Performance optimization {#section_ev4_cmx_wdb .section}

|Function|Description|Default |
|:-------|:----------|:-------|
|[Page optimization](intl.en-US/User Guide/Performance Optimization settings/Page optimization.md#)|Compresses and removes useless blank lines and carriage return characters to effectively reduce the page size.|Disabled|
|[Smart compression](intl.en-US/User Guide/Performance Optimization settings/Smart compression.md#)|Supports smart compression for content in multiple formats to effectively reduce the size of user transmitted content.|Disabled|
|[Filter parameter](intl.en-US/User Guide/Performance Optimization settings/Filter parameter.md#)|Removes parameters after ? in a URL request   during the back-to-source process.|Disabled|

## Video-related settings {#section_is2_hmx_wdb .section}

|Function|Description|Default |
|:-------|:----------|:-------|
|[Back-to-source of range](intl.en-US/User Guide/Video Service Configuration/Back-to-source of range.md#)|Allows a user to notify an origin site server to return partial content within a specified range. This function helps with accelerated delivery of large files.|Disabled|
|[Drag/drop playback](intl.en-US/User Guide/Video Service Configuration/Drag/Drop playback.md#)|Enables random drag or drop playback in a video or audio on-demand scenario.|Disabled|
|[Notify\_URL](intl.en-US/User Guide/Video Service Configuration/Notify_URl Setting.md#)| 【Applicable to Live】Real-time information callback of stream status, promptly notifies users about the operation results of streaming or stream disconnection.|Disabled|

## Other settings {#section_ihf_hmx_wdb .section}

|Function|Description|Default |
|:-------|:----------|:-------|
|[Set httpDNS](intl.en-US/User Guide/Set httpDNS.md#)|Provides a DNS service by using the HTTP protocol to directly access the server of Alibaba Cloud CDN.|Disabled|


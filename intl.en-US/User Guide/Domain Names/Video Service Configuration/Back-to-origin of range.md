# Back-to-origin of range {#concept_zrw_s1f_xdb .concept}

## Introduction {#section_prj_v1f_xdb .section}

The Back-to-origin of Range function allows a client to notify an origin site server to return partial content within a specified range. It accelerates delivery of large files by reducing the consumption of back-to-origin traffic and improving the resource response speed.

The origin site must support the range request, that is, the range field is included in the HTTP request header, and the origin site can respond to the correct 206 file slice.

|When the Back-to-origin of Range is|Description|Instances|
|-----------------------------------|-----------|---------|
|Enable|A parameter request can be returned to an origin site. In this case, based on the Range parameter, the origin site returns the file byte range, while the CDN node returns the content in the byte range to the client.|If a request sent from a client to a CDN node contains range:0-100, the range:0-100 parameter will also be contained in the request received on the origin site.  When the origin site returns the parameter content to the CDN node, the node returns the content in 101 bytes ranging from 0 to 100 to the client.|
|Disable|A CDN higher-level node requests an origin site for all files. However, the requested files will not be cached on the CDN node because a client will automatically disconnect HTTP links after receiving bytes specified by Range. This causes a low cache hit rate and large back-to-origin traffic.|If a request sent from a client to a CDN node contains range:0-100, the range:0-100 parameter will not be contained in the request received on the server. The origin site will return a complete file to the CDN node and the CDN node will return only 101 bytes to the client. However, the file cannot be cached on the CDN node because the link is disconnected.|

**Note:** To use the Back-to-origin of Range function, an origin site must support Range requests, meaning that the origin site must be able to return correct 206 Partial Content for an HTTP request header containing a Range field.

## Procedure {#section_cxc_bbf_xdb .section}

Back-to-origin of Range feature is optional and is disabled by default. You can change the configuration to enable it.

1.  Go toDomain Namepage,selete your domain name, and click **Manage**.
2.  Click **Modify Configuration** in **Video-related** \> **Back-to-origin of Range**.
3.  Select **Enable**, **Disable** or **Force**.

Go to the CDN domain name management page, click **Configure**, select **Enable/Disable/Force** Back-to-origin of Range function.

**Note:** You can enable **Force** if your origin site is capable of using this feature. After enabling it, all requests will be forced to perform Back-to-origin of range.

See [Back-to-origin of Range](../../../../../reseller.en-US/API Reference/Configuration Interfaces/SetRangeConfig.md#) for more API information.


# Type 4: Live Streaming Media Acceleration {#concept_mmy_wfk_xdb .concept}

## Use cases {#section_yqj_yfk_xdb .section}

High-performance and stable live broadcast technical support is provided for video broadcast platforms, including interactive online educational websites, live broadcast gaming sites, personal live shows, and live broadcast platforms of event or vertical industry type.  RTMP, HLS, and FLV live broadcasts. Currently, acceleration is applicable to`RTMP`, `HLS` and `FLV`live broadcasts.

## Procedure {#section_w2r_zfk_xdb .section}

1.  See

    Please refer [Quick Start.](../../../../reseller.en-US/Quick Start/Quick start.md#). Make sure you select**Acceleration of live streaming media**for the business type.

    **Note:** This business type does not support the custom live streaming server. The origin site address**live-origin.alivecdn.com** of the Alibaba Cloud CDN live broadcast center is used.

2.  Stream push instructions

    Stream push address

    ```
    rtmp://video-center.alivecdn.com/app-name/video-name? vhost=test.example.com
    ```

    Operation on the console: Select the CDN domain for live broadcast in**Domain Name Management** to go to the configuration page:

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5123/15389982983633_en-US.png)

    **Note:** 

    -   By default, the number of pushed streams is limited to 20.
    -   video-center.alivecdn.com is the domain name of the live streaming server. At present, it does not support customization.
    -   app-name indicates the application name. Customization is supported. The application name may include letters, numbers, and underscores. Special characters are not allowed. Modification is supported. The length must not exceed 255 characters.
    -   video-name indicates the stream name. Customization is supported. The stream name may include letters, numbers, and underscores. Special characters are not allowed. Modification is supported. The length cannot exceed 255 characters.
    -   vhost indicates the final domain name for broadcast on the edge node, that is, your CDN domain \(For example: test.example.com\).
3.  Stream playback instructions

    Based on the pushed streams, three reading modes are supported on edge nodes:

    |Mode|URL|
    |:---|:--|
    |RTMP|`rtmp://test.example.com/app-name/video-name`|
    |FLV|`http://test.example.com/app-name/video-name.flv`|
    |M3U8|`http://test.example.com/app-name/video-name.m3u8`|

    The following figure shows the location of a stream push address on the console.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5123/15389982983634_en-US.png)

4.  Domain name configuration

    After the domains are added, use the appropriate feature to configure the CDN domains based on your business needs. All domain configurations are optional. The following configurations are recommended for the acceleration of “live streaming media”.

    -   [Authentication settings](reseller.en-US//URL authentication.md#): The URL authentication feature is implemented by collaboration between the Alibaba Cloud CDN nodes and client resource sites to provide a more secure and reliable way to protect origin server resources from theft.

        **Note:** 

        -   Currently, the same authentication scheme is adopted for stream push and stream playback.
        -   The CDN domain performs stream push and playback only after authentication configuration is completed. Currently, the live broadcast business type supports the A-type authentication method only.
        -   The streaming and playback addresses must receive authentication signature calculations respectively. Every signature is calculated based on the URL strictly, so you cannot apply the signature calculated from the streaming URL to the playback address. Similarly, different stream playback addresses correspond to different authentication calculation results.
        -   During signature calculation, no parameter is included in the URL. For example, during calculation of authentication signature for stream push is not included`? vhost=test.yourcompany.com`
        Example:

        |Step|Content|
        |:---|:------|
        |Resource URL|`rtmp://video-center.alivecdn.com/app-name/video-name`|
        |Authorization settings| Authentication method: Method A Authentication key: test123 valid time: 3,600s|
        |Stream push address|`rtmp://video-center.alivecdn.com/app-name/video-name? auth_key=1449030595-0-0-dee5f3819d7b62a9830ee2913caf111c&vhost=test.example.com`|
        |Stream playback address \(take the FLV format as an example\)|`http://test.example.com/app-name/video-name.flv?auth_key=1449030834-0-0-5e1c604710241001fd7a367bc96a17b7`|

    -   Notify\_url settings, flow status real-time feedback, send a GET request to the user server through the HTTP interface, real-time feedback to the user on the status of successful streaming and successful streaming of video, the user server returns the result by 200 response to the interface returned by default. 1 indicates a success in receiving; 0 indicates a failure in receiving.


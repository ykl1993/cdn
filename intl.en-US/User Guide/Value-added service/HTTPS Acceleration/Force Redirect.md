# Force Redirect {#concept_tyh_4rl_xdb .concept}

## Features {#section_sms_prl_xdb .section}

-   When **HTTPS Secure Acceleration** is enabled for a CDN domain, it supports custom settings to perform force redirects on users’ original request methods.
-   For example, when **force HTTPS** redirect is enabled and a user initiates an HTTP request, the server returns a 302 redirect response and the original HTTP request is forcibly redirected to an HTTPS request, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5136/3707_en-US.png)


## Note {#section_vwb_5rl_xdb .section}

-   Enabling **HTTPS Secure Acceleration** is required.
-   Both HTTP and HTTPS requests are supported by default.

## Configuration guide {#section_upx_5rl_xdb .section}

-   **Force Redirect** is an optional configuration and supports both HTTP and HTTPS requests by default.
-   Options: **default**, **force HTTPS redirect**, and **force HTTP redirect**.
    -   **Force HTTPS redirec**t: User requests are forcibly redirected to HTTPS requests.
    -   **Force HTTP redirect**: User requests are forcibly redirected to HTTP requests.
-   Change configuration:

    CDN domain management page—\>Choose a domain to enter the configuration page—\>HTTPS settings—\>Force redirect—\>Modify configuration. You can specify the force redirect type at the lower part of the settings page.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5136/3708_en-US.png)



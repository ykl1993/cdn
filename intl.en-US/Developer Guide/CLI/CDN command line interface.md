# CDN command line interface {#concept_pcn_x2m_xdb .concept}

## aliyuncli installation {#section_gg2_bgm_xdb .section}

aliyuncli is a tool based on Alibaba Cloud open APIs. With this tool, you can easily call Alibaba Cloud open API to manage your Alibaba Cloud product. Aliyuncli commands correspond to Alibaba Cloud open APIs in a one-to-one manner, and delivers robust flexibility and scalability at an equal capacity. Based on aliyuncli, you can encapsulate Alibaba Cloud atomic APIs to obtain your desired functions.

**Note:** pip The pip-installed aliyuncli will automatically process various dependencies.

-   You can install aliyuncli directly using the following command:

    ```
    $sudo pip install aliyuncli
    ```

-   aliyuncli upgrades:

    ```
    $sudo pip install --upgrade aliyuncli
    ```

-   For more information, see[Alibaba Cloud CLI](https://docs.aliyun.com/?spm=5176.1970908.105.1.kBS7lo#/pub/aliyun-command-line-interface).

## CDN SDK installation {#section_c31_3gm_xdb .section}

The CDN SDK must be installed because CDN functions are used alongside it.

**Note:**  The SDK will automatically process various dependencies and upgrades,  therefore, it is strongly recommended to install SDKs using pip.

-   Install the CDN SDK directly using the following command :

    ```
    $ sudo pip install aliyun-python-sdk-cdn
    ```

-   SDK upgrades:

    ```
    $ sudo pip install --upgrade aliyun-python-sdk-cdn
    ```


## aliyuncli CDN command descriptions {#section_fgk_ngm_xdb .section}

**Service operation commands**

**OpenCdnService**

-   Command instructions:

    Domain name operations can only be performed after the CDN service has been activated. A single user can only activate the service once. The account will activate only if it has been verified with real-name authentication.

-   Example:

    ```
    aliyuncli cdn OpenCdnService --InternetChargeType PayByTraffic
    ```


**DescribeCdnService**

-   Command instructions:

    Querying the CDN service status will include the current billing type, service activation time, the billing type that will take effect next, and the current service status.

-   Example:

    ```
    aliyuncli cdn DescribeCdnService
    ```


**ModifyCdnService**

-   Command instructions:

    Changes the CDN service billing type.

-   Example:

    ```
    aliyuncli cdn ModifyCdnService --InternetChargeType PayByTraffic
    ```


For more information about APIs, see[API Reference](https://docs.aliyun.com/#/pub/cdn/api-reference/overview).


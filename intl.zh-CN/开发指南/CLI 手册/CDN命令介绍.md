# CDN命令介绍 {#concept_pcn_x2m_xdb .concept}

## aliyuncli 安装 {#section_gg2_bgm_xdb .section}

阿里云命令行工具\(aliyuncli\)是基于阿里云开放API建立的手边管理工具。借助这个工具，您可以轻松的调用阿里云开放API，管理您的阿里云产品。阿里云命令行工具与阿里云open API一一对应，灵活性高且易于扩展。您可以基于阿里云命令行工具对阿里云原子的API进行封装，扩展出自己想要的功能。

**说明：** pip 安装阿里云命令行工具会自动帮助您处理好各种依赖。

-   您可以直接采用下面的命令安装aliyuncli：

    ```
    $sudo pip install aliyuncli
    ```

-   aliyuncli 升级：

    ```
    $sudo pip install --upgrade aliyuncli
    ```

-   更多产品细节, 请参考：[CLI产品文档](https://docs.aliyun.com/?spm=5176.1970908.105.1.kBS7lo#/pub/aliyun-command-line-interface)。

## CDN SDK安装 {#section_c31_3gm_xdb .section}

使用CDN的功能，需要与CDN SDK配合使用，因此需要您安装CDN SDK。

**说明：** pip 安装SDK会自动帮助您处理好各种依赖还有升级, 因此强烈建议您采用pip方式安装SDK。

-   您可以直接采用下面的命令安装CDN SDK：

    ```
    $ sudo pip install aliyun-python-sdk-cdn
    ```

-   SDK升级：

    ```
    $ sudo pip install --upgrade aliyun-python-sdk-cdn
    ```


## aliyuncli cdn 命令说明 {#section_fgk_ngm_xdb .section}

**服务操作命令**

**OpenCdnService**

-   命令说明：

    开通CDN服务，只有开通后，才能进行域名操作，一个用户只能开通一次。开通条件：帐号已通过实名认证。

-   使用示范：

    ```
    aliyuncli cdn OpenCdnService --InternetChargeType PayByTraffic
    ```


**DescribeCdnService**

-   命令说明：

    查询CDN服务状态。包括当前计费类型，服务开通时间，下次生效的计费类型，当前业务状态等。

-   使用示范：

    ```
    aliyuncli cdn DescribeCdnService
    ```


**ModifyCdnService**

-   命令说明：

    变更CDN服务的计费类型。

-   使用示范：

    ```
    aliyuncli cdn ModifyCdnService --InternetChargeType PayByTraffic
    ```


更多 API 接口详细信息，请进入[API 手册](https://docs.aliyun.com/#/pub/cdn/api-reference/overview)了解详情。


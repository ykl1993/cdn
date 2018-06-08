# HTTPS安全加速设置 {#concept_rns_qvk_xdb .concept}

## 功能介绍 {#section_ynt_mnl_xdb .section}

-   HTTPS是以安全为目标的HTTP通道，简单讲是HTTP的安全版。即将HTTP用SSL/TLS协议进行封装，HTTPS的安全基础是SSL/TLS。
-   HTTPS加速优势：
    -   传输过程中对用户的关键信息进行加密，防止类似Session ID或者Cookie内容被攻击者捕获造成的敏感信息泄露等安全隐患；
    -   传输过程中对数据进行完整性校验，防止DNS或内容遭第三方劫持、篡改等中间人攻击（MITM）隐患，了解更多[使用HTTPS防止流量劫持](http://yq.aliyun.com/articles/2666)
-   阿里云CDN 提供HTTPS安全加速方案，仅需开启HTTPS后上传证书和私钥，并支持对证书进行查看、停用、启用、编辑操作。用户自定义上传的证书仅支持PEM格式的证书，具体请看 [证书格式说明及转化方法](cn.zh-CN/用户指南/增值服务/HTTPS安全加速/证书格式说明.md#)。
-   您可以在[阿里云云盾](https://yundun.console.aliyun.com)快速申请免费的证书或购买高级证书。
-   证书配置正确及开启状态，同时支持HTTP访问和HTTPS访问；证书不匹配或者停用证书，仅支持HTTP访问。

**说明：** 目前不支持sni 回源。

## 功能示意图 {#section_pcc_snl_xdb .section}

在阿里云CDN控制台开启的HTTPS，将实现用户和阿里云CDN节点之间请求的HTTPS加密。而CDN节点返回源站获取资源的请求仍按您源站配置的方式进行，建议您源站也配置并开启HTTPS，实现全链路的HTTPS加密：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5134/3698_zh-CN.png)

## 注意事项 {#section_z5h_xnl_xdb .section}

配置相关

-   支持**开启HTTPS安全加速**功能的业务类型为：
    -   图片小文件加速
    -   大文件下载加速
    -   视音频点播加速
    -   直播流媒体加速
    -   暂不支持移动加速业务类型
-   支持泛域名HTTPS服务。
-   支持该功能的**停用**和**启用**：
    -   启用：支持修改证书，默认兼容用户的HTTP和HTTPS请求，支持**强制跳转**设置。
    -   停用：不支持HTTPS请求且将不再保留证书/私钥信息，再次开启证书，需要重新上传证书/私钥。
-   允许用户查看证书，但是只支持查看证书，由于私钥信息敏感不支持私钥查看，请妥善保管证书相关信息。
-   支持修改编辑证书，但注意生效时间大约为10分钟，请慎重操作。

计费相关

HTTPS安全加速属于增值服务，开启后将产生HTTPS请求数计费，当前计费标准详见 [HTTPS计费详情](https://www.aliyun.com/price/product?spm=5176.doc27271.2.9.vAt4dL#/cdn/detail)。

**说明：** 

-   HTTPS根据请求数单独计费，费用不包含在CDN流量包内，请确保账户余额充足再开通HTTPS服务，以免HTTPS服务导致欠费影响CDN服务。
-   附：[如何查看HTTPS请求数使用情况](../cn.zh-CN/.md#)。

证书相关

-   开启**HTTPS安全加速**功能的加速域名，须要上传证书，包含证书/私钥，均为 PEM 格式。

    **说明：** CDN采用的Tengine服务是基于Nginx的，因此只支持Nginx能读取的证书，即PEM格式\)。具体请看 [证书格式说明及转化方法](cn.zh-CN/用户指南/增值服务/HTTPS安全加速/证书格式说明.md#)。

-   只支持带SNI信息的SSL/TLS握手。
-   用户上传的证书和私钥要匹配，否则会校验出错。
-   更新证书的生效时间约为10分钟。
-   不支持带密码的私钥。

## 配置引导 {#section_p3r_l4l_xdb .section}

1.  购买证书。开启HTTPS安全加速，需要您具备匹配加速域名的证书，可以在 [阿里云云盾](https://yundun.console.aliyun.com) 快速申请免费的证书或购买高级证书。
2.  加速域名配置。

    登录[CDN控制台](https://cdn.console.aliyun.com)，进入CDN域名列表页，选择域名进入配置页面，HTTPS设置，修改配置。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5134/3699_zh-CN.png)

    单击**修改配置**，可以进行相应设置：

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5134/3700_zh-CN.png)

    1.  确认当前域名**HTTPS设置**是否开启，单击**修改配置**按钮进入设置界面并**开启**。

        **说明：** HTTPS安全加速属于增值服务，开启后将产生HTTPS请求数计费，了解[计费详情](https://cn.aliyun.com/price/product?spm=5176.8232292.0.0.tGqYZq#/cdn/detail)。

    2.  选择证书：
        -   可在[阿里云云盾证书服务](https://yundun.console.aliyun.com)快速申请免费证书或购买高级证书， 云盾的证书，可以通过证书名称直接选择适配该加速域名；
        -   若证书列表中无当前适配的证书可以选择自定义上传，需要设置证书名称后上传证书内容和私钥，该证书将会在“云盾证书服务”中保存，可以在**我的证书**部分查看。
    3.  仅支持 PEM 的证书格式。具体请看 [证书格式说明及转化方法](cn.zh-CN/用户指南/增值服务/HTTPS安全加速/证书格式说明.md#)。
    4.  支持**设置强制跳转**：自定义将用户的原请求方式进行强制跳转：
        -   例如开启**强制HTTPS跳转**后，用户发起了一个HTTP请求，服务端返回302重定向响应，原来的HTTP请求强制重定向为HTTPS请求。
        -   默认：兼容用户的HTTP和HTTPS请求。
        -   强制HTTPS跳转：用户的请求将强制重定向为HTTPS请求。
        -   强制HTTP跳转：用户的请求将强制重定向为HTTP请求。
3.  验证证书是否生效。

    设置完成待证书生效后（设置HTTPS证书后约1小时后生效），使用HTTPS方式访问资源，如果浏览器中出现绿色HTTPS标识，表明当前与网站建立的是私密连接，HTTPS安全加速生效。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5134/3701_zh-CN.png)



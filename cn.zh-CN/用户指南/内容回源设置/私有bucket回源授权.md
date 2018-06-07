# 私有bucket回源授权 {#concept_ljh_42y_wdb .concept}

## 功能介绍 {#section_zvk_bxc_xdb .section}

私有bucket回源授权是指若加速域名想要回源至该用户账号下标记为私有的bucket时，需要首先进行授权，授权成功并开启授权配置后，用户开启了私有bucket授权的域名有权限访问私有bucket。

**说明：** 

-   授权成功并开启了对应域名的私有bucket功能，该加速域名可以访问您的私有bucket内的资源内容，开启该功能前，请根据实际的业务情况，谨慎决策；若您授权的私有bucket内容并不适合作为cdn加速域名的回源内容，请勿授权或者开启该功能。
-   您可以配合使用cdn提供的refer防盗链功能，鉴权等功能，有效保护您的资源安全。
-   若您的网站有攻击风险，请购买高防服务，请勿授权或开启私有bucket功能。

## 配置说明 {#section_qrl_jxc_xdb .section}

如何开启私有bucket回源授权？

1.  域名配置，源站设置，单击**私有Bucket回源设置** \> **开启**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5143/3335_zh-CN.png)

2.  单击**立即授权**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5143/3336_zh-CN.png)

3.  授权成功，为该域名开启私有bucket回源配置，单击**确定**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5143/3337_zh-CN.png)

4.  设置成功。

如何关闭私有bucket回源授权？

1.  进入**访问控制** \> **角色管理**。
2.  删除**AliyunCDNAccessingPrivateOSSRole**授权。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5143/3338_zh-CN.png)

3.  私有bucket授权删除成功。

**说明：** 若您的加速域名正在使用私有bucket做为源站进行回源，请不要关闭或删除私有bucket授权。


# HTTPS安全加速设置 {#concept_rns_qvk_xdb .concept}

## 功能介绍 {#section_ynt_mnl_xdb .section}

HTTPS是以安全为目标的HTTP通道，简单讲是HTTP的安全版。即将HTTP用SSL/TLS协议进行封装，HTTPS的安全基础是SSL/TLS。

HTTPS加速优势：

-   传输过程中对用户的关键信息进行加密，防止类似Session ID或者Cookie内容被攻击者捕获造成的敏感信息泄露等安全隐患。
-   传输过程中对数据进行完整性校验，防止DNS或内容遭第三方劫持、篡改等中间人攻击（MITM）隐患，了解更多使用HTTPS防止流量劫持。

阿里云CDN 提供了HTTPS安全加速方案。您只需要开启HTTPS后上传证书和私钥，并支持对证书进行查看、停用、启用、编辑操作。

**说明：** 如果您有SNI回源的需要，请[提交工单](https://workorder-intl.console.aliyun.com)。

## 工作原理 {#section_pcc_snl_xdb .section}

在阿里云CDN控制台开启的HTTPS，将实现用户和阿里云CDN节点之间请求的HTTPS加密。而CDN节点返回源站获取资源的请求仍按您源站配置的方式进行。建议您源站也配置并开启HTTPS，实现全链路的HTTPS加密。

以下是HTTPS加密流程：

 

1.  客户端发起HTTPS请求。
2.  服务端生成公钥和私钥（可以自己制作，也可以向专业组织申请）。
3.  服务端把相应的公钥证书传送给客户端。
4.  客户端解析证书的正确性。

    -   如果证书正确，则会生成一个随机数（密钥），并用公钥该随机数进行加密，传输给服务端。
    -   如果证书不正确，则SSL握手失败。
    **说明：** 正确性包括：证书未过期、发行服务器证书的 CA可靠、发行者证书的公钥能够正确解开服务器证书的发行者的数字签名、服务器证书上的域名和服务器的实际域名相匹配。

5.  服务端用之前的私钥进行解密，得到随机数（密钥）。
6.  服务端用密钥对传输的数据进行加密。
7.  客户端用密钥对服务端的加密数据进行解密，拿到相应的数据。

## 注意事项 {#section_z5h_xnl_xdb .section}

**配置相关**

-   支持开启HTTPS安全加速功能的业务类型包括：图片小文件加速、大文件下载加速、视音频点播加速、直播流媒体加速。
-   支持泛域名HTTPS服务。
-   支持HTTPS安全加速的**启用**和**停用**：
    -   启用：您可以修改证书，系统默认兼容用户的HTTP和HTTPS请求。您也可以自定义对原请求方式设置**强制跳转**。
    -   停用：停用后，系统不再支持HTTPS请求且将不再保留证书或私钥信息。再次开启证书，需要重新上传证书或私钥。
-   您可以查看证书，但由于私钥信息敏感，不支持私钥查看。请妥善保管证书相关信息。
-   你可以更新证书，但请谨慎操作。更新HTTPS证书后1分钟内全网生效。

**计费相关**

HTTPS安全加速属于增值服务，开启后将产生HTTPS请求数计费，当前计费标准详见 HTTPS计费详情。

**说明：** HTTPS根据请求数单独计费，费用不包含在CDN流量包内。请确保账户余额充足再开通HTTPS服务，以免因HTTPS服务欠费影响您的CDN服务。

**证书相关**

-   开启**HTTPS安全加速**功能的加速域名，您需要上传证书，包含证书和私钥，均为 `PEM`格式。

    **说明：** 由于CDN采用的Tengine服务基于Nginx，因此只支持Nginx能读取的证书，即`PEM`格式\)。具体方法，请看参考[证书格式说明及转化方法](intl.zh-CN/用户指南/域名管理/HTTPS安全加速/证书格式说明.md#)。

-   只支持携带SNI信息的SSL/TLS握手。
-   您上传的证书需要和私钥匹配，否则会校验出错。
-   不支持带密码的私钥。

## 操作步骤 {#section_p3r_l4l_xdb .section}

1.  购买证书。您需要具备匹配加速域名的证书才能开启HTTPS安全加速。您可以在[云盾控制台](https://yundun.console.aliyun.com/?spm=5176.2020520110.aliyun_sidebar.19.3ff6ZSicZSiceU&p=cas#/cas/home)快速申请免费的证书或购买高级证书。
2.  登录[CDN控制台](https://cdn.console.aliyun.com)，进入CDN**域名管理**页。选择域名，单击**管理**。
3.  在**HTTPS设置** \> **HTTPS证书**，单击**修改配置**。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5134/153622074311410_zh-CN.png)
4.  在HTTPS设置对话框中，开启**HTTPS安全加速**。
5.  选择证书。您可以选择的证书类型包括：云盾、自定义和免费证书。目前仅支持 `PEM`的证书格式。

    -   您可以选择云盾。若证书列表中无当前适配的证书，您可以选择自定义上传。您需要在设置证书名称后，上传证书内容和私钥，该证书将会在阿里云云盾的证书服务中保存。您可以在[我的证书](https://yundun.console.aliyun.com/?spm=5176.2020520001.aliyun_sidebar.17.12004bd303Zdr8#/all)里查看。
    -   您也可以选择免费证书，即阿里云的Digicert免费型DV版SSL证书。
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5134/153622074311413_zh-CN.png)

6.  验证证书是否生效。证书生效后（约1小时），使用HTTPS方式访问资源。如果浏览器中出现绿色HTTPS标识，表明当前与网站建立的是私密连接，HTTPS安全加速生效。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5134/15362207433701_zh-CN.png)



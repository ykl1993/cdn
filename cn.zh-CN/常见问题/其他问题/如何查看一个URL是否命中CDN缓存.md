# 如何查看一个URL是否命中CDN缓存 {#concept_vyq_mg1_ydb .concept}

给网站使用CDN后，查看访问网站是否命中CDN缓存，用浏览器简单访问测试就可以看到。

查看方法如下：

1.  使用谷歌chrome或者火狐浏览器，在浏览器界面，按F12，打开浏览器调试界面，然后选择“网络”或者是“Network”。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5381/3971_zh-CN.png)

2.  然后访问一个网站链接，在浏览器中进行访问，查看显示的信息。

    主要查看响应头信息中的“X-Cache”字段。

    显示“MISS”，说明没有命中CDN缓存，是回源的。

    显示“HIT”，是命中了CDN缓存。

    如下图所示，显示“MISS”没有命中CDN缓存。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5381/3972_zh-CN.png)

    显示“HIT”，说明是命中CDN缓存的。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5381/3973_zh-CN.png)

    如果问题还未能解决，您可以到阿里云社区进行[免费咨询](http://bbs.aliyun.com/thread/235.html?spm=5176.1691169.1003.3.DazOaU)，或联系[云市场](http://market.aliyun.com/service/?spm=5176.1691169.1003.4.DazOaU)商家寻求帮助。



# 鉴权方式A {#concept_oxj_wrm_j2b .concept}

## 工作原理 {#section_rzx_ttm_j2b .section}

用户访问加密 URL 构成

```
http://DomainName/Filename?auth_key=timestamp-rand-uid-md5hash
```

鉴权字段描述

-   `PrivateKey` 字段用户可以自行设置
-   有效时间1800s指用户访问客户源服务器时间超过自定义失效时间（timestamp字段指定）的1800s后，该鉴权失效。例如用户设置访问时间为2020-08-15 15:00:00，则链接的真正失效时间为2020-08-15 15:30:00。

    |字段|描述|
    |:-|:-|
    |timestamp|失效时间，整形正数，固定长度为10，是1970年1月1日以来的秒数。控制失效时间，10位整数，有效时间1800s。

|
    |rand|随机数，建议使用UUID \(不能包含中划线”-“，如: 477b3bbc253f467b8def6711128c7bec 格式\)。|
    |uid|暂未使用（设置成0即可\)|
    |md5hash|通过md5算法计算出的验证串，由数字和小写英文字母混合组成0-9a-z，固定长度32。|

    CDN服务器拿到请求后，会首先判断请求中的 `timestamp` 是否小于当前时间。

    -   如果小于当前时间，则认为过期失效并返回HTTP 403错误。
    -   如果 `timestamp` 大于当前时间，则构造出一个同样的字符串\(参考以下sstring构造方式\)。然后使用MD5算法算出 `HashValue` ，再和请求中带来的 `md5hash` 进行比对。比对结果一致，则认为鉴权通过，返回文件。否则鉴权失败，返回HTTP 403错误。
-   `HashValue` 是通过以下字符串计算出来的：

    ```
    sstring = "URI-Timestamp-rand-uid-PrivateKey" （URI是用户的请求对象相对地址，不包含参数，如 /Filename）
    HashValue = md5sum(sstring)
    ```


## 鉴权实例 {#section_a1y_ttm_j2b .section}

1.  通过 `req_auth` 请求对象:

    ```
    http:// cdn.example.com/video/standard/1K.html
    ```

2.  设置密钥为：aliyuncdnexp1234（您可以自行配置）
3.  设置鉴权配置文件有效时间为：2015年10月10日00:00:00，计算出秒数为1444435200。
4.  CDN服务器会构造一个用于计算Hashvalue的签名字符串：

    ```
    /video/standard/1K.html-1444435200-0-0-aliyuncdnexp1234"
    ```

5.  根据该签名字符串，CDN服务器会计算HashValue：

    ```
    HashValue = md5sum("/video/standard/1K.html-1444435200-0-0-aliyuncdnexp1234") = 80cd3862d699b7118eed99103f2a3a4f
    ```

6.  则请求时url为：

    ```
    http://cdn.example.com/video/standard/1K.html?auth_key=1444435200-0-0-80cd3862d699b7118eed99103f2a3a4f
    ```

    如果计算出的HashValue与用户请求中带的 md5hash = 80cd3862d699b7118eed99103f2a3a4f 值一致，则鉴权通过。



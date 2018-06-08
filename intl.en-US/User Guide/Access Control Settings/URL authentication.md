# URL authentication {#concept_ixy_r32_xdb .concept}

## Introduction {#section_bc4_bj2_xdb .section}

The URL authentication function protects user’s site resources from illegal download and misuse.  Leeching issues are only partially solved by adding the referer blacklist or whitelist. Because the referer content may be forged,  this method cannot protect site resources completely. Applying URL authentication is recommended to protect the security of origin site resources.

## Concept {#section_jhh_cj2_xdb .section}

The URL authentication function uses Alibaba Cloud CDN nodes in combination with client resource sites to provide a more secure anti-theft protection for origin site resources. The CDN client site provides a user with an encrypted URL \(including permission verification information\), and the user uses it to initiate a request to the CDN node. The CDN node verifies the permission information in the encrypted URL to determine the legality of the request. Legal requests will receive a normal response and illegal requests will be rejected. This protects CDN client site resources.

## URL authentication methods {#section_zqg_dj2_xdb .section}

Alibaba Cloud CDN supports authentication Method A, Method B and Method C. You can select an appropriate method to protect origin site resources based on your business requirements.

Concept

Structure of users’ encrypted URLs

```
http://DomainName/Filename?auth_key=timestamp-rand-uid-md5hash
```

Authentication field descriptions

-   `PrivateKey` field can be set by the user.
-   The validity period 1,800 s indicates that the authentication fails when the user fails to access the client source server 1,800 s after the preset access time. For example, if the preset access time is 2020-08-15 15:00:00, the actual link expiration time is 2020-08-15 15:30:00.

    |Field|Description|
    |:----|:----------|
    |timestamp|The expiration time. It is a positive integer with a fixed length of 10 and a time in seconds from January 1, 1970. This 10-digit integer is used to control the expiration time. Effective time is 1800s.|
    |rand|Random number. We recommend that you use UUID \(not including en dash”-“, for example, 477b3bbc253f467b8def6711128c7bec format\)|
    |uid|Temporarily unused \(set to 0\).|
    |md5hash| The verification string is calculated using the MD5 algorithm. It is comprised of digits and lowercase English letters \(0-9, a-z\) with a fixed length of 32.|

    After the CDN server receives the request, it first determines whether the request  `timestamp` is less than the current time.  If so, it determines that the request has expired and returns an HTTP 403 error.  If the `timestamp` is greater than the current time, it constructs an equivalent string \(see the following string construction method\).  Then, it uses the MD5 algorithm to calculate the `HashValue` and compares it with the `md5hash` contained in the request . If they are consistent, the request passes the authentication and the file is returned. Otherwise, the request authentication fails and an HTTP 403 error is returned.

-   `HashValue` is calculated according to the following method:

    ```
    sstring = "URI-Timestamp-rand-uid-PrivateKey" （URI is the relative address of a user's request object. It does not contain parameters such as "/Filename"）
    HashValue = md5sum(sstring)
    ```


**Example**

1.  Request an object through`req_auth` .

    ```
    http:// cdn.example.com/video/standard/1K.html
    ```

2.  Set the access key to aliyuncdnexp1234 \(set by the user\).
3.  The expiration date of the authentication configuration file is 2015-10-10 00:00:00, and the calculated number of seconds is 1,444,435,200.
4.  The CDN server constructs a signature string used to calculate the HashValue.

    ```
    /video/standard/1K.html-1444435200-0-0-aliyuncdnexp1234"
    ```

5.  The CDN server calculates the HashValue according to the signature string.

    ```
    HashValue = md5sum("/video/standard/1K.html-1444435200-0-0-aliyuncdnexp1234") = 80cd3862d699b7118eed99103f2a3a4f
    ```

6.  The request URL is as follows.

    ```
    http://cdn.example.com/video/standard/1K.html?auth_key=1444435200-0-0-80cd3862d699b7118eed99103f2a3a4f
    ```

    The calculated HashValue is the same as the md5hash = 80cd3862d699b7118eed99103f2a3a4f value in the user request, so the request passes the authentication.


Concept

Format of users’ encrypted URLs

The user access URL is as follows.

```
http://DomainName/timestamp/md5hash/FileName
```

Encrypted URL structure: domain name/URL generation time \(accurate to minutes\) \(timestamp\)/md5 value \(md5hash\)/real path of the source server \(FileName\). The URL validity period is 1,800 s.

When the request passes the authentication, the back-to-source URL is as follows.

```
http://DomainName/FileName
```

Authentication field descriptions

-   Note:`PrivateKey` field can be set by the CDN user.
-   The validity period 1,800 s indicates that the authentication fails when the user fails to access the client source server 1,800 s after the preset access time. For example, if the preset access time is 2020-08-15 15:00:00, the actual link expiration time is 2020-08-15 15:30:00.

|Field|Description|
|:----|:----------|
|DomainName|The domain name of the CDN client site.|
|timestamp|The time designated for when the user accesses the client source server. This is part of the URL as well as a factor used to calculate the `md5hash`. The format is `YYYYMMDDHHMM` and the validity period is 1,800 s.|
|md5hash|The timestamp, FileName, and preset PrivateKey are used in the MD5 algorithm to get this string, namely md5\(`PrivateKey` + `timestamp` + `FileName`\)|
|FileName|The actual back-to-source access URL \(Note: during authentication, the FileName begins with /\).|

Example

1.  Back-to-source request object.

    ```
    http://cdn.example.com/4/44/44c0909bcfc20a01afaf256ca99a8b8b.mp3
    ```

2.  Set the access key to aliyuncdnexp1234 \(set by the user\).
3.  The time format for when the user accesses the client source server is 201508150800 \(the format is YYYYMMDDHHMM\).
4.  The CDN server constructs a signature string used to calculate the md5hash .

    ```
    aliyuncdnexp1234201508150800/4/44/44c0909bcfc20a01afaf256ca99a8b8b.mp3
    ```

5.  The CDN server calculates the md5hash according to the signature string .

    ```
    md5hash = md5sum("aliyuncdnexp1234201508150800/4/44/44c0909bcfc20a01afaf256ca99a8b8b.mp3") = 9044548ef1527deadafa49a890a377f0
    ```

6.  The request URL is as follows.

    ```
    http://cdn.example.com/201508150800/9044548ef1527deadafa49a890a377f0/4/44/44c0909bcfc20a01afaf256ca99a8b8b.mp3
    ```

    The calculated md5hash is the same as the md5hash = 9044548ef1527deadafa49a890a377f0 value in the user request, so the request passes the authentication.


Concept

Format of users’ encrypted URLs

Format 1

```
http://DomainName/{/}/FileName
```

Format 2

```
http://DomainName/FileName{&KEY1=<md5hash>&KEY2=<timestamp>}
```

-   Content in brackets indicates the encryption information added to the standard URL.
-   `<md5hash>`is the authentication information string after MD5 encryption.
-   `<timestamp>`is a non-encrypted string expressed in plaintext. It is a hexadecimal value with a fixed length of 10, indicating the time in seconds from January 1, 1970.
-   Format 1 is used to encrypt the URL. For example,

    ```
    http://cdn.example.com/a37fa50a5fb8f71214b1e7c95ec7a1bd/55CE8100/test.flv
    ```

    `<md5hash>` is a37fa50a5fb8f71214b1e7c95ec7a1bd`<timestamp>` is 55CE8100.


Authentication field descriptions

-   `<md5hash>`field descriptions:

    |Field|Description|
    |:----|:----------|
    |PrivateKey|An interference string. Different users use different interference strings.|
    |FileName|The back-to-source access URL \(Note: during authentication, the path begins with /\).|
    |time| The time when the user accesses the source server. It is UNIX time expressed as a hexadecimal value.|

-   PrivateKey is set to `aliyuncdnexp1234`
-   PrivateKey is set to aliyuncdnexp1234. FileName is set to `/test.flv`
-   time is set to`55CE8100`
-   So the md5hash value is as follows .

    ```
    md5hash = md5sum(aliyuncdnexp1234/test.flv55CE8100) = a37fa50a5fb8f71214b1e7c95ec7a1bd
    ```

-   Plaintext: `timestamp = 55CE8100`

    The URL is generated as so :

    Format 1:

    ```
    http://cdn.example.com/a37fa50a5fb8f71214b1e7c95ec7a1bd/55CE8100/test.flv
    ```

    Format 2:

    ```
    http://cdn.example.com/test.flv?KEY1=a37fa50a5fb8f71214b1e7c95ec7a1bd&KEY2=55CE8100
    ```


Example

When the user uses an encrypted URL to access a CDN node, the CDN server extracts encrypted string 1 and obtains the

`<FileName> of the original URL`

After this process, the CDN server authenticates the URL.

1.  The CDN server uses the  `<FileName>`  of the original URL and the request time and PrivateKey to perform MD5 encryption and obtain encrypted string 2.
2.  The CDN server compares encrypted string 2 with encrypted string 1. If the strings are not the same, the request is rejected.
3.  The current time on the CDN server is used to subtract the plaintext time in the access URL to determine whether the preset time limit t expires \(the time limit t is set to 1,800 s by default\).
4.  The validity period 1,800 s means that the authentication fails when the user fails to access the client source server 1,800 s after the preset access time. For example, if the preset access time is 2020-08-15 15:00:00, the actual link expiration time is 2020-08-15 15:30:00.
5.  The request is valid if the time difference is less than the preset time limit. The CDN server will send a normal response. Any aberration from this means the request is rejected and an HTTP 403 error is returned.

## Sample authentication code {#section_h25_k42_xdb .section}

See [Sample Authentication Code  ](../intl.en-US/Developer Guide/Utilities/Sample authentication code.md#)document in CDN Utilities.

## Procedure {#section_n5x_l42_xdb .section}

Go to the Domain Namespage, select the desired domain name, and click **Configure**.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5152/3461_en-US.png)

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5152/3462_en-US.png)

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5152/3463_en-US.png)


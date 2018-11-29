# Authentication method B {#concept_k5t_zrm_j2b .concept}

Principles

Formats of the encrypted URL for user access

\* The user access URL is as follows:

```
http://DomainName/timestamp/md5hash/FileName
```

Encrypted URL structure: domain name/URL generation time \(accurate to minutes\) \(timestamp\)/md5 value \(md5hash\)/real path of the source server \(FileName\). The URL validity period is 1,800 s.

When the request passes the authentication, the back-to-source URL is as follows.

```
http://DomainName/FileName
```

Authentication fields

-   Note: `PrivateKey` is set by CDN clients.
-   \* Validity period of 1,800 seconds: The user fails the authentication if attempting to access the client source server 1,800 seconds \(specified in the Timestamp field\) later than the preset access time. For example, if the preset access time is 15:00:00 on August 15, 2020, the link expires at 15:30:00 on the same day.

|Field|Description|
|:----|:----------|
|DomainName|CDN client domain name.|
|timestamp|Resource failure time, as part of the URL and as a factor in the calculation of `md5hash` , is formatted: `YYYYMMDDHHMM` , effective time 1800 s|
|md5hash|//md5hash: The "timestamp", "FileName", and preset "PrivateKey" are used in the MD5 algorithm to get this string, i.e., \(`PrivateKey` + `timestamp` + `FileName`\)"|
|FileName|The actual URL of the origin access. Note that FileName must start with a slash \(/\) in authentication.|

Example

1.  Back-to-source request object.

    ```
    http://cdn.example.com/4/44/44c0909bcfc20a01afaf256ca99a8b8b.mp3
    ```

2.  The key is set to aliyuncdnexp1234 \(user-defined\).
3.  The time for the user to access the client source server is 201508150800 \(format: YYYYMMDDHHMM\).
4.  The CDN server constructs a signature string used to calculate the "md5hash":

    ```
    aliyuncdnexp1234201508150800/4/44/44c0909bcfc20a01afaf256ca99a8b8b.mp3
    ```

5.  The CDN server calculates the "md5hash" according to the signature string:

    ```
    md5hash = md5sum("aliyuncdnexp1234201508150800/4/44/44c0909bcfc20a01afaf256ca99a8b8b.mp3") = 9044548ef1527deadafa49a890a377f0
    ```

6.  The URL to request CDN:

    ```
    http://cdn.example.com/201508150800/9044548ef1527deadafa49a890a377f0/4/44/44c0909bcfc20a01afaf256ca99a8b8b.mp3
    ```

    The calculated "md5hash" is the same as the "md5hash = 9044548ef1527deadafa49a890a377f0" value in the user request, so the request passes authentication



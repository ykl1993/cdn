# Authentication method A {#concept_oxj_wrm_j2b .concept}

## How it works {#section_rzx_ttm_j2b .section}

Formats of the encrypted URL for user access

```
http://DomainName/Filename?auth_key=timestamp-rand-uid-md5hash
```

Authentication fields

-   You can set the `PrivateKey` field.
-   The validity period 1,800 seconds indicates that the authentication fails when the user fails to access the client source server 1,800 seconds after the preset access time. For example, if the user sets the access expiration time to 2020-08-15 15:00:00, the link actually fails at 2020-08-15 15:30:00.

    |Field|Description|
    |:----|:----------|
    |timestamp|The expiration time. It is a positive integer with a fixed length of 10 and a time in seconds from January 1, 1970.This 10-digit integer is used to control the expiration time. Effective time is 1,800 seconds.

|
    |rand|random number, we recommend that you use UUID \(not including hyphen“-”, for example, 477b3bbc253f467b8def6711128c7bec format\)|
    |uid|Not used yet \(set to 0\).|
    |md5hash|Verification string calculated by the MD5 algorithm, which is a combination of numbers 0 to 9 and lowercase English letters a to z, with a fixed length of 32 characters|

    When the CDN server receives a request, it first determines whether the `timestamp` in the request is earlier than the current time.

    -   If the \`Timestamp\` is earlier than the current time, the URL is regarded as expired, and the CDN server returns an HTTP 403 error.
    -   If the `timestamp` is later than the current time, the CDN server constructs an equivalent string \(see the construction of the sstring field described later\). Use the MD5 algorithm to calculate `HashValue`, and compare it with `md5hash` . If they are consistent, the request passes the authentication and the requested file is returned. Otherwise, the request fails the authentication, and an HTTP 403 error is returned.
-   The \``HashValue`\` is calculated based on the following string:

    ```
    sstring = "URI-Timestamp-rand-uid-PrivateKey" (URI is the relative address of the user's request object. It does not contain parameters such as /Filename.)
    HashValue = md5sum(sstring)
    ```


## An instance of authorization {#section_a1y_ttm_j2b .section}

1.  Request object by `req_auth`:

    ```
    http:// cdn.example.com/video/standard/1K.html
    ```

2.  Set key to: aliyuncdnexp1234 \(you can configure yourself\)
3.  The expiration date of the authentication configuration file is October 10, 2015 00:00:00. The calculated number of seconds is 1,444,435,200.
4.  The CDN server constructs a signature string for the calculation of HashValue:

    ```
    /video/standard/1K.html-1444435200-0-0-aliyuncdnexp1234"
    ```

5.  Depending on the signature string, the CDN server evaluates hashvalue:

    ```
    HashValue = md5sum("/video/standard/1K.html-1444435200-0-0-aliyuncdnexp1234") = 80cd3862d699b7118eed99103f2a3a4f
    ```

6.  When requested, the URL is:

    ```
    http://cdn.example.com/video/standard/1K.html?auth_key=1444435200-0-0-80cd3862d699b7118eed99103f2a3a4f
    ```

    If the calculated HashValue matches the value of md5hash = 80cd3862d699b7118eed99103f2a3a4f that is carried in the user request, authentication succeeds.



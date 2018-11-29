# Authentication method C {#concept_fvc_bsm_j2b .concept}

Principles

Formats of the encrypted URL for user access

Format 1

```
http://DomainName/{<md5hash>/<timestamp>}/FileName
```

Format 2

```
http://DomainName/FileName{&KEY1=<md5hash>&KEY2=<timestamp>}
```

-   The content in braces represents the encrypted information that is added based on the standard URL.
-   `<md5hash>` is the MD5 encrypted string of authentication information.
-   `<timestamp>` is a non-encrypted string expressed in plaintext.. The fixed length is 10 bits. It is the number of seconds since January 1, 1970, Coordinated Universal Time \(UTC\), expressed in hexadecimal format.
-   Use format 1 to encrypt a URL, for example:

    ```
    http://cdn.example.com/a37fa50a5fb8f71214b1e7c95ec7a1bd/55CE8100/test.flv
    ```

    `<md5hash>` 为 a37fa50a5fb8f71214b1e7c95ec7a1bd`<timestamp>` is 55CE8100。


Authentication fields

-   Field description for `<md5hash>`:

    |Field|Description|
    |:----|:----------|
    |PrivateKey|Interference string. Different clients use different interference strings.|
    |FileName|The actual URL of the origin fetch access. Note that the path must start with a slash \(/\) in authentication.|
    |time|The UNIX time of the user’s access to the origin server, expressed in hexadecimal format.|

-   PrivateKey value: `aliyuncdnexp1234`
-   FileName value: `/test.flv`
-   time value: `55CE8100`
-   So the "md5hash" value is:

    ```
    md5hash = md5sum(aliyuncdnexp1234/test.flv55CE8100) = a37fa50a5fb8f71214b1e7c95ec7a1bd
    ```

-   Plaintext: `timestamp = 55CE8100`

    The encrypted URL is then generated as follows:

    Format 1:

    ```
    http://cdn.example.com/a37fa50a5fb8f71214b1e7c95ec7a1bd/55CE8100/test.flv
    ```

    Format 2:

    ```
    http://cdn.example.com/test.flv?KEY1=a37fa50a5fb8f71214b1e7c95ec7a1bd&KEY2=55CE8100
    ```


Example

The user accesses the acceleration node using the encrypted URL. The CDN server first extracts the encrypted string 1, obtains

`<FILENAME>`

After this process, the CDN server authenticates the URL.

1.  Use `<FileName>`of the original URL, request time, and PrivateKey to do MD5
2.  Compare whether the encrypted string 2 and the encrypted string 1 are the same. The access request is rejected if the two strings are inconsistent.
3.  Use the current time on the CDN server to subtract the plaintext time in the access URL to determine whether the preset time limit t expires \(the time limit t is set to 1,800 s by default\).
4.  The validity period 1,800s means that authentication fails when the user fails to access the client source server 1,800s after the preset access time. For example, if the preset access time is 2020-08-15 15:00:00, the actual link expiry time is 2020-08-15 15:30:00
5.  If the time difference is less than the preset time limit, the request is valid, and the CDN acceleration node responds normally. Otherwise, the request is rejected and an HTTP 403 error is returned.


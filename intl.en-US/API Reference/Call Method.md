# Call Method {#reference_etd_fzt_vdb .reference}

## Request Structure {#section_iy2_3p5_vdb .section}

CDN API interfaces are called by sending an HTTP GET request to the CDN API server. Such requests are completed by adding the relevant request parameters in the request according to the interface instructions. Results will be returned based on the request’s processing status.

its request has been structured as follows:

```
http://Endpoint/? action = xx & Parameters
```

Among them:

-   Endpoint：the cloud service node that is called. The access node of CDN is `cdn.aliyuncs.com`
-   Action: the action that is performed. To use AddCdnDomain.
-   Version: the API version to use. The cloud network API version is 2014-11-11.
-   Parameters: Request Parameters, separated by "&" for each parameter.

    Request Parameters consist of Public Request Parameters and API custom parameters. The common parameters contain information such as the API version number, authentication, and so on.


The following is an example of an instance of a cloud enterprise network that has been created by calling the described becens interface:

**Note:** For user viewing, all the examples in this document have been formatted.


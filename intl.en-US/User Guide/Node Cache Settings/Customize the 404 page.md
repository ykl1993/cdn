# Customize the 404 page {#concept_edl_pjd_xdb .concept}

## Introduction {#section_ctr_wjd_xdb .section}

You can customize the page that is displayed when a 404 status code is returned.  The following three options are available:

Take return Code 404 as an example:

-   Default 404 page: when an HTTP 404 error is returned, the server returns the default 404 Not Found page.
-   Public welfare 404 page: when an HTTP an HTTP 404 error is returned, the server returns to the real-time update of the public welfare 404 page, view the [public welfare 404 page](http://promotion.alicdn.com/help/oss/error.html).
-   Custom 404 page: when an HTTP 404 error is returned, the server returns to the 404 page designed and edited by the user. You must costomize complete URL address of the error page.

## Attentions: {#section_ckt_bkd_xdb .section}

-   The public welfare 404 page is a public welfare resource of Alibaba Cloud. It is free and generates no traffic fees.
-   Custom 404 pages are personal resources which are billed based on normal delivery.

## Procedure {#section_kb1_dkd_xdb .section}

1.  Go to the CDN domain name overview page, select a domain name to enter the Domain Namespage, and set the **Custom page**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5148/3394_en-US.png)

2.  Click  **Modify**, and you can view and manage the custom error pages.  

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5148/3395_en-US.png)

3.  Click **Add** to add the page content of the custom return code.  

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5148/3396_en-US.png)


If you choose  **Custom page 404**, you need to store the page resources, like other static files, under the origin site domain. You can access the page through a CDN domain by entering the complete URL \(including \`http://\`\) of the CDN domain.

For example, if the CDN domain name is `exp.aliyun.com`, and the 404 page is`error404.html` you can store the`error404.html`page to the origin site. Select the “Custom 404”, and enter  `http://exp.aliyun.com/error404.html`.


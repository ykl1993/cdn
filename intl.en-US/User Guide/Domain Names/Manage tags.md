# Manage tags {#concept_d4k_zb3_4gb .concept}

This topic describes how to tag your domain names in the Content Delivery Network \(CDN\) console. You decide the usage of tags. Alibaba Cloud CDN only works to match and filter your tags and domain names by character string.

## Feature introduction {#section_eqh_3c3_4gb .section}

You can use tags to mark the usage of domain names or to group them. Then, you can filter the data corresponding to specified domain names on the Domain Names page, Resource Monitoring page, and Usage page by using tags. This helps you query domain name data and manage domain name groups.

## Limits {#section_qcm_kc3_4gb .section}

-   Each tag consists of a key-value pair \(key:value\).
-   Each domain name can be attached with up to 20 tags.
-   The tag key of a domain name is unique. If you successively set two tags to have the same key but have two different values for a domain name, the new value overwrites the old one. For example, if you set the Key1:Value1 tag and Key1:Value2 tag for the domain name test.example.com, only the Key1:Value2 tag is attached to the domain name.
-   A key cannot start with aliyun: or acs:. It cannot contain http://, https://, and it cannot contain empty strings.
-   A value cannot contain http://or https://, but can contain empty strings.
-   A key can contain up to 64 Unicode characters.
-   A value can contain up to 128 Unicode characters.
-   Letters in a key or a value are case-sensitive.

## Procedure {#section_mld_pc3_4gb .section}

**Tag editing**

-   To edit the tag of a single domain name, follow these steps:
    1.  Log on to the [CDN console](https://cdn.console.aliyun.com).
    2.  Click **Domain Names**.
    3.  Select the target domain name, and then move the pointer over the corresponding tag.
    4.  In the displayed shortcut menu, select **Edit**.

        ![](images/38492_en-US.png)

    5.  In the Edit Tag dialog box, select **Existing Tags** or **New Tags**. After you finish editing the tag, click **OK**.

        ![](images/38493_en-US.png)

-   To edit the tag of multiple domain names, follow these steps:
    1.  Log on to the [CDN console](https://cdn.console.aliyun.com).
    2.  Click **Domain Names**.
    3.  Select the target domain names, and then click **Manage Tag**.![](images/38494_en-US.png)
    4.  Select **Delete Tag** or **Add Tag**.

**Data filtering**

To filter domain name data, follow these steps:

1.  Log on to the [CDN console](https://cdn.console.aliyun.com).
2.  On the Domain Names page, Resource Monitoring page, or Usage page, select the target tag \(key:value\), and then click **Query**.

    **Note:** If you select multiple tags, the query result is an intersection of the domain names corresponding to these tags.


![](images/38530_en-US.png "Domain Names page")

![](images/38495_en-US.png "Resource Monitoring")

![](images/38496_en-US.png "Usage")

## Example {#section_ng3_rc3_4gb .section}

Company C have 100 domain names in Alibaba Cloud CDN. These domain names are used by three departments \(that is, the e-commerce, gaming, and entertainment departments\) for marketing activities, Game G1, Game G2, and post-production. The company has three O&M leaders: Alice, Bob, and Chris.

**Tag setting**

Company C uses tags to manage its domain names and defines the following keys and values.

|Key|Value|
|:--|:----|
|Department|E-commerce, gaming, and entertainment|
|Business|Marketing activities, Game G1, Game G2, and post-production|
|Leader|Alice, Bob, and Chris|

Company C attaches these key and values to the domain names. The following table describes the relationships between the domain names and key-value pairs.

|Domain name|Value for when the key is a department|Value for when the key is a business|Value for when the key is a leader|
|-----------|--------------------------------------|------------------------------------|----------------------------------|
|Domain 1|E-commerce|Marketing activities|Chris|
|Domain 2|E-commerce|Marketing activities|Chris|
|Domain 3|Gaming|Game G1|Alice|
|Domain 3|Gaming|Game G2|Alice|
|Domain 4|Gaming|Game G2|Alice|
|Domain 5|Gaming|Game G2|Bob|
|Domain 6|Gaming|Game G2|Bob|
|Domain 7|Gaming|Game G2|Bob|
|Domain 8|Entertainment|Post-production|Chris|
|Domain 9|Entertainment|Post-production|Chris|
|Domain 10|Entertainment|Post-production|Chris|

**Tag use**

-   If Company C wants to filter the domain names managed by Chris, the tag **leader:Chris** needs to be selected.
-   If Company C wants to filter the domain names managed by Bob in the gaming department, the **department:gaming** tag and the**leader:Bob** tag need to be selected.


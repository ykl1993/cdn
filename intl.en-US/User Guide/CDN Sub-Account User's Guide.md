# CDN Sub-Account User's Guide {#concept_zk3_mr2_xdb .concept}

This document is available to customers of CDN domain name resource group management requirements, the sub-account + Resource Group is used to authorize the isolation of resources between different departments, and the access process is as follows.

## Access Process {#section_vx5_zw2_xdb .section}

1.  Log on to the Enterprise Console.

    **Note:** Resource Group setup and sub-account management need to be done in the Enterprise Console, after you have set up the appropriate resource groups and permissions, A child account is logged into the CDN console and limited resource viewing and operation is performed in accordance with the rules that have been set, ensure that operations and resource displays are completely isolated between sub-accounts.

    Use the master account to log on to the [Enterprise Console](https://enterprise.console.aliyun.com/) \(attached: [Enterprise Console User's Manual](https://help.aliyun.com/document_detail/59910.html) \).

    ![](images/3487_en-US.png)

2.  Create a sub-account.
    -   Entering the personnel management module for the first time requires the creation of a directory, A user must and only belong to a directory.**personnel management**
    -   After creating the directory, you can**Personnel Management** \> **User management**Create a sub-account in.

        ![](images/3488_en-US.png)

        **Note:** Groups can also be created and managed in a unified manner, depending on your business needs.

3.  Create a Resource Group + authorization.

    Enter the **Resource management**resource management module, create a resource group, and create the following **1 BU**。No. 1 bu Resource Group.

    ![](images/3489_en-US.png)

    Complete**resource**、**personel**and**set**。

    ![](images/3490_en-US.png)

    Enter**Resources management** \> **Resource** To achieve accelerated domain name grouping settings, select the product CDN in the filter area, check the accelerated domain name to which you want to join the resource group, and click **go to** complete the accelerated domain name settings within the resource group.

    ![](images/3491_en-US.png)

    Enter**Resource management** \> **Members**Complete the authorization for the sub-account, click **Add-on**, you can select a sub-account that needs to manage this resource group and complete the policy authorization: authorization template description.

    ![](images/3492_en-US.png)

4.  Log in to the CDN console using a sub-account.

    Login address: [http://signin.aliyun.com/<custom domain\>.onaliyun.com/login.htm](http://signin.aliyun.com/%3C%E8%87%AA%E5%AE%9A%E4%B9%89%E5%9F%9F%3E.onaliyun.com/login.htm)

    After the sub-account is logged in, you can select a resource group that shows that the current sub-account has permissions, accelerate domain names according to resource group column.

    ![](images/3493_en-US.png)

    Self-account support Domain name management, monitoring, refresh and log download, and other operations are in full agreement with the master account, please refer to [Quick Start](https://help.aliyun.com/document_detail/27112.html).


## Appendix {#section_nmw_4y2_xdb .section}

Current Ram template Policy

1.  CDN management authorization: supports additional Delete check changes.

    ```
    
      Version: "1 ",
      "Statement ":[
        
          Action: CDN :*",
          "Resource ":"*",
          "Effect": "allow"
        
      
    
    ```

2.  CDN read-only permission.

    ```
    
      Version: "1 ",
      "Statement ":[
        
          Action: CDN: Describe *",
          "Resource ":"*",
          "Effect": "allow"
        
      
    
    ```



# IP Blacklist and Whitelist {#concept_drs_1q2_xdb .concept}

## Introduction {#section_xsf_2q2_xdb .section}

CDN supports the blacklist and whitelist rules. You can add IP addresses on the IP blacklist. An IP address on the blacklist cannot access the target domain. Likewise, only IP addresses on the whitelist can access the target domain.

You can use an IP network segment to add IP addresses to the blacklist or whitelist. For example, 127.0.0.1/24.

**Note:**   127.0.0.1/24. 24 indicates that the first 24 bits in the subnet mask are used as effective bits, for example, 32-24=8 bits are used to express host numbers. In this way, the subnet can accommodate 2 ^ 8-2 = 254 hosts. And 127.0.0.1/24 indicates the IP network segment scope of 127.0.0.1~127.0.0.255.

## Procedure {#section_i1n_2q2_xdb .section}

1.  Go to Domain Namespage, select the domain name, then click **Manage**.
2.  On **Access Control** \> **IP Blacklist/Whitelist**, click **Modify**.
3.  Choose**Blacklist** or **Whitelist**, and add the IP network segment in the box below.
4.  Click **Confirm**.


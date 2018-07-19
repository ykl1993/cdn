# Back-to-origin with the Same Protocol {#concept_j1v_l1d_xdb .concept}

## Introduction {#section_hn2_q1d_xdb .section}

When the back-to-source with the same protocol feature is enabled, back-to-source requests for resources uses the same protocol used by the client in order to request resources. If the client makes an HTTPS request for resources, but the resources are not cached on the node, the same back-to-source HTTPS request will be made for resources. This protocol is also applicable for HTTP requests.

**Note:** The origin site must support both the port 80 and port 443; otherwise, the back-to-source may fail.

## Procedure {#section_q5g_xpk_n2b .section}

1.  Go to Domain Namespage, select the domain name, then click **Manage**.
2.  Click **Modify** in**Cache Configuration** \> **Back-to-origin with the Same Protocol**.
3.  Choose your **Redirect Type**: **Follow** **HTTPS**, or **HTTP**.


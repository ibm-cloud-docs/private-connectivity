---



copyright:
  years: 2023, 2024
lastupdated: "2024-02-04"

keywords: private connectivity options

subcollection: private-connectivity

---

{{site.data.keyword.attribute-definition-list}}

# Direct Link Connect provisioning walk-through
{: #provisioning-scenario-connect}

Leverage a service provider to quickly establish and deliver connectivity to IBM Cloud locations. A service provider is already connected to the IBM Cloud network via multi-tenant, high-capacity links, also known as a network-to-network interface (NNI). Typically, you can purchase a virtual circuit at this provider, establishing connectivity in a rapid manner because the physical connectivity from IBM to the service provider is already in place.
{: shortdesc}

This offering is ideal for multicloud environments with your service provider's network.

Depending on your service provider, the Direct Link Connect provisioning process takes approximately 3 to 5 business days to complete. Provisioning on the IBM side is completed the same day. The provisioning process is as follows:

IBM Cloud highly recommends that a second, diverse direct link be established to prevent outages, whether unplanned or planned due to maintenance.
{: important}

1. [1-2 days]{: tag-blue} - Contact your service provider. Determine the location to IBM Cloud by verifying your provider capabilities to reach IBM Cloud over partner interconnects known as NNIs.
1. [1-2 days]{: tag-blue} - Read planning considerations and order Direct Link Connect. For instructions, see [Ordering Direct Link Connect](/docs/dl?topic=dl-how-to-order-ibm-cloud-dl-connect).

    The IBM side is provisioned immediately after submitting your order in the IBM Cloud console.
    {: note}

1. After you submit your order, contact your service provider and negotiate connectivity to your environment, whether it is on-premises or in colocation.
1. [Contact your provider for provisioning time]{: tag-blue} - Order a virtual circuit through the service provider. Reference the case ID of the Direct Link Connect request as your Request ID or Authorization ID.
1. [Contact your provider for provisioning time]{: tag-blue} - Configure the BGP parameters on your Edge router for BGP session establishment. After this completes, the BGP status indicates `Established`.

After connectivity is established successfully, your gateway moves to `Provisioned` status. Then, this case is closed. For further assistance with your direct link, contact [IBM Support](https://cloud.ibm.com/unifiedsupport/supportcenter){: external}.

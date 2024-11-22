---



copyright:
  years: 2023, 2024
lastupdated: "2024-02-04"

keywords: private connectivity options

subcollection: private-connectivity

---

{{site.data.keyword.attribute-definition-list}}

# Direct Link Dedicated
{: #reference-direct-link-dedicated}

Provides additional information on the Direct Link Dedicated offering.
{: shortdesc}

## Pricing
{: #reference-pricing-dedicated}

To calculate pricing for IBM Cloud offerings, use the [IBM Cloud cost estimator](https://www.ibm.com/cloud/cloud-calculator){: external}.
{: tip}

* High cost
* Dedicated connectivity with increased bandwidth options.
* Cost varies by network service provider.
* Costs are typically structured based on bandwidth limits, port charges (fixed or metered per GB of data), volume of data egress from VPC through the connection gateway, and so on.
* IBM Cloud offers two pricing plans - metered and unmetered. With metered pricing, you pay only for what you use. Unmetered means unlimited access, for a monthly fee.

## Connectivity
{: #reference-connectivity-dedicated}

* Connect the VPC networks directly with physical connections.
* The connection is established between the network provider and IBM Cloud at a colocation data center facility common to both parties.
* The connection is private, not encrypted, bypasses the internet, and is a dedicated single-tenant network connection.

## Latency and bandwidth
{: #reference-latency-bandwidth-dedicated}

* Lowest latency, single tenant, with high-bandwidth options.
* Higher maximum limits apply to throughput capacity, depending on the selected offerings from the network service provider.
* Available in speeds up to 10 Gbps.

## Provisioning
{: #reference-provisioning-dedicated}

* Requires the provisioning of physical connections at the colocation facility. The provisioning is done through a semi-self-service process with support and assistance from the network service provider and colocation facility partner.
* The provisioning process can take several days (typically 5 to 30), depending on the network service provider’s colocation facility partner offerings, contracting process, and exchange of technical details to set up connectivity.
* Lower flexibility to make changes and adapt to changes in workload locations due to physical connectivity, contracting, and colocation dependencies.
* Detailed long-term planning is required, specific to the workload location and connectivity service providers available at the colocation facility.
* IBM Cloud Direct Link Dedicated has partnerships with various colocation/data center operators.

Related links:
* [Ordering](/docs/dl?topic=dl-how-to-order-ibm-cloud-dl-dedicated)
* [Locations](/docs/dl?topic=dl-locations#dedicated-locations)
* [FAQs](/docs/dl?topic=dl-faqs&interface=ui)
* [Limitations](/docs/dl?topic=dl-known-limitations&interface=ui)
* [Access management](/docs/dl?topic=dl-iam&interface=ui)
* [Responsibilities](/docs/dl?topic=dl-dl-responsibilities)
* [View egress usage](/docs/dl?topic=dl-faqs#view-egress-usage)

## Security and data encryption
{: #reference-security-data-encryption-dedicated}

* Workload data that is transmitted across the network connections is usually not encrypted by the providers and is the customer's responsibility.
* Encryption is highly recommended and can be achieved at application level, for example with TLS encryption between the application client/severs.
* Optionally, a VPN can be set up on the connection to get a secure tunnel between endpoint subnetworks.
* The offering configuration and control data are encrypted in-transit and at-rest at the database level.  [Learn more](/docs/dl?topic=dl-mng-data#data-storage)

## Resiliency
{: #reference-resiliency-dedicated}

* Depends on the availability requirements. Additional connections can be provisioned in the same or different PoPs (Points of Presence) to achieve higher resiliency.
* Optionally, for a lower-cost redundant alternative, a VPN or partner network connectivity can be provisioned and used as a fallback.

Related links:
* [Achieving redundancy](/docs/dl?topic=dl-faqs#how-can-i-achieve-redundancy-with-ibm-cloud-dl)
* [Models for diversity and redundancy](/docs/dl?topic=dl-models-for-diversity-and-redundancy-in-direct-link)
* [High availability](/docs/dl?topic=dl-ha)
* [Business continuity and disaster recovery](/docs/dl?topic=dl-bc-dr)

## Monitoring and logging
{: #reference-monitoring-logging-dedicated}

Direct Link Dedicated uses a combination of IBM Activity Tracker and the IBM Cloud Console for log analysis and metrics monitoring.

### Direct Link Dedicated log analysis
{: #dld-logging}

You can use the Activity Tracker service to track how users and applications interact with Direct Link Dedicated in IBM Cloud.

IBM Cloud Activity Tracker records user-initiated activities that change the state of a service in IBM Cloud. You can use this service to investigate abnormal activity and critical actions and to comply with regulatory audit requirements. In addition, you can be alerted about actions as they happen. The events that are collected comply with the Cloud Auditing Data Federation (CADF) standard. For more information, refer to [Auditing events for IBM Cloud Direct Link](/docs/dl?topic=dl-at_events&interface=ui).

### Direct Link Dedicated metrics monitoring
{: #dld-metrics}

You can generate a report of all routes that are known to a direct link and its connections. This report allows you to verify the expected routes, view what virtual connections are contributing which routes to your direct link, and see next-hop address details of the routes received. If you are using the cross-account VPC linking feature, you can also see which prefixes or subnets are being routed through your cross-connect router. For more information, refer to [Generating a direct link route report](/docs/dl?topic=dl-generate-route-reports&interface=ui).

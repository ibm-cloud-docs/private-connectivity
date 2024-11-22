---



copyright:
  years: 2023, 2024
lastupdated: "2024-02-04"

keywords: private connectivity options

subcollection: private-connectivity

---

{{site.data.keyword.attribute-definition-list}}

# Direct Link Connect
{: #reference-direct-link-connect}

This topic provides additional information on the Direct Link Connect offering.
{: shortdesc}

## Pricing
{: #reference-pricing-connect}

To calculate pricing for IBM Cloud offerings, use the [IBM Cloud cost estimator](https://www.ibm.com/cloud/cloud-calculator){: external}.
{: tip}

* Moderate cost
* Varies by cloud provider and partner network offerings
* Costs are typically structured based on routing options, bandwidth limits, cross connect port charges (fixed or metered per GB of data), volume of data egress from VPC through the connection gateway, and so on.
* IBM Cloud offers two pricing plans - metered and unmetered. With metered pricing, you pay only for what you use. Unmetered means unlimited access, for a monthly fee.

## Connectivity
{: #reference-connectivity-connect}

* Connect the VPC networks through intermediate partner networks
* Partners have pre-established connectivity with cloud provider networks and provide an exchange for cross connections and routing between the cloud networks.
* The connection is private, not encrypted, bypasses the internet, and is over a multi-tenant, shared network.

## Latency and bandwidth
{: #reference-latency-bandwidth-connect}

* Reliable, consistent, and lower latencies, higher security as connections bypass the internet.
* Maximum limits apply to throughput capacity, depending on the selected partner offerings from the cloud provider.
* Available in speeds up to 5 Gbps.

## Provisioning
{: #reference-provisioning-connect}

* Requires the provisioning of connectivity ports on the peer VPCs to connect the VPC to the partner network, as well as the provisioning of the cross-connect between the peer cloud ports on the partner network. Provisioning is done using self-service or semi-self-service processes available from IBM Cloud and partner service providers.
* The provisioning process typically takes 2-10 days and utilizes pre-established partnerships and contracts, but depends on offerings used from the cloud service provider and partner service provider.
* Provides flexibility to make changes and adapt to changes in workload locations.
* Must ensure the partner network supports cross connecting the relevant cloud provider data center locations.
* IBM Cloud Direct Link Connect has partnerships with over 45 global service providers.

Related links:
* [Ordering](/docs/dl?topic=dl-how-to-order-ibm-cloud-dl-connect)
* [Providers and locations](/docs/dl?topic=dl-locations#connect-locations)
* [FAQs](/docs/dl?topic=dl-faqs&interface=ui)
* [Limitations](/docs/dl?topic=dl-known-limitations&interface=ui)
* [Access management](/docs/dl?topic=dl-iam&interface=ui)
* [Responsibilities](/docs/dl?topic=dl-dl-responsibilities)
* [View egress usage](/docs/dl?topic=dl-faqs#view-egress-usage)

## Security and data encryption
{: #reference-security-data-encryption-connect}

* Workload data transmitted across the network connections is usually not encrypted by the providers and is the customer's responsibility.
* Encryption is highly recommended and can be achieved at application level, for example with TLS encryption between the application client/severs.
* Optionally, VPN can be set up on the connection to get a secure tunnel between endpoint sub-networks.
* The offering configuration and control data is encrypted in-transit and at-rest at the database level. [Learn more](/docs/dl?topic=dl-mng-data#data-storage)

## Resiliency
{: #reference-resiliency-connect}

* Depends on the offerings. Typically requires a second connection to be configured using different availability zones and different cross connect routers (XCRs) to achieve HA.
* Leverages SND by provisioning a virtual circuit across a bank of physical XCRs, which allows for failure of one physical device without connectivity failure. Additional connections can be provisioned to provide higher resiliency.
* Optionally, for a low-cost redundant alternative, a VPN can be provisioned and used as fallback.

Related links:
* [Achieving redundancy](/docs/dl?topic=dl-faqs#how-can-i-achieve-redundancy-with-ibm-cloud-dl)
* [Models for diversity and redundancy](/docs/dl?topic=dl-models-for-diversity-and-redundancy-in-direct-link)
* [High availability](/docs/dl?topic=dl-ha)
* [Business continuity and disaster recovery](/docs/dl?topic=dl-bc-dr)

## Monitoring and logging
{: #reference-monitoring-logging-connect}

Direct Link Connect uses a combination of IBM Activity Tracker and the IBM Cloud Console for log analysis and metrics monitoring.

### Direct Link Connect log analysis
{: #dlc-logging}

You can use the Activity Tracker service to track how users and applications interact with Direct Link Connect in IBM Cloud.

IBM Cloud Activity Tracker records user-initiated activities that change the state of a service in IBM Cloud. You can use this service to investigate abnormal activity and critical actions and to comply with regulatory audit requirements. In addition, you can be alerted about actions as they happen. The events that are collected comply with the Cloud Auditing Data Federation (CADF) standard. For more information, refer to [Auditing events for IBM Cloud Direct Link](/docs/dl?topic=dl-at_events&interface=ui).

### Direct Link Connect metrics monitoring
{: #dlc-metrics}

You can generate a report of all routes known to a direct link and its connections. This report allows you to verify the expected routes, view what virtual connections are contributing which routes to your direct link, and see next-hop address details of the routes received. If using the cross-account VPC linking feature, you can also see which prefixes or subnets are being routed through your cross-connect router. For more information, refer to [Generating a direct link route report](/docs/dl?topic=dl-generate-route-reports&interface=ui).

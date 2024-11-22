---



copyright:
  years: 2023, 2024
lastupdated: "2024-02-04"

keywords: private connectivity options

subcollection: private-connectivity

---

{{site.data.keyword.attribute-definition-list}}

# Transit Gateway
{: #reference-transit-gateway}

This topic provides additional information on the Transit Gateway offering.
{: shortdesc}

## Pricing
{: #reference-pricing-transit-gateway}

To calculate pricing for IBM Cloud offerings, use the [IBM Cloud cost estimator](https://www.ibm.com/cloud/cloud-calculator){: external}.
{: tip}

* Moderate cost
* Costs are derived from the number of networks connected to the gateway, is the gateway enabled for local or global routing, volume of traffic through the gateway, and so on.

## Connectivity
{: #reference-connectivity-transit-gateway}

IBM Cloud provides:
* A private backbone for all connectivity between resources deployed in your VPC virtual networks with an AZ and between AZs (this backbone is separate from the public backbone for connectivity using public addressing). IP addresses on the private backbone are non-internet routable, or not announced toward the public backbone or the internet. The private backbone is owned, managed, and operated exclusively by IBM Cloud.
* IBM Cloud Transit Gateway uses this private backbone exclusively for connectivity between your virtual networks within a single region, across multiple regions, and to your IBM Cloud classic workloads.

Transit gateways connect:
   - VPCs in the same region (local routing)
   - VPCs in different regions (global routing)
   - VPCs to your IBM Cloud classic infrastructure
   - Networks using a Generic Routing Encapsulation (GRE) tunnel
   - On-premise networks using Direct Link to your IBM Cloud networks

## Latency and bandwidth
{: #reference-latency-bandwidth-transit-gateway}

* Reliable, high throughput, purely contained within the Cloud network.
* Can traverse multiple regions if connecting networks in disparate locations.
* Speeds up to or in excess of 10 Gbps.

## Provisioning
{: #reference-provisioning-transit-gateway}

With IBM Cloud Transit Gateway, you can connect:
* VPCs in the same region (local routing)
* VPCs in different regions (global routing)
* VPCs to your IBM Cloud classic infrastructure
* Networks using a Generic Routing Encapsulation (GRE) tunnel
* On-premise networks using Direct Link to your IBM Cloud networks
* Ordered and configured through IBM Cloud UI, CLI or API.

Related links:
* [Locations](/docs/transit-gateway?topic=transit-gateway-tg-locations)
* [Ordering a Transit Gateway](/docs/transit-gateway?topic=transit-gateway-ordering-transit-gateway&interface=ui)
* [FAQs](/docs/transit-gateway?topic=transit-gateway-faqs-for-transit-gateway)
* [Adding Connection to Transit Gateway](/docs/transit-gateway?topic=transit-gateway-adding-connections&interface=ui)
* [Responsibilities](/docs/transit-gateway?topic=transit-gateway-tg-responsibilities)

## Security and data encryption
{: #reference-security-data-encryption-transit-gateway}

* Workload data transmitted across the network connections is not encrypted by the provider and is the customer's responsibility.
* Encryption is highly recommended and can be achieved at application level, for example with TLS encryption between the application client/severs.
* The offering configuration and control data is encrypted in-transit and at-rest at the database level. [Learn more](/docs/transit-gateway?topic=transit-gateway-mng-data#data-storage)

## Resiliency
{: #reference-resiliency-transit-gateway}

IBM Cloud Transit Gateway is highly available within any IBM Cloud location (for example, Dallas or Washington, DC). However, recovering from disasters that affect an entire location requires planning and preparation.

You are responsible for understanding your configuration, customization, and usage of the service. You are also responsible for being ready to re-create an instance of the service in a new location and restore your data in a new location.

Related links:

* [High Availability](/docs/transit-gateway?topic=transit-gateway-ha)
* [Business continuity and disaster recovery](/docs/transit-gateway?topic=transit-gateway-bc-dr)

## Monitoring and logging
{: #reference-monitoring-logging-transit-gateway}

### Transit Gateway log analysis
{: #tgw-logging}

You can use the Activity Tracker service to track how users and applications interact with Transit Gateway in IBM Cloud.

IBM Cloud Activity Tracker records user-initiated activities that change the state of a service in IBM Cloud. You can use this service to investigate abnormal activity and critical actions and to comply with regulatory audit requirements. In addition, you can be alerted about actions as they happen. The events that are collected comply with the Cloud Auditing Data Federation (CADF) standard. For more information, refer to [Auditing events for IBM Cloud Transit Gateway](/docs/transit-gateway?topic=transit-gateway-at_events&interface=ui).

### Transit Gateway metrics monitoring
{: #tgw-metrics}

You can generate a report of all routes known to a gateway and its connections. This report allows you to verify the expected routes, view what connections are contributing which routes to your gateway, and see BGP information on routes recieved. This report contains routes from same account networks, and from networks connected using the cross-account connection capability. For more information, refer to [Generating a Transit Gateway route report](/docs/transit-gateway?topic=transit-gateway-route-reports&interface=ui).

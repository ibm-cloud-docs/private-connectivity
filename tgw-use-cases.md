---



copyright:
  years: 2023, 2024
lastupdated: "2023-10-06"

keywords: private connectivity options

subcollection: private-connectivity

---

{{site.data.keyword.attribute-definition-list}}

# Transit Gateway use cases
{: #use-cases-transit-gateway}

As the number of your Virtual Private Clouds (VPCs) grow, you need an easy way to manage the interconnection between these resources across multiple regions. IBM Cloud Transit Gateway is designed specifically for this purpose.

With IBM Cloud Transit Gateway, you can create single or multiple transit gateways to connect VPCs together. You can also connect your IBM Cloud classic infrastructure to a transit gateway to provide seamless communication with classic infrastructure resources. Any new network that you connect to a transit gateway is then automatically made available to every other network connected to it. This makes it easy to scale your network as it grows.

Transit gateways provide flexibility by allowing you to add networks to local gateways. Networks can be attached to multiple local gateways and a single global gateway, enabling you to keep local traffic on a local gateway.

## Connecting two {{site.data.keyword.powerSys_notm}} environments by using IBM Cloud Transit Gateway
{: #network-reference-architecture-tgw}

In this deployment topology, a connection through IBM Cloud Transit Gateway is used to provide connectivity between Power virtual server environments located at two different data centers. With IBM Cloud Transit Gateway, you can also interconnect your {{site.data.keyword.powerSys_notm}}s to the IBM Cloud classic and VPC infrastructures, keeping traffic within the IBM Cloud network. Transit Gateway enables you to connect your otherwise disconnected private networks, such as classic, VPC, and {{site.data.keyword.dl_short}}. In addition, you can establish connection between multiple {{site.data.keyword.powerSys_notm}} workspaces across different data centers.

The following network architecture allows connectivity between multiple {{site.data.keyword.powerSys_notm}} locations with high availability (HA) and disaster recovery (DR) solutions.

![Transit Gateway deployment scenario](/images/network-tgw.svg "Transit Gateway use case"){: caption="Figure 1. Transit Gateway use case" caption-side="bottom"}

Key features are as follows:

   - Access and connectivity between two different {{site.data.keyword.powerSys_notm}} locations in the same region (for example DAL12 to DAL13) to support HA through replication.
   - Access and connectivity between two different {{site.data.keyword.powerSys_notm}} locations in different regions (for example DAL12 to WDC06) to support DR through replication.

With local routingm you can only connect PERs in the same region as the Transit Gateway, while PERs in a different region require global routing.
{: note}

Complete the following steps to implement this scenario:

1.	Create an [IBM Cloud Transit Gateway](/interconnectivity/transit/provision){: external} to enable the virtual connections.
1.	[Create an IBM Cloud connection](/docs/power-iaas?topic=power-iaas-cloud-connections#create-cloud-connections) with Transit Gateway enabled.
1.	Connect your {{site.data.keyword.powerSys_notm}}s that are located in data center 1 and data center 2 through the IBM Cloud network by using a transit gateway.

After the transit gateway connection is established, different IBM Cloud networks are connected to each other.

Related link: [Transit Gateway interconnectivity patterns](/docs/transit-gateway?topic=transit-gateway-about#patterns)

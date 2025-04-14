---



copyright:
  years: 2023, 2025
lastupdated: "2025-04-14"

keywords: private connectivity options

subcollection: private-connectivity

---

{{site.data.keyword.attribute-definition-list}}

# {{site.data.keyword.cloud_notm}} private connectivity offerings 
{: #white-paper}

This white paper explores how to establish a private connection to {{site.data.keyword.cloud_notm}} by using various network topologies.
{: shortdesc}

## Introduction
{: #introduction}

These network topologies enable secure, high-performance connectivity between on-premises infrastructure and {{site.data.keyword.cloud_notm}} resources. The following options are available:

* Direct Link Dedicated - Single tenant connection to {{site.data.keyword.cloud_notm}} [Point of Presences](#x5458832){: term} (PoPs)
* Direct Link Connect - Multi-tenant service provider connection to {{site.data.keyword.cloud_notm}} PoPs
* VPN (site-to-site) - VPN tunnel from on-premises firewall to {{site.data.keyword.cloud_notm}} VPN
* VPN (client-to-site) - VPN tunnel from laptop to {{site.data.keyword.cloud_notm}} VPN
* Satellite Connector - A layer-7, endpoint-oriented connection from {{site.data.keyword.cloud_notm}} to access on-premises data source.

Private connectivity resources within {{site.data.keyword.cloud_notm}} can be achieved with Transit Gateway (private backbone).
{: note}

![{{site.data.keyword.cloud_notm}} Overview](/images/cloud-private-conn.svg "{{site.data.keyword.cloud_notm}} Private Connectivity Overview"){: caption="{{site.data.keyword.cloud_notm}} Private Connectivity Overview" caption-side="bottom"}

### Required skills for system administrators
{: #required-skills}

Creating network connectivity in {{site.data.keyword.cloud_notm}} is a critical task for network administrators. It allows you to connect your on-premises networks to the cloud, as well as connect different resources within the cloud itself. However, creating network connectivity can be a complex task, and it requires a number of different skills.

Administrators who need to create network connectivity in {{site.data.keyword.cloud_notm}} should have a strong understanding of the following topics:

* IP addressing and routing
* Cloud networking concepts
* IBM {{site.data.keyword.cloud_notm}} networking services

Administrators should also be familiar with the following tools and technologies:

* The {{site.data.keyword.cloud_notm}} console
* The {{site.data.keyword.cloud_notm}} CLI
* The {{site.data.keyword.cloud_notm}} SDKs
* Network monitoring and debugging tools

### {{site.data.keyword.cloud_notm}} offering descriptions and key differentiators
{: #offerings-key-points}

{{site.data.keyword.cloud_notm}} offers the following private connectivity services.

#### Direct Link Dedicated
{: #dedicated}

The {{site.data.keyword.cloud_notm}} Direct Link solution seamlessly connects your on-premises resources to your cloud resources, through a single-tenant, fiber-based, cross-connect terminated connection. This offering is also used by colocation facilities that are next to {{site.data.keyword.cloud_notm}} PoPs and data centers.

* Private access to {{site.data.keyword.cloud_notm}} using dedicated infrastructure.
* High cost for dedicated connectivity with increased bandwidth options.
* Single-tenant solution for maximum throughput.
* Optimal for large or frequent data transfers.

[Learn more](/docs/dl?topic=dl-get-started-with-ibm-cloud-dl#get-started-with-direct-link-dedicated)

#### Direct Link Connect
{: #connect}

Direct Link Connect uses a service provider to quickly establish and deliver connectivity to {{site.data.keyword.cloud_notm}} locations. These service providers are already connected to the {{site.data.keyword.cloud_notm}} network, and use multi-tenant, high capacity links (also known as network-to-network interfaces, or NNI).

* Private access to {{site.data.keyword.cloud_notm}} using shared infrastructure.
* Moderate cost, private and secure, shared infrastructure, and fast deployment.
* Ideal for multicloud environments with your server provider’s network.
* Virtual connectivity for rapid provisioning.

[Learn more](/docs/dl?topic=dl-get-started-with-ibm-cloud-dl#get-started-with-direct-link-connect)

#### Transit Gateway
{: #private-tgw}

Use {{site.data.keyword.cloud_notm}} Transit Gateway to interconnect {{site.data.keyword.cloud_notm}} resources and Virtual Private Cloud (VPC) infrastructures worldwide, keeping traffic within the {{site.data.keyword.cloud_notm}} network.

* Deliver your applications around the world, with global routing across the {{site.data.keyword.cloud_notm}} network.
* Simplify your network and build applications — without managing a distributed network.
* Scale and share {{site.data.keyword.cloud_notm}} services  like IBM classic infrastructure resources and IBM VPCs.
* Keep traffic within the {{site.data.keyword.cloud_notm}} network without traversing the public internet.

[Learn more](/docs/transit-gateway?topic=transit-gateway-getting-started)

#### VPN (site-to-site gateways)
{: #vpn-site-to-site}

You can use the {{site.data.keyword.cloud_notm}} VPN for VPC service to securely connect your Virtual Private Cloud (VPC) to another private network. Use a static, route-based VPN, or a policy-based VPN to set up an IPsec site-to-site tunnel between your VPC and your on-premises private network or another VPC.

* Protocol suite that provides secure communication between devices.
* Low-cost, [pay-as-you-go pricing](https://www.ibm.com/cloud/pricing/pay-as-you-go){: external}
* Configurable mechanism to detect the availability of an IPsec peer.
* Internet Key Exchange (IKE) is a part of the IPsec protocol that is used to establish VPN connections.
* Perfect Forward Secrecy (PFS) ensures that DH-generated keys aren't used again during IPsec renegotiation.
* Supports a pre-shared key for Phase 1 peer authentication. Supported authentication algorithms for both phases include SHA-256, SHA-384, and SHA-512.

[Learn more](/docs/vpc?topic=vpc-using-vpn)

#### VPN (client-to-site servers)
{: #vpn-client-to-site}

Client VPN for VPC provides client-to-site connectivity, which allows remote devices to securely connect to the VPC network using an OpenVPN software client. This solution is useful for telecommuters who want to connect to the {{site.data.keyword.cloud_notm}} from a remote location, such as a home office, while still maintaining secure connectivity.

* Multi-factor client authentication.
* Provides added layers of security with integrated authentication methods.
* Low cost, [pay-as-you-go pricing](https://www.ibm.com/cloud/pricing/pay-as-you-go){: external}.
* Availability in all MZRs' worldwide.
* Supports both stand-alone (pilot) and high availability (production) deployments.
* High availability spanning across zones, providing better performance and resiliency.
* TLS 1.2 / 1.3-based secure or encrypted connectivity over the internet.

[Learn more](/docs/vpc?topic=vpc-using-vpn)

#### Satellite Connector
{: #satellite}

Satellite Connector provides a lightweight solution for {{site.data.keyword.cloud_notm}} services to reach out to on-premises data sources. If bidirectional communication is needed, or Cloud services to be deployed on the client on-premises, refer to a [Satellite Location](/docs/satellite?topic=satellite-location-host).

* Provides client-owned L7 endpoints for {{site.data.keyword.cloud_notm}} services to access data on the client premise, rather than bridging on-premises networks with cloud like a VPN.
* Allows you to use your AWS, Azure, Google Cloud infrastructure, your on-premises hardware, or purchase from IBM/IBM partners.
* Uses internet or Direct Link for transport.
* Operated as-a-service by IBM.
* Use a single dashboard to centralize observability and management across all locations.
* Extend access policies, logging, monitoring, and other controls to all locations.
* Low cost, [pay-as-you-go pricing](https://www.ibm.com/cloud/pricing/pay-as-you-go){: external} without bandwidth capacity limitations.

If bidirectional communication is needed or the ability to deploy {{site.data.keyword.cloud_notm}} services on your on-premises or other cloud infrastructures are required, a Satellite Location provides more capabilities. For more information, see [Understanding Satellite location and hosts](/docs/satellite?topic=satellite-location-host).

[Learn more](/docs/satellite)

### Offering comparisons
{: #comparison-table}

#### Pricing
{: #pricing-comparison}

There are many factors to consider regarding pricing, such as peer configurations, dependent offerings, local providers. For example, a VPN site-to-site gateway or a VPN client-to-site server does not charge for an extra floating IP, and the pricing is also location-based.

To calculate pricing for {{site.data.keyword.cloud_notm}} offerings, use the [{{site.data.keyword.cloud_notm}} cost estimator](https://www.ibm.com/cloud/cloud-calculator){: external}.
{: important}

| {{site.data.keyword.cloud_notm}} service | High cost | Medium cost | Low cost |
|---------------|-------------|-------------|-------------|
| Direct Link Dedicated  | ![Checkmark icon](../icons/checkmark-icon.svg) | |
| Direct Link Connect  |  | ![Checkmark icon](../icons/checkmark-icon.svg) |
| Transit Gateway   | | ![Checkmark icon](../icons/checkmark-icon.svg) |
| VPN (site-to-site) | | |  ![Checkmark icon](../icons/checkmark-icon.svg) |
| VPN (client-to-site) | | | ![Checkmark icon](../icons/checkmark-icon.svg) |
| Satellite Connector | | | ![Checkmark icon](../icons/checkmark-icon.svg) |
{: caption="Pricing comparison" caption-side="bottom"}

#### Connectivity
{: #connectivity-comparison}

* Direct Link Dedicated: Connect VPC networks directly with physical connections.
* Direct Link Connect: Connect VPC networks through intermediate partner networks.
* Transit Gateway: Connect resources deployed in your VPC virtual networks with an Availability Zone (AZ) and between AZs.
* VPN (site-to-site): Connect private networks with private connectivity over the internet.
* VPN (client-to-site): Host a VPC network with private connectivity over the internet.
* Satellite Connector: Connect with secure TLS 1.3 endpoint-oriented communications over the internet or Direct Link.

#### Latency and bandwidth
{: #latency-bandwidth}

Direct Link offerings have the lowest latency followed by Satellite and VPN offerings. Latency is highly dependent on location.

Bandwidth:

* Direct Link Dedicated: Speeds up to 10 Gbps.
* Direct Link Connect: Speeds up to 5 Gbps.
* Transit Gateway: Speeds up to or in excess of 10 Gbps.
* VPN (site-to-site): Stand-alone mode up to 600 Mbps; High availability up to 1200 Mbps.
* VPN (client-to-site): Speeds up to 650 Mbps.
* Satellite Connector: Limited by client connectivity; maximum speed less than 1000 Mbps.

#### Provisioning time
{: #provisioning-time}

Provisioning time includes completing names and configuration parameters, as well as other dependencies and prerequisites.

* Direct Link Dedicated: 5-30 days
* Direct Link Connect: 3-5 days, depending on your provider (Provisioning on the IBM side is the same day.)
* Transit Gateway: 20-55 minutes
* VPN (site-to-site gateways): 20 minutes to one hour
* VPN (client-to-site servers): 20 minutes to one hour
* Satellite Connector: 10 minutes

#### Security and data encryption
{: #security-data-encryption-comparison}

All solutions that are listed are private and secure. For more information, see Security and data encryptions in the Reference section for each service.

#### Resiliency
{: #resiliency-comparison}

Solutions are diverse. To establish true redundancy, you must implement multiple connections to ensure that your solution meets your resiliency needs.

#### Monitoring and logging
{: #monitoring-logging-comparison}

Private connectivity options use various tools for monitoring and logging.

| {{site.data.keyword.cloud_notm}} service | Monitoring | Logging |
|---------------|-------------|-------------|
| Direct Link Dedicated | [Route reports](/docs/dl?topic=dl-generate-route-reports&interface=ui) | [Activity Tracker](/docs/dl?topic=dl-at_events&interface=ui) |
| Direct Link Connect | [Route reports](/docs/dl?topic=dl-generate-route-reports&interface=ui) | [Activity Tracker](/docs/dl?topic=dl-at_events&interface=ui) |
| Transit Gateway   | [{{site.data.keyword.cloud_notm}} Monitoring](/docs/vpc?topic=vpc-vpn-monitoring-metrics&interface=ui) | [Activity Tracker](/docs/transit-gateway?topic=transit-gateway-at_events&interface=ui) |
| VPN (site-to-site) | [{{site.data.keyword.cloud_notm}} Monitoring](/docs/vpc?topic=vpc-vpn-client-to-site-monitoring&interface=ui) | [IBM Log Analysis](/docs/vpc?topic=vpc-using-log-analysis-to-view-vpn-logs&interface=ui) |
| VPN (client-to-site) | [{{site.data.keyword.cloud_notm}} Monitoring](/docs/vpc?topic=vpc-vpn-client-to-site-monitoring&interface=ui) | [IBM Log Analysis](/docs/vpc?topic=vpc-client-vpn-log-analysis-c2s&interface=ui) |
| Satellite Connector | [{{site.data.keyword.cloud_notm}} Monitoring](/docs/satellite?topic=satellite-monitor) | [Activity Tracker](/docs/satellite?topic=satellite-at_events)  \n  \n [IBM Log Analysis](/docs/satellite?topic=satellite-health) |
{: caption="Monitoring and logging comparison" caption-side="bottom"}

## Deployment considerations
{: #deployment-considerations}

When planning your network architecture, it's important to consider the deployment factors to ensure optimal performance, reliability, and cost-effectiveness.

### Direct Link Dedicated deployment considerations
{: #direct-link-dedicated-deployment-considerations}

Here are some deployment considerations to review when choosing Direct Link Dedicated.

| Deployment consideration | Action |
|:----|:--------|
| Set up a second, diverse direct link to prevent outages. [Learn more](/docs/dl?topic=dl-models-for-diversity-and-redundancy-in-direct-link) |  |
| Review Direct Link Dedicated [prerequisites](/docs/dl?topic=dl-ibm-cloud-dl-prerequisites). | |
| Consider whether you want a metered or unmetered pricing plan. Metered has a lower port fee and charges a per GB usage free for egress traffic across the direct link. Unmetered billing has a higher port fee and no usage charges, which is ideal for customers who have higher egress traffic across their direct link. | |
| Review Direct Link Dedicated [planning considerations](/docs/dl?topic=dl-how-to-order-ibm-cloud-dl-dedicated#before-you-begin-dedicated) and [planning for virtual connections](/docs/dl?topic=dl-dl-planning-considerations#dl-planning-virtual-connections). | |
| Review Direct Link Dedicated [known limitations](/docs/dl?topic=dl-known-limitations). |   |
| Decide what type of network connection that you want to bind to your direct link. For example, you can create a direct, private connection between your on-premises network and {{site.data.keyword.cloud_notm}}, or bind your direct link to transit gateways. Your on-premises network can then access {{site.data.keyword.cloud_notm}} resources that are connected through the transit gateways. [Learn more](/docs/transit-gateway?topic=transit-gateway-about) | |
{: caption="Part 1: Direct Link Dedicated deployment considerations" caption-side="bottom"}

### Direct Link Connect deployment considerations
{: #direct-link-connect-deployment-considerations}

Here are some deployment considerations to review when choosing Direct Link Connect.

| Deployment consideration | Action |
|:----|:--------|
| Set up a second, diverse direct link to prevent outages? [Learn more](/docs/dl?topic=dl-models-for-diversity-and-redundancy-in-direct-link) |  |
| Contact your service provider to determine the location to {{site.data.keyword.cloud_notm}} by verifying your colocation or provider's capabilities to reach the Meet Me Room (MMR) and cross-connect into {{site.data.keyword.cloud_notm}}. Also, make sure that you understand your provider's deployment process.|  |
| Review Direct Link Connect [prerequisites](/docs/dl?topic=dl-ibm-cloud-dl-prerequisites). | |
| Consider whether you want a metered or unmetered pricing plan. Metered has a lower port fee and charges a per GB usage fee for egress traffic across the direct link. Unmetered billing has a higher port fee and no usage charges, which is ideal for customers who have higher egress traffic across their direct link. | |
| Review Direct Link Connect [planning considerations](/docs/dl?topic=dl-how-to-order-ibm-cloud-dl-connect&interface=ui#before-you-begin-connect) and [planning for virtual connections](/docs/dl?topic=dl-dl-planning-considerations#dl-planning-virtual-connections). |
| Review Direct Link Connect [known limitations](/docs/dl?topic=dl-known-limitations). |   |
| Decide whether you want to activate the optional BGP settings. See the following links for details. \n * [MD5 authentication](/docs/dl?topic=dl-enable-disable-md5&interface=ui)  \n * [bidirectional Forwarding Detection (BFD)](/docs/dl?topic=dl-activate-deactivate-bfd&interface=ui)  \n * [Prepending an AS path to influence route priority](/docs/dl?topic=dl-prepend-as-paths&interface=ui)  \n * [Route filtering](/docs/dl?topic=dl-filter-routes) | |
| Decide what type of network connection that you want to bind to your direct link. For example, you can create a direct, private connection between your on-premises network and {{site.data.keyword.cloud_notm}}, or bind your direct link to transit gateways. Your on-premises network can then access {{site.data.keyword.cloud_notm}} resources that are connected through the transit gateways. [Learn more](/docs/transit-gateway?topic=transit-gateway-about)  | |
{: caption="Part 1: Direct Link Connect deployment considerations" caption-side="bottom"}

### Transit Gateway deployment considerations
{: #tgw-deployment-considerations}

Here are some deployment considerations to review when choosing Transit Gateway.

| Deployment consideration | Action |
|:----|:--------|
| Have you decided which Transit Gateway location to use? | |
| Do you want to use local or global routing? Your choice depends on where the networks to be connected are located. [Learn more](/docs/transit-gateway?topic=transit-gateway-helpful-tips&interface=ui#routing-considerations)  | |
| Have you addressed any overlapping routes in the connected networks? Overlapping routes are a common issue when configuring a transit gateway. If the routes from two or more connections overlap, traffic might not be routed as intended. [Learn more](/docs/transit-gateway?topic=transit-gateway-route-reports&interface=ui#route-conflicts)| |
| Are there routes that you don't want advertised over the transit gateway? Do you need to create [prefix filters](/docs/transit-gateway?topic=transit-gateway-adding-prefix-filters)? | |
| Have you considered what connection type you plan to use? | |
| For a GRE tunnel or unbound GRE tunnel, have you configured redundant tunnels for high availability? There's no out-of-the-box redundancy with either GRE connection type. You must configure two GREs in different zones advertising the same routes to get redundancy. [Learn more](/docs/transit-gateway?topic=transit-gateway-helpful-tips&interface=ui#gre-considerations) |
{: caption="Part 1: Transit Gateway planning considerations" caption-side="bottom"}

Related link: [Planning for {{site.data.keyword.cloud_notm}} Transit Gateway](/docs/transit-gateway?topic=transit-gateway-helpful-tips)

### Site-to-site VPN deployment considerations
{: #s2s-vpn-deployment-considerations}

Here are some deployment considerations to review when choosing a VPN for VPC.

| Deployment consideration | Action |
|:----|:--------|
|Which {{site.data.keyword.cloud_notm}} region do you plan to deploy the VPCs? The regions might be closest to your on-premises site.| |
|What subnets in the VPC need to be connected through the VPN? Make sure that there's enough space in the subnet for the gateway.| |
|Is there a requirement to separate connectivity between your VPN and your resources, such as the virtual server instances into VPCs?| |
|How are your virtual server instances distributed in the VPC? VPN gateway is created in the zone that is associated with the subnet that you select and can be used to connect to virtual servers in the same zone. For zone fault tolerance, you can deploy one VPN gateway per zone.| |
|Do you need your on-premises network to access service endpoints through your site-to-site connectivity option?  \n Do you have resources in {{site.data.keyword.cloud_notm}} on Classic that you need to access through VPN or another connectivity option?|  |
|Do you have a peer VPN gateway or router (or multiple gateways/routers) setup on-premises? If yes, what is the type or model of that gateway? If your peer gateway enforces Perfect Forward Secrecy (PFS), you need to set custom policies.|  |
|What will be the CIDRs on-premises? Note that local (VPC) and peer (on-premises) subnets of a VPN gateway connection should not overlap or conflict.  /\n The local (VPC) subnet is specified when you create the VPN Gateway. For more information, see working with [Working with subnets in VPC](/docs/vpc?topic=vpc-subnets-configure).| |
|Is your VPN gateway on-premises behind a firewall doing Network Address Translation (NAT)?|  |
|Do you need the VPC resources to access the internet through VPN? Do you want any IP range to be blocked? |  |
{: caption="Part 1: Site-to-site VPN deployment considerations" caption-side="bottom"}

#### Performance and other things
{: #performance-c2s-vpn}

Here are some site-to-site connectivity deployment considerations and actions.

| Deployment consideration | Action |
|:----|:--------|
|What is the desired throughput of the site-to-site connectivity option (that is, Direct Link or VPN)? Is there a peak hour, month, or season?  \n Site-to-site VPN supports up to [650 Mbps of throughput](/docs/vpc?topic=vpc-faqs-vpn). Direct Link supports a much higher bandwidth up to 5 Gbps or 10 Gbps depending on your configurations. | |
|What is your expected cost for the connectivity option?  \n Site-to-site VPN uses a usage-based pricing that can be estimated by using the [Cost Estimator](https://www.ibm.com/cloud/cloud-calculator){: external}. Direct Link has multiple pricing plans, varies by provider, and has higher cost. See [Direct Link Dedicated] (/docs/private-connectivity?topic=private-connectivity-reference-direct-link-dedicated) and [Direct Link Connect](/docs/private-connectivity?topic=private-connectivity-reference-direct-link-connect) for more information.
| |
{: caption="Part 2. Site-to-site connectivity performance and other things" caption-side="bottom"}

### Client-to-site VPN deployment considerations
{: #c2s-vpn-deployment-considerations}

Here are some deployment considerations to review when choosing Client VPN for VPC.

| Deployment consideration | Action |
|:----|:--------|
|Do you need your individual users to have private and secure access (client-to-site servers) to your VPC resources from anywhere (for example, the airport, a hotel, or from home)? If yes, where are these users located?|  |
|Do you need your individual users to access service endpoints through your client-to-site VPN? These endpoints securely connect to {{site.data.keyword.cloud_notm}} services over the {{site.data.keyword.cloud_notm}} private network.|  |
|Client-to-site VPN is integrated with Secrets Manager for server authentication. Are you familiar with Secrets Manager and do you have an existing public/imported/private certificate with your Secrets Manager instance?|  |
|Client-to-site VPN supports three types of client authentication: a client certificate, added security with a user ID and passcode, or both. Which will be your preferred way of authenticating your users?| Client certificate / User ID/passcode / Both |
|Do you use client-to-site VPN for critical workload that requires a multi-zone deployment, or a pilot where multi-zone deployment is not a must?| |
|Do you need the VPN server to do SNAT making your VPN client IP invisible to the destination devices?|  |
{: caption="Part 1. Client-to-site VPN deployment considerations" caption-side="bottom"}

#### Performance and other things
{: #performance-c2s}

Here are some client-to-site connectivity deployment considerations and actions.

| Deployment consideration | Action |
|:----|:--------|
|If you need individual access to VPC (client-to-site connectivity) from remote, how many users can be connecting to VPC concurrently through VPN?|  |
|What is your expected cost for the connectivity option?  \n  \n Client-to-site VPN uses usage-based pricing that can be estimated by using the [Cost Estimator](https://www.ibm.com/cloud/cloud-calculator){: external}.  \n  \n Direct Link has multiple pricing plans, varies by provider, and has higher cost. See [Direct Link Dedicated](/docs/private-connectivity?topic=private-connectivity-reference-direct-link-dedicated) and [Direct Link Connect](/docs/private-connectivity?topic=private-connectivity-reference-direct-link-connect) for more information.|  |
{: caption="Part 2. Client-to-site performance and other things" caption-side="bottom"}

### Satellite Connector deployment considerations
{: #satellite-deployment-considerations}

Here are some deployment considerations to review when choosing a Satellite Connector.

| Deployment consideration | Action |
|----|-----|
| Do you need a lightweight, secure tunnel or gateway from {{site.data.keyword.cloud_notm}} back to your on-premises environment? If this describes your use case, see [Satellite Connector overview](/docs/satellite?topic=satellite-understand-connectors). | |
| Still, not sure which solution fits your use case? See more detailed [Satellite Location use cases](/docs/satellite?topic=satellite-use-case) or the [Satellite Connector capability comparison with Secure Gateway](/docs/satellite?topic=satellite-connector-and-secure-gateway#capability-comparison). | |
| Do you need to initiate communications from your on-premises to {{site.data.keyword.cloud_notm}}? In this case, a Satellite Location is required instead of a Satellite Connector. | |
| Do you need to route networks between your on-premises and {{site.data.keyword.cloud_notm}}? If so, consider a VPN or Direct Link connection. | |
| Do you also need to run {{site.data.keyword.cloud_notm}} services like Red Hat OpenShift on your own infrastructure, another cloud provider infrastructure, or on the edge? If this describes your use case, see [Understanding Satellite locations and hosts](/docs/satellite?topic=satellite-location-host). | |
{: caption="Satellite Connector deployment considerations" caption-side="bottom"}

## Use cases
{: #use-cases}

Explore typical scenarios where the connectivity method is most effective.

### Direct Link Dedicated use cases
{: #use-cases-direct-link-dedicated}

Primary use cases include transactional or batch data exchange across business-critical application workloads with high-volume and low-latency real-time access to software services and components across different clouds.

* Well suited for continuous high volume real-time data transfers between applications,  e.g., system data replication
* Direct physical connection provides a robust, reliable, and fast communication to support multiple protocols and complex workload connectivity requirements.

For Direct Link Dedicated use cases, see [Customer on-premises facility to {{site.data.keyword.cloud_notm}}](/docs/dl?topic=dl-dl-about#use-cases-dedicated) and [Customer colocation to {{site.data.keyword.cloud_notm}}](/docs/dl?topic=dl-dl-about#use-case-dedicated-2).

For a Power Edge Router (PER) use case for IBM Power System Virtual Server, see [Power Edge Router use cases](/docs/power-iaas?topic=power-iaas-network-architecture-diagrams#per-use-cases).

### Direct Link Connect use cases
{: #use-cases-connect}

* Primary use cases include transactional data exchange across business-critical application workloads with moderate to high volume and low latency requirements.
* Other use cases include on-demand or scheduled, real-time, near-real-time high volume batch data transfers between applications, such as for analytical processing, archiving, or replication.
* Application data exchange is done via RESTful APIs or TCP host/ports for synchronous/real-time calls between systems and components.
* Data transfers usually is done using sophisticated data migration and data replication applications.

#### Connecting to VPC by using Direct Link Connect
{: #connecting-to-vpc-using-connect}

Direct Link is a hybrid cloud connectivity service providing secure, private, high-bandwidth connectivity between customer on-premises and {{site.data.keyword.cloud_notm}} resources. Paired with Power Systems Virtual Servers and {{site.data.keyword.cloud_notm}} Transit Gateway, Direct Link offers options for high-bandwidth customer demand.

For Direct Link Connect use cases, see [Using service provider networks to virtually reach {{site.data.keyword.cloud_notm}}](/docs/dl?topic=dl-dl-about#use-case-connect-2) and [Other Cloud Service Provers (CSPs) or enterprises](/docs/dl?topic=dl-dl-about#connect-use-case-3).

For use cases with Power Systems Virtual Server, see [Network architecture diagrams](/docs/power-iaas?topic=power-iaas-network-architecture-diagrams).

### Transit Gateway use cases
{: #use-cases-transit-gateway}

As the number of your Virtual Private Clouds (VPCs) grows, you need an easy way to manage the interconnection between these resources across multiple regions. {{site.data.keyword.cloud_notm}} Transit Gateway is designed specifically for this purpose.

With {{site.data.keyword.cloud_notm}} Transit Gateway, you can create single or multiple transit gateways to connect VPCs together. You can also connect your {{site.data.keyword.cloud_notm}} classic infrastructure to a transit gateway to provide seamless communication with classic infrastructure resources. Any new network that you connect to a transit gateway is then automatically made available to every other network connected to it. This makes it easy to scale your network as it grows.

Transit gateways provide flexibility by allowing you to add networks to local gateways. Networks can be attached to multiple local gateways and a single global gateway, enabling you to keep local traffic on a local gateway.

#### Connecting two {{site.data.keyword.powerSys_notm}} environments by using {{site.data.keyword.cloud_notm}} Transit Gateway
{: #network-reference-architecture-tgw}

In this deployment topology, a connection through {{site.data.keyword.cloud_notm}} Transit Gateway is used to provide connectivity between Power virtual server environments at two different data centers. With {{site.data.keyword.cloud_notm}} Transit Gateway, you can also interconnect your {{site.data.keyword.powerSys_notm}}s to the {{site.data.keyword.cloud_notm}} classic and VPC infrastructures, keeping traffic within the {{site.data.keyword.cloud_notm}} network. Transit Gateway enables you to connect your otherwise disconnected private networks, such as classic, VPC, and {{site.data.keyword.dl_short}}. In addition, you can establish connection between multiple {{site.data.keyword.powerSys_notm}} workspaces across different data centers.

The following network architecture allows connectivity between multiple {{site.data.keyword.powerSys_notm}} locations with high availability (HA) and disaster recovery (DR) solutions.

![Transit Gateway deployment scenario](/images/network-tgw.svg "Transit Gateway use case"){: caption="Transit Gateway use case" caption-side="bottom"}

Key features are as follows:

   - Access and connectivity between two different {{site.data.keyword.powerSys_notm}} locations in the same region (for example DAL12 to DAL13) to support HA through replication.
   - Access and connectivity between two different {{site.data.keyword.powerSys_notm}} locations in different regions (for example DAL12 to WDC06) to support DR through replication.

With local routing you can only connect PERs in the same region as the Transit Gateway, while PERs in a different region require global routing.
{: note}

Complete the following steps to implement this scenario:

1. Create an [{{site.data.keyword.cloud_notm}} Transit Gateway](/interconnectivity/transit/provision){: external} to enable the virtual connections.
1. [Create an {{site.data.keyword.cloud_notm}} connection](/docs/power-iaas?topic=power-iaas-cloud-connections#create-cloud-connections) with Transit Gateway enabled.
1. Connect your {{site.data.keyword.powerSys_notm}}s that are located in data center 1 and data center 2 through the {{site.data.keyword.cloud_notm}} network by using a transit gateway.

After the transit gateway connection is established, different {{site.data.keyword.cloud_notm}} networks are connected to each other.

Related link: [Transit Gateway interconnectivity patterns](/docs/transit-gateway?topic=transit-gateway-about#patterns)

### Site-to-site VPN use cases
{: #use-cases-vpn-s2s}

Primary use cases include administrative remote access to various hosts across the cloud. Other use cases include low to moderate volume transactional or batch data exchange across business-critical application workloads tolerant to higher latency applications.

* Direct administrative access to hosts on the cloud is accomplished with jump servers, SSH, remote desktop protocol, and so on.
* Application data exchange is accomplished through RESTful APIs or TCP host/ports for synchronous/real-time calls between systems and components.
* Data transfer is accomplished using SFTP or simple data migration applications.

#### Site-to-Site VPN for secure connectivity using a policy-based VPN
{: #use-case-vpn-1}

Traffic that matches negotiated CIDR ranges passes through a policy-based VPN. You can use policy-based VPN gateways and ingress routing to forward POWER incoming traffic from transit gateways to your on-premises network. VPC 1 adds an on-premises CIDR as the VPC address prefix to allow route propagation.

![Site-to-site VPN use case](/images/VPN-s2s-usecase.png "Site-to-site VPN use case"){: caption="Site-to-site VPN use case" caption-side="bottom"}

Related link: [VPN for VPC use cases](/docs/vpc?topic=vpc-using-vpn#vpn-use-cases)

### Client-to-site VPN use cases
{: #use-cases-vpn-c2s}

Primary use cases include ad hoc or on-demand connectivity for low volume administrative remote access from a client host to hosts on a VPC network. Other use cases include ad hoc or on-demand low volume batch data transfers from a client host to hosts on a VPC network. These connections are tolerant to higher latency.

* Direct administrative access to hosts on the cloud is accomplished using jump servers, SSH, remote desktop protocol, and so on.
* Data transfer is accomplished using SFTP or simple data migration applications.

#### Client-to-site VPN for secure connectivity
{: #use-case-c2s-1}

With Client VPN for VPC (client-to-site VPN) you can securely connect from remote devices to the {{site.data.keyword.cloud_notm}} network using an OpenVPN client.

To access the resources in `VPC1`, in your routing table set **Accept routes from** to **VPN server** to allow route propagation by the VPN server.

To access resources in the `POWER VM`, in your routing table, create a VPN server route with the POWER network as the destination using the **Translate** action. This translates the source IP to the VPN server's private IP, making your VPN client IP invisible to the destination in the POWER network.

![Client-to-site VPN use case](/images/vpn-client-to-site.png "Client-to-site VPN use case"){: caption="Client-to-site VPN use case" caption-side="bottom"}

Related link: [VPN server use cases](/docs/vpc?topic=vpc-vpn-client-to-site-overview#vpn-client-to-site-use-cases)

### Satellite use cases
{: #use-cases-satellite}

* A Satellite Connector is a lightweight resource that provides secure TLS tunneling from {{site.data.keyword.cloud_notm}} applications and services to your on-premises resources.

* A Satellite Location expands on a Satellite Connector's capabilities by adding the ability for cloud services to be delivered on-premises, such as a managed Red Hat OpenShift on-premises or managed database on-premises. It also allows for communications originating from on-premises to resources inside of {{site.data.keyword.cloud_notm}}.

Related link: [Satellite Connector use cases](/docs/satellite?topic=satellite-use-case)

## Provisioning walk-throughs
{: #provisioning-walkthroughs}

Use the walk-throughs to understand the provisioning process for the connectivity method.

### Direct Link Dedicated provisioning walk-through
{: #provisioning-scenario-dedicated}

Direct Link Dedicated requires that you install an edge router (CER) to physically connect to the IBM cross-connect router (XCR) in the meet me room (MMR) at the {{site.data.keyword.cloud_notm}} location. The setup is initiated by requesting an LOA/CFA from IBM to proceed.

You are issued a letter of authorization (LOA) that allows you and your service provider to work with the {{site.data.keyword.cloud_notm}} site manager to install the CER. The site manager then provides a completion notice indicating that the install happened. This completion notice is approved by the IBM Implementation team for accuracy. After which, the team will ensure IBM side Layer-1 connectivity.

After there is compete Layer-1 connectivity (customer and IBM side), and the direct link is configured on the XCR and cross-connect switch (XCS), the provisioning process is complete. The direct link is now able to establish the boarder gateway protocol (BGP) session between the CER and XCR.

You must have your Direct Link planned and built out before ordering a dedicated direct link to prevent delays. The Dedicated Direct Link physical demarcation is a Patch page Port. It is up to the client to build to the Patch page Port. If this is the first Direct Link order or is a new order into a new region, please allow yourself plenty of time. Depending on where your network's Points Of Presence (PoPs) are, it can take 20 to 40 days to build out to an IBM site.
{: important}

When all prerequisites are met, the Direct Link Dedicated provisioning process takes approximately 4 weeks to complete. The provisioning process is as follows:

1. [1 day]{: tag-blue} - Read planning considerations and order a Dedicated direct link. For instructions, see [Ordering {{site.data.keyword.cloud_notm}} Direct Link Dedicated](/docs/dl?topic=dl-how-to-order-ibm-cloud-dl-dedicated).
1. [1 day]{: tag-blue} - You receive a letter of authorization (LOA), which allows your service provider to order and set up the cross-connect for your direct link. You are notified when the LOA becomes available for review on the {{site.data.keyword.cloud_notm}} console.
1. [Depends on customer]{: tag-blue} - Review the LOA with your service provider for accuracy and accept it. If anything is incorrect, discuss your concern with the IBM implementation team directly through this case.

   If the LOA is incorrect, or you have any questions, open a case with IBM Support case, upload your concerns or questions to the case.
   {: note}

1. [Depends on-site provider]{: tag-blue} - Give the approved LOA to your service provider. Work with your service provider to set up the cross-connect within your chosen {{site.data.keyword.cloud_notm}} location.
1. [Depends on customer]{: tag-blue} - Upload the completion notice received from your service provider on the {{site.data.keyword.cloud_notm}} console. Ensure that your physical connection is patched down between the device and patch page. Also, check to make sure you're sending light to IBM. For more information, see [How do I troubleshoot a Direct Link Dedicated connection during activation?](/docs/dl?topic=dl-troubleshoot-level-1) and this [completion notice example](/docs/dl?topic=dl-completion-notice-example).
1. [1-2 days]{: tag-blue} - The IBM Implementation team reviews the completion notice to ensure that it aligns with the LOA. If the completion notice is rejected, you are notified through an existing case or via the Direct Link console.
1. [1-4 days]{: tag-blue} - The IBM implementation team checks Layer-1 connectivity between the cross-connect router (XCR) and the Edge router and begins the patch cable installation process to established Layer-1 connectivity.
1. [1-4 days]{: tag-blue} - After the cross-connect completion notice is accepted, the patch cable installation between the {{site.data.keyword.cloud_notm}} device to the patch page begins.

   Some DC sites cannot work on the patch cable installation process until they receive management approval.
   {: note}

After connectivity is established successfully, your gateway moves to `Provisioned` status. Then, this case is closed. For further assistance with your direct link, contact [IBM Support](/unifiedsupport/supportcenter){: external}.

### Direct Link Connect provisioning walk-through
{: #provisioning-scenario-connect}

Use a service provider to quickly establish and deliver connectivity to {{site.data.keyword.cloud_notm}} locations. A service provider is already connected to the {{site.data.keyword.cloud_notm}} network via multi-tenant, high-capacity links, also known as a network-to-network interface (NNI). Typically, you can purchase a virtual circuit at this provider, establishing connectivity in a rapid manner because the physical connectivity from IBM to the service provider is already in place.

This offering is ideal for multicloud environments with your service provider's network.

Depending on your service provider, the Direct Link Connect provisioning process takes approximately 3 to 5 business days to complete. Provisioning on the IBM side is completed the same day. The provisioning process is as follows:

{{site.data.keyword.cloud_notm}} highly recommends that a second, diverse direct link be established to prevent outages, whether unplanned or planned due to maintenance.
{: important}

1. [1-2 days]{: tag-blue} - Contact your service provider. Determine the location to {{site.data.keyword.cloud_notm}} by verifying your provider capabilities to reach {{site.data.keyword.cloud_notm}} over partner interconnects known as NNIs.
1. [1-2 days]{: tag-blue} - Read planning considerations and order Direct Link Connect. For instructions, see [Ordering Direct Link Connect](/docs/dl?topic=dl-how-to-order-ibm-cloud-dl-connect).

    The IBM side is provisioned immediately after submitting your order in the {{site.data.keyword.cloud_notm}} console.
    {: note}

1. After you submit your order, contact your service provider and negotiate connectivity to your environment, whether it is on-premises or in colocation.
1. [Contact your provider for provisioning time]{: tag-blue} - Order a virtual circuit through the service provider. Reference the case ID of the Direct Link Connect request as your Request ID or Authorization ID.
1. [Contact your provider for provisioning time]{: tag-blue} - Configure the BGP parameters on your Edge router for BGP session establishment. After this completes, the BGP status indicates `Established`.

After connectivity is established successfully, your gateway moves to `Provisioned` status. Then, this case is closed. For further assistance with your direct link, contact [IBM Support](https://cloud.ibm.com/unifiedsupport/supportcenter){: external}.

### Transit Gateway provisioning walk-through
{: #provisioning-scenario-tgw}

Use {{site.data.keyword.cloud_notm}} Transit Gateway to interconnect {{site.data.keyword.cloud_notm}} resources and Virtual Private Cloud (VPC) infrastructures worldwide, keeping traffic within the {{site.data.keyword.cloud_notm}} network.

The provisioning process takes approximately 20-55 minutes to complete. The provisioning process is as follows:
1. [5-10 mins]{: tag-blue} - Review [Planning for {{site.data.keyword.cloud_notm}} Transit Gateway](/docs/transit-gateway?topic=transit-gateway-helpful-tips) and plan the networks to be connected.
1. [5-20 mins]{: tag-blue} - [Create a transit gateway](/docs/transit-gateway?topic=transit-gateway-ordering-transit-gateway&interface=ui).
1. [5-20 mins]{: tag-blue} - [Add desired network connections](/docs/transit-gateway?topic=transit-gateway-adding-connections&interface=ui) to the transit gateway. These can be added while the gateway is still provisioning.
1. [5 mins]{: tag-blue} - Verify that you can ping between networks via the transit gateway.

### Site-to-site VPN provisioning walk-through
{: #provisioning-scenario-vpn-s2s}

You can use the {{site.data.keyword.cloud_notm}} VPN for VPC service to securely connect your Virtual Private Cloud (VPC) to another private network. Use a static, route-based VPN, or a policy-based VPN to set up an IPsec site-to-site tunnel between your VPC and your on-premises private network or another VPC.

The provisioning process takes approximately 20 minutes to one hour to complete. The provisioning process is as follows:

1. [10 mins]{: tag-blue} - Review [planning considerations for VPN gateways](/docs/vpc?topic=vpc-planning-considerations-vpn&interface=ui) and plan for local/remote CIDRs. Also, review [VPN gateway limitations](/docs/vpc?topic=vpc-vpn-limitations) and [configuration information](/docs/vpc?topic=vpc-using-vpn&interface=ui), such as IKE policies, mode.
1. [10 mins]{: tag-blue} - Create a VPN gateway using the [{{site.data.keyword.cloud_notm}} console](/docs/vpc?topic=vpc-creating-a-vpc-using-the-ibm-cloud-console) or with the [CLI and API](/docs/vpc?topic=vpc-creating-vpc-resources-with-cli-and-api&interface=cli). Review [ACLs and security groups](/docs/vpc?topic=vpc-acls-security-groups-vpn).
1. [5-10 mins, depending on the gateway type]{: tag-blue} - Make sure that your peer device supports NAT traversal and that it is enabled on the peer device.
1. [5 mins]{: tag-blue} - [Create a VPN gateway](/docs/vpc?topic=vpc-vpn-create-gateway).
1. [5 mins]{: tag-blue} - [Create VPN connections](/docs/vpc?topic=vpc-vpn-adding-connections).
1. [5 mins]{: tag-blue} - For static, route-based VPNs, select or [create a routing table for static routing](/docs/vpc?topic=vpc-create-vpc-routing-table), then [create routes](/docs/vpc?topic=vpc-create-vpc-route) by using the **VPN connection** type.
1. [10-20 mins, depending on the gateway type]{: tag-blue} - [Connect to an on-premises network through a VPN tunnel](/docs/vpc?topic=vpc-vpn-onprem-example).
1. [5 mins]{: tag-blue} - Verify that your VPN connection is available by sending ping or data traffic across the tunnel to devices that are on the peer network.

### Client-to-site VPN provisioning walk-through
{: #provisioning-scenario-vpn-c2s}

Client VPN for VPC provides client-to-site connectivity, which allows remote devices to securely connect to the VPC network using an OpenVPN software client. This solution is useful for telecommuters who want to connect to the {{site.data.keyword.cloud_notm}} from a remote location, such as a home office, while still maintaining secure connectivity.

The provisioning process takes approximately 20 minutes to one hour to complete. The provisioning process is as follows:

1. [10 mins]{: tag-blue} - Review [planning considerations for VPN servers](/docs/vpc?topic=vpc-client-to-site-vpn-planning) and decide which VPN client authentication that you want to use: certificate-based, user ID and passcode, or both. For more information, see [Setting up client-to-site authentication](/docs/vpc?topic=vpc-client-to-site-authentication).
1. [10 mins]{: tag-blue} - For user ID and passcode authentication only, [create an IAM access group and grant users the role to connect to the VPN server](/docs/vpc?topic=vpc-create-iam-access-group).
1. [15 mins]{: tag-blue} - [Create a Secrets Manager instance and import certificates](/docs/vpc?topic=vpc-client-to-site-authentication#creating-cert-manager-instance-import).
1. [10 mins]{: tag-blue} - [Create a VPC](/docs/vpc?topic=vpc-creating-a-vpc-using-the-ibm-cloud-console#creating-a-vpc-and-subnet). Optionally, [configure security groups and ACLs for use with VPN](/docs/vpc?topic=vpc-vpn-client-to-site-security-groups).

   **Notes:**

   * For a high available VPN server, create a VPC and two subnets in two different zones.
   * For a stand-alone VPN server, create a VPC and one subnet in one zone.
   * Ensure your security groups and ACLs allow VPN traffic.
   * When creating a new VPC, the default security group that is attached only allows ICMP and SSH communications. Ensure that you add an inbound rule for client-to-site VPN traffic in this security group.
1. [5 mins]{: tag-blue} - For server authentication only, [create IAM service-to-service authorization](/docs/vpc?topic=vpc-client-to-site-authentication#creating-iam-service-to-service).
1. [5 mins]{: tag-blue} - [Create a VPN server](/docs/vpc?topic=vpc-vpn-create-server) and validate status.
1. [5 mins]{: tag-blue} - [Create VPN routes](/docs/vpc?topic=vpc-vpn-client-to-site-routes).
1. [10 mins]{: tag-blue} - [Set up a VPN client environment and connect to the VPN server](/docs/vpc?topic=vpc-vpn-client-environment-setup).

### Satellite Connector provisioning walk-through
{: #provisioning-scenario-satellite}

Satellite Connector provides secure TLS tunneling from {{site.data.keyword.cloud_notm}} applications and services to your on-premises applications.

- [Connector overview](/docs/satellite?topic=satellite-understand-connectors)
- [Connector end-to-end example](/docs/satellite?topic=satellite-end-to-end)

## Reference
{: #reference}

Reference for understanding the key aspects of connectivity and implementation.

### Direct Link Dedicated
{: #reference-direct-link-dedicated}

Provides additional information on the Direct Link Dedicated offering.

#### Pricing
{: #reference-pricing-dedicated}

To calculate pricing for {{site.data.keyword.cloud_notm}} offerings, use the [{{site.data.keyword.cloud_notm}} cost estimator](https://www.ibm.com/cloud/cloud-calculator){: external}.
{: tip}

* High cost
* Dedicated connectivity with increased bandwidth options.
* Cost varies by network service provider.
* Costs are typically structured based on bandwidth limits, port charges (fixed or metered per GB of data), volume of data egress from VPC through the connection gateway, and so on.
* {{site.data.keyword.cloud_notm}} offers two pricing plans - metered and unmetered. With metered pricing, you pay only for what you use. Unmetered means unlimited access, for a monthly fee.

#### Connectivity
{: #reference-connectivity-dedicated}

* Connect the VPC networks directly with physical connections.
* The connection is established between the network provider and {{site.data.keyword.cloud_notm}} at a colocation data center facility common to both parties.
* The connection is private, not encrypted, bypasses the internet, and is a dedicated single-tenant network connection.

#### Latency and bandwidth
{: #reference-latency-bandwidth-dedicated}

* Lowest latency, single tenant, with high-bandwidth options.
* Higher maximum limits apply to throughput capacity, depending on the selected offerings from the network service provider.
* Available in speeds up to 10 Gbps.

#### Provisioning
{: #reference-provisioning-dedicated}

* Requires the provisioning of physical connections at the colocation facility. The provisioning is done through a semi-self-service process with support and assistance from the network service provider and colocation facility partner.
* The provisioning process can take several days (typically 5 to 30), depending on the network service provider’s colocation facility partner offerings, contracting process, and exchange of technical details to set up connectivity.
* Lower flexibility to make changes and adapt to changes in workload locations due to physical connectivity, contracting, and colocation dependencies.
* Detailed long-term planning is required, specific to the workload location and connectivity service providers available at the colocation facility.
* {{site.data.keyword.cloud_notm}} Direct Link Dedicated has partnerships with various colocation/data center operators.

Related links:
* [Ordering](/docs/dl?topic=dl-how-to-order-ibm-cloud-dl-dedicated)
* [Locations](/docs/dl?topic=dl-locations#dedicated-locations)
* [FAQs](/docs/dl?topic=dl-faqs&interface=ui)
* [Limitations](/docs/dl?topic=dl-known-limitations&interface=ui)
* [Access management](/docs/dl?topic=dl-iam&interface=ui)
* [Responsibilities](/docs/dl?topic=dl-dl-responsibilities)
* [View egress usage](/docs/dl?topic=dl-faqs#view-egress-usage)

#### Security and data encryption
{: #reference-security-data-encryption-dedicated}

* Workload data that is transmitted across the network connections is usually not encrypted by the providers and is the customer's responsibility.
* Encryption is highly recommended and can be achieved at application level, for example with TLS encryption between the application client/severs.
* Optionally, a VPN can be set up on the connection to get a secure tunnel between endpoint subnetworks.
* The offering configuration and control data are encrypted in-transit and at-rest at the database level.  [Learn more](/docs/dl?topic=dl-mng-data#data-storage)

#### Resiliency
{: #reference-resiliency-dedicated}

* Depends on the availability requirements. Additional connections can be provisioned in the same or different PoPs (Points of Presence) to achieve higher resiliency.
* Optionally, for a lower-cost redundant alternative, a VPN or partner network connectivity can be provisioned and used as a fallback.

Related links:
* [Achieving redundancy](/docs/dl?topic=dl-faqs#how-can-i-achieve-redundancy-with-ibm-cloud-dl)
* [Models for diversity and redundancy](/docs/dl?topic=dl-models-for-diversity-and-redundancy-in-direct-link)
* [High availability](/docs/dl?topic=dl-ha)
* [Business continuity and disaster recovery](/docs/dl?topic=dl-bc-dr)

#### Monitoring and logging
{: #reference-monitoring-logging-dedicated}

Direct Link Dedicated uses a combination of IBM Activity Tracker and the {{site.data.keyword.cloud_notm}} Console for log analysis and metrics monitoring.

##### Direct Link Dedicated log analysis
{: #dld-logging}

You can use the Activity Tracker service to track how users and applications interact with Direct Link Dedicated in {{site.data.keyword.cloud_notm}}.

{{site.data.keyword.cloud_notm}} Activity Tracker records user-initiated activities that change the state of a service in {{site.data.keyword.cloud_notm}}. You can use this service to investigate abnormal activity and critical actions and to comply with regulatory audit requirements. In addition, you can be alerted about actions as they happen. The events that are collected comply with the Cloud Auditing Data Federation (CADF) standard. For more information, refer to [Auditing events for {{site.data.keyword.cloud_notm}} Direct Link](/docs/dl?topic=dl-at_events&interface=ui).

##### Direct Link Dedicated metrics monitoring
{: #dld-metrics}

You can generate a report of all routes that are known to a direct link and its connections. This report allows you to verify the expected routes, view what virtual connections are contributing which routes to your direct link, and see next-hop address details of the routes received. If you are using the cross-account VPC linking feature, you can also see which prefixes or subnets are being routed through your cross-connect router. For more information, refer to [Generating a direct-link route report](/docs/dl?topic=dl-generate-route-reports&interface=ui).

### Direct Link Connect
{: #reference-direct-link-connect}

This topic provides additional information on the Direct Link Connect offering.

#### Pricing
{: #reference-pricing-connect}

To calculate pricing for {{site.data.keyword.cloud_notm}} offerings, use the [{{site.data.keyword.cloud_notm}} cost estimator](https://www.ibm.com/cloud/cloud-calculator){: external}.
{: tip}

* Moderate cost
* Varies by cloud provider and partner network offerings
* Costs are typically structured based on routing options, bandwidth limits, cross-connect port charges (fixed or metered per GB of data), volume of data egress from VPC through the connection gateway, and so on.
* {{site.data.keyword.cloud_notm}} offers two pricing plans - metered and unmetered. With metered pricing, you pay only for what you use. Unmetered means unlimited access, for a monthly fee.

#### Connectivity
{: #reference-connectivity-connect}

* Connect the VPC networks through intermediate partner networks
* Partners have pre-established connectivity with cloud provider networks and provide an exchange for cross-connections and routing between the cloud networks.
* The connection is private, not encrypted, bypasses the internet, and is over a multi-tenant, shared network.

#### Latency and bandwidth
{: #reference-latency-bandwidth-connect}

* Reliable, consistent, and lower latencies, higher security as connections bypass the internet.
* Maximum limits apply to throughput capacity, depending on the selected partner offerings from the cloud provider.
* Available in speeds up to 5 Gbps.

#### Provisioning
{: #reference-provisioning-connect}

* Requires the provisioning of connectivity ports on the peer VPCs to connect the VPC to the partner network, as well as the provisioning of the cross-connect between the peer cloud ports on the partner network. Provisioning is done using self-service or semi-self-service processes available from {{site.data.keyword.cloud_notm}} and partner service providers.
* The provisioning process typically takes 2-10 days and utilizes pre-established partnerships and contracts, but depends on offerings used from the cloud service provider and partner service provider.
* Provides flexibility to make changes and adapt to changes in workload locations.
* Must ensure the partner network supports cross-connecting the relevant cloud provider data center locations.
* {{site.data.keyword.cloud_notm}} Direct Link Connect has partnerships with over 45 global service providers.

Related links:
* [Ordering](/docs/dl?topic=dl-how-to-order-ibm-cloud-dl-connect)
* [Providers and locations](/docs/dl?topic=dl-locations#connect-locations)
* [FAQs](/docs/dl?topic=dl-faqs&interface=ui)
* [Limitations](/docs/dl?topic=dl-known-limitations&interface=ui)
* [Access management](/docs/dl?topic=dl-iam&interface=ui)
* [Responsibilities](/docs/dl?topic=dl-dl-responsibilities)
* [View egress usage](/docs/dl?topic=dl-faqs#view-egress-usage)

#### Security and data encryption
{: #reference-security-data-encryption-connect}

* Workload data that is transmitted across the network connections is usually not encrypted by the providers and is the customer's responsibility.
* Encryption is highly recommended and can be achieved at application level, for example with TLS encryption between the application client/severs.
* Optionally, VPN can be set up on the connection to get a secure tunnel between endpoint subnetworks.
* The offering configuration and control data is encrypted in-transit and at-rest at the database level. [Learn more](/docs/dl?topic=dl-mng-data#data-storage)

#### Resiliency
{: #reference-resiliency-connect}

* Depends on the offerings. Typically requires a second connection to be configured using different availability zones and different cross connect routers (XCRs) to achieve HA.
* Leverages SND by provisioning a virtual circuit across a bank of physical XCRs, which allows for failure of one physical device without connectivity failure. Additional connections can be provisioned to provide higher resiliency.
* Optionally, for a low-cost redundant alternative, a VPN can be provisioned and used as fallback.

Related links:
* [Achieving redundancy](/docs/dl?topic=dl-faqs#how-can-i-achieve-redundancy-with-ibm-cloud-dl)
* [Models for diversity and redundancy](/docs/dl?topic=dl-models-for-diversity-and-redundancy-in-direct-link)
* [High availability](/docs/dl?topic=dl-ha)
* [Business continuity and disaster recovery](/docs/dl?topic=dl-bc-dr)

#### Monitoring and logging
{: #reference-monitoring-logging-connect}

Direct Link Connect uses a combination of IBM Activity Tracker and the {{site.data.keyword.cloud_notm}} Console for log analysis and metrics monitoring.

##### Direct Link Connect log analysis
{: #dlc-logging}

You can use the Activity Tracker service to track how users and applications interact with Direct Link Connect in {{site.data.keyword.cloud_notm}}.

{{site.data.keyword.cloud_notm}} Activity Tracker records user-initiated activities that change the state of a service in {{site.data.keyword.cloud_notm}}. You can use this service to investigate abnormal activity and critical actions and to comply with regulatory audit requirements. In addition, you can be alerted about actions as they happen. The events that are collected comply with the Cloud Auditing Data Federation (CADF) standard. For more information, refer to [Auditing events for {{site.data.keyword.cloud_notm}} Direct Link](/docs/dl?topic=dl-at_events&interface=ui).

##### Direct Link Connect metrics monitoring
{: #dlc-metrics}

You can generate a report of all routes that are known to a direct link and its connections. This report allows you to verify the expected routes, view what virtual connections are contributing which routes to your direct link, and see next-hop address details of the routes received. If using the cross-account VPC linking feature, you can also see which prefixes or subnets are being routed through your cross-connect router. For more information, refer to [Generating a direct link route report](/docs/dl?topic=dl-generate-route-reports&interface=ui).

### Transit Gateway
{: #reference-transit-gateway}

This topic provides additional information on the Transit Gateway offering.

#### Pricing
{: #reference-pricing-transit-gateway}

To calculate pricing for {{site.data.keyword.cloud_notm}} offerings, use the [{{site.data.keyword.cloud_notm}} cost estimator](https://www.ibm.com/cloud/cloud-calculator){: external}.
{: tip}

* Moderate cost
* Costs are derived from the number of networks connected to the gateway, is the gateway that is enabled for local or global routing, volume of traffic through the gateway, and so on.

#### Connectivity
{: #reference-connectivity-transit-gateway}

{{site.data.keyword.cloud_notm}} provides:
* A private backbone for all connectivity between resources deployed in your VPC virtual networks with an AZ and between AZs (this backbone is separate from the public backbone for connectivity using public addressing). IP addresses on the private backbone are non-internet routable, or not announced toward the public backbone or the internet. The private backbone is owned, managed, and operated exclusively by {{site.data.keyword.cloud_notm}}.
* {{site.data.keyword.cloud_notm}} Transit Gateway uses this private backbone exclusively for connectivity between your virtual networks within a single region, across multiple regions, and to your {{site.data.keyword.cloud_notm}} classic workloads.

Transit gateways connect:
   - VPCs in the same region (local routing)
   - VPCs in different regions (global routing)
   - VPCs to your {{site.data.keyword.cloud_notm}} classic infrastructure
   - Networks using a Generic Routing Encapsulation (GRE) tunnel
   - On-premise networks using Direct Link to your {{site.data.keyword.cloud_notm}} networks

#### Latency and bandwidth
{: #reference-latency-bandwidth-transit-gateway}

* Reliable, high throughput, purely contained within the Cloud network.
* Can traverse multiple regions if connecting networks in disparate locations.
* Speeds up to or in excess of 10 Gbps.

#### Provisioning
{: #reference-provisioning-transit-gateway}

With {{site.data.keyword.cloud_notm}} Transit Gateway, you can connect:
* VPCs in the same region (local routing)
* VPCs in different regions (global routing)
* VPCs to your {{site.data.keyword.cloud_notm}} classic infrastructure
* Networks using a Generic Routing Encapsulation (GRE) tunnel
* On-premise networks using Direct Link to your {{site.data.keyword.cloud_notm}} networks
* Ordered and configured through {{site.data.keyword.cloud_notm}} UI, CLI or API.

Related links:
* [Locations](/docs/transit-gateway?topic=transit-gateway-tg-locations)
* [Ordering a Transit Gateway](/docs/transit-gateway?topic=transit-gateway-ordering-transit-gateway&interface=ui)
* [FAQs](/docs/transit-gateway?topic=transit-gateway-faqs-for-transit-gateway)
* [Adding Connection to Transit Gateway](/docs/transit-gateway?topic=transit-gateway-adding-connections&interface=ui)
* [Responsibilities](/docs/transit-gateway?topic=transit-gateway-tg-responsibilities)

#### Security and data encryption
{: #reference-security-data-encryption-transit-gateway}

* Workload data transmitted across the network connections is not encrypted by the provider and is the customer's responsibility.
* Encryption is highly recommended and can be achieved at application level, for example with TLS encryption between the application client/severs.
* The offering configuration and control data is encrypted in-transit and at-rest at the database level. [Learn more](/docs/transit-gateway?topic=transit-gateway-mng-data#data-storage)

#### Resiliency
{: #reference-resiliency-transit-gateway}

{{site.data.keyword.cloud_notm}} Transit Gateway is highly available within any {{site.data.keyword.cloud_notm}} location (for example, Dallas or Washington, DC). However, recovering from disasters that affect an entire location requires planning and preparation.

You are responsible for understanding your configuration, customization, and usage of the service. You are also responsible for being ready to re-create an instance of the service in a new location and restore your data in a new location.

Related links:

* [High Availability](/docs/transit-gateway?topic=transit-gateway-ha)
* [Business continuity and disaster recovery](/docs/transit-gateway?topic=transit-gateway-bc-dr)

#### Monitoring and logging
{: #reference-monitoring-logging-transit-gateway}

##### Transit Gateway log analysis
{: #tgw-logging}

You can use the Activity Tracker service to track how users and applications interact with Transit Gateway in {{site.data.keyword.cloud_notm}}.

{{site.data.keyword.cloud_notm}} Activity Tracker records user-initiated activities that change the state of a service in {{site.data.keyword.cloud_notm}}. You can use this service to investigate abnormal activity and critical actions and to comply with regulatory audit requirements. In addition, you can be alerted about actions as they happen. The events that are collected comply with the Cloud Auditing Data Federation (CADF) standard. For more information, refer to [Auditing events for {{site.data.keyword.cloud_notm}} Transit Gateway](/docs/transit-gateway?topic=transit-gateway-at_events&interface=ui).

##### Transit Gateway metrics monitoring
{: #tgw-metrics}

You can generate a report of all routes known to a gateway and its connections. This report allows you to verify the expected routes, view what connections are contributing which routes to your gateway, and see BGP information on routes received. This report contains routes from same account networks, and from networks connected using the cross-account connection capability. For more information, refer to [Generating a Transit Gateway route report](/docs/transit-gateway?topic=transit-gateway-route-reports&interface=ui).

### Site-to-site VPN
{: #reference-site-to-site-vpn}

This topic provides additional information on the VPN for VPC offering.

#### Pricing
{: #reference-pricing-vpn-s2s}

To calculate pricing for {{site.data.keyword.cloud_notm}} offerings, use the [{{site.data.keyword.cloud_notm}} cost estimator](https://www.ibm.com/cloud/cloud-calculator){: external}.
{: tip}

* Low cost, [pay-as-you-go](https://www.ibm.com/cloud/pricing/pay-as-you-go){: external} pricing
* Costs are typically associated with the type of VPN gateway, usage hours, connection hours, and public IP addresses, volume of data egress from VPC through the gateway, and so on.

#### Connectivity
{: #reference-connectivity-vpn-s2s}

* Connect private networks with private connectivity over the internet.
* The cloud provider's internet service provider (ISP) provides connection to the internet.
* The connection is shared with internet users, is private and encrypted, and uses a secure tunnel.

#### Latency and bandwidth
{: #reference-latency-bandwidth-vpn-s2s}

* Susceptible to the inherent variability in internet connectivity, latency, and bandwidth fluctuations.
* Connection path might not be the shortest and might also traverse multiple hops, resulting in higher latencies.
* Latency can be minimized if the data center location where the VPN host and server are provisioned are geographically close (in the same region).
* Maximum limits usually apply to throughput capacity, depending on the cloud provider's VPN offering.
* The {{site.data.keyword.cloud_notm}} offerings provide two options - stand-alone (up to 600 Mbps) and HA (up to 1200 Mbps).

#### Provisioning
{: #reference-provisioning-vpn-s2s}

* Requires VPN gateways deployed on each peer VPC network. VPNs use network connectivity resources from cloud service provider's ISPs that connect the public clouds and VPCs to the internet.
* Most cloud providers offer VPN-as-a-service: self-service provisioning of the VPN gateway and connections to establish secure private connection.
* Provides flexibility to make changes by adding/removing connections quickly and by modifying subnets included in the tunnel.

Related links:
* [Creating a VPN gateway](/docs/vpc?topic=vpc-vpn-create-gateway&interface=ui)
* [FAQs](/docs/vpc?topic=vpc-faqs-vpn)
* [Limitations](/docs/vpc?topic=vpc-vpn-limitations)
* [Quotas](/docs/vpc?topic=vpc-quotas#vpn-quotas)
* [Access management](/docs/vpc?topic=vpc-iam-getting-started)
* [Responsibilities](/docs/vpc?topic=vpc-responsibilities-vpc)

#### Security and data encryption
{: #reference-security-data-encryption-vpn-s2s}

* Uses IPsec secure encrypted tunnel between networks exchanging workload data; uses Internet Key Exchange (IKE) encryption, and Pre-Shared Key (PSK) authentication.
* Appropriate access controls and network ports must be configured on the VPC networks for applications to communicate with each other. [Learn more](/docs/vpc?topic=vpc-mng-data&interface=ui#data-storage) (Search for `VPN` in this link.)

#### Resiliency
{: #reference-resiliency-vpn-s2s}

* Depends on the VPN cloud offering. Typically, two VPN gateways are provisioned in the same availability zones and provide appliance-level redundancy/HA.
* Appropriate selection of locations can help in planning for HA/DR.
* {{site.data.keyword.cloud_notm}} VPN gateway consists of two back-end instances in the same zone for high availability. Recommended to provision a gateway in each availability zone for zone fault tolerance.

Related link: [VPN gateway high availability](/docs/vpc?topic=vpc-vpn-ha&interface=ui)

#### Monitoring and logging
{: #reference-monitoring-logging-vpn-s2s}

VPN (site-to-site) gateways use a combination of IBM Log Analysis and {{site.data.keyword.cloud_notm}} Monitoring for log analysis and metrics monitoring.

##### Site-to-site log analysis
{: #s2s-logging}

You can use IBM Log Analysis to view application and connection logs from your {{site.data.keyword.cloud_notm}} VPN (site-to-site) for VPC. IBM Log Analysis offers administrators, DevOps teams, and developers advanced features to filter, search, and tail log data, define alerts, and design custom views to monitor application and system logs.

For more information, refer to [Using IBM Log Analysis to view VPN logs](/docs/vpc?topic=vpc-using-log-analysis-to-view-vpn-logs&interface=ui).

##### Site-to-site metrics monitoring
{: #s2s-metrics}

{{site.data.keyword.cloud_notm}} Monitoring collects basic VPN metrics on {{site.data.keyword.cloud_notm}} for VPC, such as VPN gateway status, VPN gateway packets input/output, and VPN connection bytes input/output. These metrics are stored in {{site.data.keyword.cloud_notm}} Monitoring. You can access metrics through the prebuilt dashboard.

For more information, refer to [Monitoring VPN gateway for VPC metrics](/docs/vpc?topic=vpc-vpn-monitoring-metrics&interface=ui).

Related link: [VPN gateway events](/docs/vpc?topic=vpc-at_events#events-vpns)

### Client-to-site VPN
{: #reference-client-to-site-vpn}

This topic provides additional information on the Client VPN for VPC offering.

#### Pricing
{: #reference-pricing-vpn-c2s}

To calculate pricing for {{site.data.keyword.cloud_notm}} offerings, use the [{{site.data.keyword.cloud_notm}} cost estimator](https://www.ibm.com/cloud/cloud-calculator){: external}.
{: tip}

* Low cost, [pay-as-you-go](https://www.ibm.com/cloud/pricing/pay-as-you-go){: external} pricing
* Costs are typically associated with the type of VPN server, usage hours, aggregated connection hours, and public IP addresses, volume of data egress from the VPC, and so on.

#### Connectivity
{: #reference-connectivity-vpn-c2s}

* It connects a client host to a VPC network with private connectivity over the internet.
* The cloud provider's internet service provider (ISP) provides connection to the internet.
* The connection is shared with internet users, is private and encrypted, and uses a secure tunnel.

#### Latency and bandwidth
{: #reference-latency-bandwidth-vpn-c2s}

* Susceptible to the inherent variability in internet connectivity, latency, and bandwidth fluctuations.
* Connection path may not be the shortest and may traverse multiple hops, resulting in higher latencies.
* Latency can be minimized if the data center location where the VPN gateways are provisioned are geographically close (in the same region).
* Maximum limits usually apply to throughput capacity, depending on the cloud provider's VPN offering.
* This {{site.data.keyword.cloud_notm}} offering provides speeds up to 650 Mbps.

#### Provisioning
{: #reference-provisioning-vpn-c2s}

* Requires the provisioning of a VPN server on the VPC network; The VPN uses network connectivity resources from cloud service provider's ISPs that connect the public clouds and VPCs to the internet. VPN client software (OpenVPN) is required on the client host to connect to the VPN server and its network.
* Most cloud providers offer VPN-as-a-service: self-service provisioning of VPN server and connections to establish secure private connection. For a client-to-site VPN, a software client must be installed.
* Provides a flexible host to network connectivity and quick provisioning.

Related links:
* [Creating a VPN server](/docs/vpc?topic=vpc-vpn-create-server&interface=ui)
* [FAQs](/docs/vpc?topic=vpc-faqs-vpn-server)
* [Limitations](/docs/vpc?topic=vpc-vpn-client-vpn-limitations)
* [Quotas](/docs/vpc?topic=vpc-quotas#vpn-server-quotas)
* [Access management](/docs/vpc?topic=vpc-iam-getting-started)
* [Responsibilities](/docs/vpc?topic=vpc-responsibilities-vpc)

#### Security and data encryption
{: #reference-security-data-encryption-vpn-c2s}

* Uses TLS 1.2/1.3 encryption
* Multi-factor authentication can be applied to VPN server and client connections to provide an added layer of security to meet compliance and security requirements.

Related link: [Securing your environment with VPN server](/docs/vpc?topic=vpc-client-to-site-vpn-securing-environment)

#### Resiliency
{: #reference-resiliency-vpn-c2s}

* Depends on the VPN cloud offering. Typically, two VPN servers are provisioned in different availability zones and provide appliance-level redundancy/HA.
* An appropriate selection of locations can help in planning for HA/DR. {{site.data.keyword.cloud_notm}} offering provides two modes:
   * High-availability mode: Deploys the VPN server across two subnets in different zones. Best for multi-zone deployments and solutions where client VPN access is critical.
   * Stand-alone mode: Deploys the VPN server in a single subnet and zone. Best for nonproduction use where multi-zone resiliency is not required.

Related link: [Upgrading to an HA VPN server](/docs/vpc?topic=vpc-vpn-client-to-site-change-server-types)

#### Monitoring and logging
{: #reference-monitoring-logging-vpn-c2s}

VPN (client-to-site) gateways use a combination of IBM Log Analysis and {{site.data.keyword.cloud_notm}} Monitoring for log analysis and metrics monitoring.

##### Client-to-site log analysis
{: #cts-logging}

You can use IBM Log Analysis to view application and connection logs from your {{site.data.keyword.cloud_notm}} VPN (client-to-site) for VPC. IBM Log Analysis offers administrators, DevOps teams, and developers advanced features to filter, search, and tail log data, define alerts, and design custom views to monitor application and system logs.

For more information, refer to [Using IBM Log Analysis to view VPN logs](/docs/vpc?topic=vpc-using-log-analysis-to-view-vpn-logs&interface=ui).

##### Client-to-site metrics monitoring
{: #cts-metrics-monitoring}

{{site.data.keyword.cloud_notm}} Monitoring collects basic VPN metrics on {{site.data.keyword.cloud_notm}} for VPC, such as VPN gateway status, VPN gateway packets input/output, and VPN connection bytes input/output. These metrics are stored in {{site.data.keyword.cloud_notm}} Monitoring. You can access metrics through the prebuilt dashboard.

For more information, refer to [Monitoring VPN servers](/docs/vpc?topic=vpc-vpn-client-to-site-monitoring&interface=ui).

Related link: [VPN server events](/docs/vpc?topic=vpc-at_events#events-vpn-server)

### Satellite Connector
{: #reference-satellite-connector}

Provides additional information on the Satellite Connector offering.

Satellite Connector provides a lightweight solution for {{site.data.keyword.cloud_notm}} services to reach out to on-premises data sources. If bidirectional communication is needed, or Cloud services to be deployed on the client on-premises, refer to [Understanding Satellite location and hosts](/docs/satellite?topic=satellite-location-host).

#### Pricing
{: #reference-pricing-satellite}

To calculate pricing for {{site.data.keyword.cloud_notm}} offerings, use the [{{site.data.keyword.cloud_notm}} cost estimator](https://www.ibm.com/cloud/cloud-calculator){: external}.
{: tip}

* Low cost, [pay-as-you-go](https://www.ibm.com/cloud/pricing/pay-as-you-go){: external} pricing with a single flat rate charge without bandwidth caps.
* Flat rate per on-premises instance. Satellite locations and connections are priced at the same rate with no additional charges.
* The client is responsible for on-premises compute/storage/network components and internet connection back to the {{site.data.keyword.cloud_notm}} MZR.

#### Connectivity
{: #reference-connectivity-satellite}

* Establishes secure TLS 1.3 endpoint communications over the internet or Direct Link. The client always maintains control over whatever data is transferred.
* Communications originate outbound from within the client's network for simplified client networking.
* Unique DNS names for each instance enable tight firewall controls.
* The client configured unique endpoints for each data transfer at layer 7 of the stack, as opposed to linking L2/L3 networks similar to a VPN.

#### Latency and bandwidth
{: #reference-latency-bandwidth-satellite}

*  Fully dependent on the client's underlying internet or Direct Link transport, and is impacted by any bandwidth limitations or latency they might introduce.
* Connection is made to one of IBM's MZRs. Clients are encouraged to pick the MZR closet to them in terms of network performance.
* Maximum latency requirements exist between the on-premises hosts for a satellite location. The maximum host-to-host communication at the satellite location is _x_ ms.

#### Provisioning
{: #reference-provisioning-satellite}

* Ordered and configured through {{site.data.keyword.cloud_notm}} UI, CLI, or API.
* Satellite Locations support an on-premises service control plan that operates all local services, and establishes management connectivity with {{site.data.keyword.cloud_notm}}. This requires three hosts for the HA control plane, plus an additional host to support local management services.
* Satellite connectors support cloud endpoints that enable communication to the client premises. These require a client-supported docker host (x86), and can also be deployed in redundant and HA configurations.

For deployment options, including redundant and HA patterns, see the [Satellite Connector overview](/docs/satellite?topic=satellite-understand-connectors).
{: note}

Related links:
* [Connector overview](/docs/satellite?topic=satellite-understand-connectors)
* [FAQs](/docs/satellite?topic=satellite-faqs)
* [Limitations, default settings, usage requirements](/docs/satellite?topic=satellite-requirements)
* [Access management](/docs/satellite?topic=satellite-iam)

#### Security and data encryption
{: #reference-security-data-encryption-satellite}

* Uses TLS 1.3 encryption for all communications, with managed key rotation implemented through an IBM Site Recovery Engineer.
* The client always has control on communication and is able to individually disable and enable any set of endpoints on demand.
* Client can specify their own encryption for individual endpoints they create, if wanted.
* Fully supports IAM roles and responsibility assignment to control access and data exposure risk.

Related links:
* [Access management](/docs/satellite?topic=satellite-iam)
* [Architecture](/docs/satellite?topic=satellite-service-architecture)
* [Compliance](/docs/satellite?topic=satellite-compliance)
* [Service connection](/docs/satellite?topic=satellite-service-connection)
* [Data security](/docs/satellite?topic=satellite-data-security)

#### Resiliency
{: #reference-resiliency-satellite}

* Satellite Locations and Satellite Connectors both support High Availability (HA) deployments across multiple client availability zones.
* The client premise deployment is the responsibility of the client to deploy across hosts that are logically and physically independent of give the greatest failure resiliency.
* For resiliency the {{site.data.keyword.cloud_notm}} infrastructure is deployed across three independent zones, each zone is a separate data center with independent power, cooling, and networking for maximum reliability.

Related links:
* [Architecture](/docs/satellite?topic=satellite-service-architecture)
* [High availability](/docs/satellite?topic=satellite-ha)

#### Monitoring and logging
{: #reference-monitoring-logging-satellite}

IBM Satellite connectivity uses a combination of IBM Log Analysis and {{site.data.keyword.cloud_notm}} Monitoring for log analysis and metrics monitoring.

* All operations work through the client's {{site.data.keyword.cloud_notm}} account, and can be accomplished through the UI, CLI, or API.
* Solution management is provided by an {{site.data.keyword.cloud_notm}} Site Reliability Engineer. The client is responsible for their on-premises compute, network, and storage management.

##### Satellite log analysis
{: #satellite-logging}

You can use IBM Log Analysis to view application and connection logs for satellite connectivity. IBM Log Analysis offers administrators, DevOps teams, and developers advanced features to filter, search, and tail log data, define alerts, and design custom views to monitor application and system logs. For more information, refer to [Logging for Satellite](/docs/satellite?topic=satellite-health).

##### Satellite metrics monitoring
{: #satellite-metrics}

{{site.data.keyword.cloud_notm}} Satellite® comes with basic tools to help you manage the health of your Satellite resources, such as reviewing location and host health. Also, you can integrate Satellite and other {{site.data.keyword.cloud_notm}} resources with {{site.data.keyword.cloud_notm}} Monitoring to get a comprehensive view and tools to manage all your resources. 

Related links:
* [Monitoring for Satellite](/docs/satellite?topic=satellite-monitor)
* [Auditing, logging, and monitoring Satellite Link endpoints](/docs/satellite?topic=satellite-link-cloud-monitor)

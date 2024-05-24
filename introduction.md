---



copyright:
  years: 2023, 2024
lastupdated: "2024-02-04"

keywords: private connectivity options

subcollection: private-connectivity

---

{{site.data.keyword.attribute-definition-list}}

# IBM Cloud private connectivity offerings
{: #connect-privately-ibm-cloud}

Connecting to IBM Cloud with a private connection can be achieved with the following topologies:

* Direct Link Dedicated - Single tenant connection to IBM Cloud [Point of Presences](#x5458832){: term} (PoPs)
* Direct Link Connect - Multi-tenant service provider connection to IBM Cloud PoPs
* VPN (site-to-site) - VPN tunnel from on-premises firewall to IBM Cloud VPN
* VPN (client-to-site) - VPN tunnel from laptop to IBM Cloud VPN
* Satellite Connector - A layer-7, endpoint-oriented connection from IBM Cloud to access on-premises data source.

Private connectivity resources within IBM Cloud can be achieved with Transit Gateway (private backbone).
{: note}

![IBM Cloud Overview](/images/cloud-private-conn.svg "IBM Cloud Private Connectivity Overview"){: caption="Figure 1. IBM Cloud Private Connectivity Overview" caption-side="bottom"}

## Required skills for system administrators
{: #required-skills}

Creating network connectivity in IBM Cloud is a critical task for network administrators. It allows you to connect your on-premises networks to the cloud, as well as connect different resources within the cloud itself. However, creating network connectivity can be a complex task, and it requires a number of different skills.

Administrators who need to create network connectivity in IBM Cloud should have a strong understanding of the following topics:

* IP addressing and routing
* Cloud networking concepts
* IBM Cloud networking services

Administrators should also be familiar with the following tools and technologies:

* The IBM Cloud console
* The IBM Cloud CLI
* The IBM Cloud SDKs
* Network monitoring and debugging tools

## IBM Cloud offering descriptions and key differentiators
{: #offerings-key-points}

IBM Cloud offers the following private connectivity services.
{: shortdesc}

### Direct Link Dedicated
{: #dedicated}

The IBM Cloud Direct Link solution seamlessly connects your on-premises resources to your cloud resources, through a single-tenant, fiber-based, cross-connect terminated connection. This offering is also used by colocation facilities that are next to IBM Cloud PoPs and data centers.

* Private access to IBM Cloud using dedicated infrastructure.
* High cost for dedicated connectivity with increased bandwidth options.
* Single-tenant solution for maximum throughput.
* Optimal for large or frequent data transfers.

[Learn more](/docs/dl?topic=dl-get-started-with-ibm-cloud-dl#get-started-with-direct-link-dedicated)

### Direct Link Connect
{: #connect}

Direct Link Connect uses a service provider to quickly establish and deliver connectivity to IBM Cloud locations. These service providers are already connected to the IBM Cloud network, and use multi-tenant, high capacity links (also known as network-to-network interfaces, or NNI).

* Private access to IBM Cloud using shared infrastructure.
* Moderate cost, private and secure, shared infrastructure, and fast deployment.
* Ideal for multicloud environments with your server provider’s network.
* Virtual connectivity for rapid provisioning.

[Learn more](/docs/dl?topic=dl-get-started-with-ibm-cloud-dl#get-started-with-direct-link-connect)

### Transit Gateway
{: #private-tgw}

Use IBM Cloud Transit Gateway to interconnect IBM Cloud resources and Virtual Private Cloud (VPC) infrastructures worldwide, keeping traffic within the IBM Cloud network.

* Deliver your applications around the world, with global routing across the IBM Cloud network.
* Simplify your network and build applications — without managing a distributed network.
* Scale and share IBM Cloud services  like IBM classic infrastructure resources and IBM VPCs.
* Keep traffic within the IBM Cloud network without traversing the public internet.

[Learn more](/docs/transit-gateway?topic=transit-gateway-getting-started)

### VPN (site-to-site gateways)
{: #vpn-site-to-site}

You can use the IBM Cloud VPN for VPC service to securely connect your Virtual Private Cloud (VPC) to another private network. Use a static, route-based VPN, or a policy-based VPN to set up an IPsec site-to-site tunnel between your VPC and your on-premises private network or another VPC.

* Protocol suite that provides secure communication between devices.
* Low cost, [pay-as-you-go pricing](https://www.ibm.com/cloud/pricing/pay-as-you-go){: external}
* Configurable mechanism to detect availability of an IPsec peer.
* Internet Key Exchange (IKE) is a part of the IPsec protocol that is used to establish VPN connections.
* Perfect Forward Secrecy (PFS) ensures that DH-generated keys aren't used again during IPsec renegotiation.
* Supports a pre-shared key for Phase 1 peer authentication. Supported authentication algorithms for both phases include SHA-256, SHA-384, and SHA-512.

[Learn more](/docs/vpc?topic=vpc-using-vpn)

### VPN (client-to-site servers)
{: #vpn-client-to-site}

Client VPN for VPC provides client-to-site connectivity, which allows remote devices to securely connect to the VPC network using an OpenVPN software client. This solution is useful for telecommuters who want to connect to the IBM Cloud from a remote location, such as a home office, while still maintaining secure connectivity.

* Multi-factor client authentication.
* Provides added layers of security with integrated authentication methods.
* Low cost, [pay-as-you-go pricing](https://www.ibm.com/cloud/pricing/pay-as-you-go){: external}.
* Availability in all MZRs world wide.
* Supports both stand-alone (pilot) and high availability (production) deployments.
* High availability spanning across zones, providing better performance and resiliency.
* TLS 1.2/1.3-based secure/encrypted connectivity over the internet.

[Learn more](/docs/vpc?topic=vpc-using-vpn)

### Satellite Connector
{: #satellite}

Satellite Connector provides a lightweight solution for IBM Cloud services to reach out to on-premises data sources. If bidirectional communication is needed, or Cloud services to be deployed on the client on-premises, refer to a [Satellite Location](/docs/satellite?topic=satellite-location-host).

* Provides client-owned L7 endpoints for IBM Cloud services to access data on the client premise, rather than bridging on-premise networks with cloud like a VPN.
* Allows you to leverage your AWS, Azure, Google Cloud infrastructure, your on-premises hardware, or purchase from IBM/IBM partners.
* Uses internet or Direct Link for transport.
* Operated as-a-service by IBM.
* Use a single dashboard to centralize observability and management across all locations.
* Extend access policies, logging, monitoring and other controls to all locations.
* Low cost, [pay-as-you-go pricing](https://www.ibm.com/cloud/pricing/pay-as-you-go){: external} without bandwidth capacity limitations.

If bidirectional communication is needed or the ability to deploy IBM Cloud services on your on-premises or other cloud infrastructures are required, a Satellite Location provides additional capabilites. For more information, see [Understanding Satellite location and hosts](/docs/satellite?topic=satellite-location-host).

[Learn more](/docs/satellite)

## Offering comparisons
{: #comparison-table}

### Pricing
{: #pricing-comparison}

There are many factors to consider regarding pricing, such as peer configurations, dependent offerings, local providers, and so on. For example, a VPN site-to-site gateway or a VPN client-to-site server does not charge for an additional floating IP, and the pricing is also location based.

To calculate pricing for IBM Cloud offerings, use the [IBM Cloud cost estimator](https://www.ibm.com/cloud/cloud-calculator){: external}.
{: important}

| IBM Cloud service | High  \n cost | Medium  \n cost | Low  \n cost |
|---------------|-------------|-------------|-------------|
| Direct Link Dedicated  | ![Checkmark icon](../icons/checkmark-icon.svg) | |
| Direct Link Connect  |  | ![Checkmark icon](../icons/checkmark-icon.svg) |
| Transit Gateway   | | ![Checkmark icon](../icons/checkmark-icon.svg) |
| VPN (site-to-site) | | |  ![Checkmark icon](../icons/checkmark-icon.svg) |
| VPN (client-to-site) | | | ![Checkmark icon](../icons/checkmark-icon.svg) |
| Satellite Connector | | | ![Checkmark icon](../icons/checkmark-icon.svg) |
{: caption="Table 1: Pricing comparison" caption-side="bottom"}

### Connectivity
{: #connectivity-comparison}

* Direct Link Dedicated: Connect VPC networks directly with physical connections.
* Direct Link Connect: Connect VPC networks through intermediate partner networks.
* Transit Gateway: Connect resources deployed in your VPC virtual networks with an Availability Zone (AZ) and between AZs.
* VPN (site-to-site): Connect private networks with private connectivity over the internet.
* VPN (client-to-site): Host a VPC network with private connectivity over the internet.
* Satellite Connector: Connect with secure TLS 1.3 endpoint-oriented communications over the internet or Direct Link.

### Latency & bandwidth
{: #latency-bandwidth}

Direct Link offerings have the lowest latency followed by Satelite and VPN offerings. Latency is highly dependent on location.

Bandwidth:

* Direct Link Dedicated: Speeds up to 10 Gbps.
* Direct Link Connect: Speeds up to 5 Gbps.
* Transit Gateway: Speeds up to or in excess of 10 Gbps.
* VPN (site-to-site): Standalone mode up to 600 Mbps; High availability up to 1200 Mbps.
* VPN (client-to-site): Speeds up to 650 Mbps.
* Satellite Connector: Limited by client connectiviy; maximum speed less than 1000 Mbps.

### Provisioning time
{: #provisioning-time}

Provisioning time includes completing names and configuration parameters, as well as other dependencies and prerequisites.

* Direct Link Dedicated: 5-30 days
* Direct Link Connect: 3-5 days, depending on your provider (Provisioning on the IBM side is the same day.)
* Transit Gateway: 20-55 minutes
* VPN (site-to-site gateways): 20 minutes to one hour
* VPN (client-to-site servers): 20 minutes to one hour
* Satellite Connector: 10 minutes

### Security and data encryption
{: #security-data-encryption-comparison}

All solutions listed are private and secure. For more information, see the "Security and data encryptions" in the Reference section for each service.

### Resiliency
{: #resiliency-comparison}

Solutions are diverse. To establish true redundancy, you must implement multiple connections to ensure your solution meets your resiliency needs.

### Monitoring and logging
{: #monitoring-logging-comparison}

Private connectivity options use a variety of tools for monitoring and logging.

| IBM Cloud service | Monitoring | Logging |
|---------------|-------------|-------------|
| Direct Link Dedicated | [Route reports](/docs/dl?topic=dl-generate-route-reports&interface=ui) | [Activity Tracker](/docs/dl?topic=dl-at_events&interface=ui) |
| Direct Link Connect | [Route reports](/docs/dl?topic=dl-generate-route-reports&interface=ui) | [Activity Tracker](/docs/dl?topic=dl-at_events&interface=ui) |
| Transit Gateway   | [IBM Cloud Monitoring](/docs/vpc?topic=vpc-vpn-monitoring-metrics&interface=ui) | [Activity Tracker](/docs/transit-gateway?topic=transit-gateway-at_events&interface=ui) |
| VPN (site-to-site) | [IBM Cloud Monitoring](/docs/vpc?topic=vpc-vpn-client-to-site-monitoring&interface=ui) | [IBM Log Analysis](/docs/vpc?topic=vpc-using-log-analysis-to-view-vpn-logs&interface=ui) |
| VPN (client-to-site) | [IBM Cloud Monitoring](/docs/vpc?topic=vpc-vpn-client-to-site-monitoring&interface=ui) | [IBM Log Analysis](/docs/vpc?topic=vpc-client-vpn-log-analysis-c2s&interface=ui) |
| Satellite Connector | [IBM Cloud Monitoring](/docs/satellite?topic=satellite-monitor) | [Activity Tracker](/docs/satellite?topic=satellite-at_events)  \n  \n [IBM Log Analysis](/docs/satellite?topic=satellite-health) |
{: caption="Table 1: Monitoring and logging comparison" caption-side="bottom"}

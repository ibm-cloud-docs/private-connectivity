---



copyright:
  years: 2023, 2024
lastupdated: "2024-02-04"

keywords: private connectivity options

subcollection: private-connectivity

---

{{site.data.keyword.attribute-definition-list}}

# Site-to-site VPN
{: #reference-site-to-site-vpn}

This topic provides additional information on the VPN for VPC offering.
{: shortdesc}

## Pricing
{: #reference-pricing-vpn-s2s}

To calculate pricing for IBM Cloud offerings, use the [IBM Cloud cost estimator](https://www.ibm.com/cloud/cloud-calculator){: external}.
{: tip}

* Low cost, [pay-as-you-go](https://www.ibm.com/cloud/pricing/pay-as-you-go){: external} pricing
* Costs are typically associated with the type of VPN gateway, usage hours, connection hours, and public IP addresses, volume of data egress from VPC through the gateway, and so on.

## Connectivity
{: #reference-connectivity-vpn-s2s}

* Connect private networks with private connectivity over the internet.
* The cloud provider's internet service provider (ISP) provides connection to the internet.
* The connection is shared with internet users, is private and encrypted, and uses a secure tunnel.

## Latency and bandwidth
{: #reference-latency-bandwidth-vpn-s2s}

* Susceptible to the inherent variability in internet connectivity, latency, and bandwidth fluctuations.
* Connection path might not be the shortest and might also traverse multiple hops, resulting in higher latencies.
* Latency can be minimized if the data center location where the VPN host and server are provisioned are geographically close (in the same region).
* Maximum limits usually apply to throughput capacity, depending on the cloud provider's VPN offering.
* The IBM Cloud offerings provide two options - Standalone (up to 600 Mbps) and HA (up to 1200 Mbps).

## Provisioning
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

## Security and data encryption
{: #reference-security-data-encryption-vpn-s2s}

* Uses IPsec secure encrypted tunnel between networks exchanging workload data; uses Internet Key Exchange (IKE) encryption, and Pre-Shared Key (PSK) authentication.
* Appropriate access controls and network ports must be configured on the VPC networks for applications to communicate with each other. [Learn more](/docs/vpc?topic=vpc-mng-data&interface=ui#data-storage) (Search for `VPN` in this link.)

## Resiliency
{: #reference-resiliency-vpn-s2s}

* Depends on the VPN cloud offering. Typically, two VPN gateways are provisioned in the same availability zones and provide appliance-level redundancy/HA.
* Appropriate selection of locations can help in planning for HA/DR.
* IBM Cloud VPN gateway consists of two back-end instances in the same zone for high availability. Recommended to provision a gateway in each availability zone for zone fault tolerance.

Related link: [VPN gateway high availability](/docs/vpc?topic=vpc-vpn-ha&interface=ui)

## Monitoring and logging
{: #reference-monitoring-logging-vpn-s2s}

VPN (site-to-site) gateways use a combination of IBM Log Analysis and IBM Cloud Monitoring for log analysis and metrics monitoring.

### Site-to-site log analysis
{: #s2s-logging}

You can use IBM Log Analysis to view application and connection logs from your IBM Cloud VPN (site-to-site) for VPC. IBM Log Analysis offers administrators, DevOps teams, and developers advanced features to filter, search, and tail log data, define alerts, and design custom views to monitor application and system logs.

For more information, refer to [Using IBM Log Analysis to view VPN logs](/docs/vpc?topic=vpc-using-log-analysis-to-view-vpn-logs&interface=ui).

### Site-to-site metrics monitoring
{: #s2s-metrics}

IBM Cloud Monitoring collects basic VPN metrics on IBM Cloud for VPC, such as VPN gateway status, VPN gateway packets input/output, and VPN connection bytes input/output. These metrics are stored in IBM Cloud Monitoring. You can access metrics through the prebuilt dashboard.

For more information, refer to [Monitoring VPN gateway for VPC metrics](/docs/vpc?topic=vpc-vpn-monitoring-metrics&interface=ui).

Related link: [VPN gateway events](/docs/vpc?topic=vpc-at_events#events-vpns)

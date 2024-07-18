---



copyright:
  years: 2023, 2024
lastupdated: "2024-02-04"

keywords: private connectivity options

subcollection: private-connectivity

---

{{site.data.keyword.attribute-definition-list}}

# Client-to-site VPN
{: #reference-client-to-site-vpn}

This topic provides additional information on the Client VPN for VPC offering.
{: shortdesc}

## Pricing
{: #reference-pricing-vpn-c2s}

To calculate pricing for IBM Cloud offerings, use the [IBM Cloud cost estimator](https://www.ibm.com/cloud/cloud-calculator){: external}.
{: tip}

* Low cost, [pay-as-you-go](https://www.ibm.com/cloud/pricing/pay-as-you-go){: external} pricing
* Costs are typically associated with the type of VPN server, usage hours, aggregated connection hours, and public IP addresses, volume of data egress from the VPC, and so on.

## Connectivity
{: #reference-connectivity-vpn-c2s}

* It connects a client host to a VPC network with private connectivity over the internet.
* The cloud provider's internet service provider (ISP) provides connection to the internet.
* The connection is shared with internet users, is private and encrypted, and uses a secure tunnel.

## Latency and bandwidth
{: #reference-latency-bandwidth-vpn-c2s}

* Susceptible to the inherent variability in internet connectivity, latency, and bandwidth fluctuations.
* Connection path may not be the shortest and may traverse multiple hops, resulting in higher latencies.
* Latency can be minimized if the data center location where the VPN gateways are provisioned are geographically close (in the same region).
* Maximum limits usually apply to throughput capacity, depending on the cloud provider's VPN offering.
* This IBM Cloud offering provides speeds up to 650 Mbps.

## Provisioning
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

## Security and data encryption
{: #reference-security-data-encryption-vpn-c2s}

* Uses TLS 1.2/1.3 encryption
* Multi-factor authentication can be applied to VPN server and client connections to provide an added layer of security to meet compliance and security requirements.

Related link: [Securing your environment with VPN server](/docs/vpc?topic=vpc-client-to-site-vpn-securing-environment)

## Resiliency
{: #reference-resiliency-vpn-c2s}

* Depends on the VPN cloud offering. Typically, two VPN servers are provisioned in different availability zones and provide appliance-level redundancy/HA.
* Appropriate selection of locations can help in planning for HA/DR. IBM Cloud offering provides two modes:
   * High-availability mode: Deploys the VPN server across two subnets in different zones. Best for multi-zone deployments and solutions where client VPN access is critical.
   * Stand-alone mode: Deploys the VPN server in a single subnet and zone. Best for non-production use where multi-zone resiliency is not required.

Related link: [Upgrading to an HA VPN server](/docs/vpc?topic=vpc-vpn-client-to-site-change-server-types)

## Monitoring and logging
{: #reference-monitoring-logging-vpn-c2s}

VPN (client-to-site) gateways use a combination of IBM Log Analysis and IBM Cloud Monitoring for log analysis and metrics monitoring.

### Client-to-site log analysis
{: #cts-logging}

You can use IBM Log Analysis to view application and connection logs from your IBM Cloud VPN (client-to-site) for VPC. IBM Log Analysis offers administrators, DevOps teams, and developers advanced features to filter, search, and tail log data, define alerts, and design custom views to monitor application and system logs.

For more information, refer to [Using IBM Log Analysis to view VPN logs](/docs/vpc?topic=vpc-using-log-analysis-to-view-vpn-logs&interface=ui).

### Client-to-site metrics monitoring
{: #cts-metrics-monitoring}

IBM Cloud Monitoring collects basic VPN metrics on IBM Cloud for VPC, such as VPN gateway status, VPN gateway packets input/output, and VPN connection bytes input/output. These metrics are stored in IBM Cloud Monitoring. You can access metrics through the prebuilt dashboard.

For more information, refer to [Monitoring VPN servers](/docs/vpc?topic=vpc-vpn-client-to-site-monitoring&interface=ui).

Related link: [VPN server events](/docs/vpc?topic=vpc-at_events#events-vpn-server)

---



copyright:
  years: 2023, 2024
lastupdated: "2024-02-04"

keywords: private connectivity options

subcollection: private-connectivity

---

{{site.data.keyword.attribute-definition-list}}

# Site-to-site VPN provisioning walk-through
{: #provisioning-scenario-vpn-s2s}

You can use the IBM Cloud VPN for VPC service to securely connect your Virtual Private Cloud (VPC) to another private network. Use a static, route-based VPN, or a policy-based VPN to set up an IPsec site-to-site tunnel between your VPC and your on-premises private network or another VPC.
{: shortdesc}

The provisioning process takes approximately 20 minutes to one hour to complete. The provisioning process is as follows:

1. [10 mins]{: tag-blue} - Review [planning considerations for VPN gateways](/docs/vpc?topic=vpc-planning-considerations-vpn&interface=ui) and plan for local/remote CIDRs. Also, review [VPN gateway limitations](/docs/vpc?topic=vpc-vpn-limitations) and [configuration information](/docs/vpc?topic=vpc-using-vpn&interface=ui), such as IKE policies, mode, and so on.
1. [10 mins]{: tag-blue} - Create a VPN gateway using the [IBM Cloud console](/docs/vpc?topic=vpc-creating-a-vpc-using-the-ibm-cloud-console) or with the [CLI and API](/docs/vpc?topic=vpc-creating-vpc-resources-with-cli-and-api&interface=cli). Review [ACLs and security groups](/docs/vpc?topic=vpc-acls-security-groups-vpn).
1. [5-10 mins, depending on the gateway type]{: tag-blue} - Make sure that your peer device supports NAT traversal and that it is enabled on the peer device.
1. [5 mins]{: tag-blue} - [Create a VPN gateway](/docs/vpc?topic=vpc-vpn-create-gateway).
1. [5 mins]{: tag-blue} - [Create VPN connections](/docs/vpc?topic=vpc-vpn-adding-connections).
1. [5 mins]{: tag-blue} - For static, route-based VPNs, select or [create a routing table for static routing](/docs/vpc?topic=vpc-create-vpc-routing-table), then [create routes](/docs/vpc?topic=vpc-create-vpc-route) by using the **VPN connection** type.
1. [10-20 mins, depending on the gateway type]{: tag-blue} - [Connect to an on-premises network through a VPN tunnel](/docs/vpc?topic=vpc-vpn-onprem-example).
1. [5 mins]{: tag-blue} - Verify that your VPN connection is available by sending ping or data traffic across the tunnel to devices that are on the peer network.

---



copyright:
  years: 2023, 2024
lastupdated: "2024-02-01"

keywords: private connectivity options

subcollection: private-connectivity

---

{{site.data.keyword.attribute-definition-list}}

# Site-to-site VPN deployment considerations
{: #s2s-vpn-deployment-considerations}

Here are some deployment considerations to review when choosing VPN for VPC.
{: shortdesc}

|   |   |
|:----|:--------|
|Which IBM Cloud region do you plan to deploy the VPCs? The regions could be closest to your on-premises site.| |
|What subnets in the VPC need to be connected through the VPN? Make sure that there's enough space in the subnet for the gateway.| |
|Is there a requirement to separate connectivity between your VPN and your resources, such as the virtual server instances into VPCs?| |
|How are your virtual server instances distributed in the VPC? VPN gateway is created in the zone associated with the subnet that you select and can be used to connect to virtual servers in the same zone. For zone fault tolerance, you can deploy one VPN gateway per zone.| |
|Do you need your on-premises network to access service endpoints through your site-to-site connectivity option?  \n Do you have resources in IBM Cloud on Classic that you need to access through VPN or another connectivity option?|  |
|Do you have a peer VPN gateway or router (or multiple gateways/routers) set up on-premises? If yes, what is the type or model of that gateway? If your peer gateway enforces Perfect Forward Secrecy (PFS), you’ll need to set custom policies.|  |
|What will be the CIDRs on-premises? Note that local (VPC) and peer (on-premises) subnets of a VPN gateway connection should not overlap or conflict.  /\n The local (VPC) subnet is specified when you create the VPN Gateway. For more information, see working with [Working with subnets in VPC](/docs/vpc?topic=vpc-subnets-configure).| |
|Is your VPN gateway on-premises behind a firewall doing Network Address Translation (NAT)?|  |
|Do you need the VPC resources to access the internet through VPN? Do you want any IP range to be blocked? |  |
{: caption="Part 1: Site-to-site VPN deployment considerations" caption-side="bottom"}

## Performance and other things
{: #performance-c2s-vpn}

|   |   |
|:----|:--------|
|What is the desired throughput of the site-to-site connectivity option (i.e., Direct Link or VPN)? Is there a peak hour, month, or season?  \n Site-to-site VPN supports up to [650 Mbps of throughput](/docs/vpc?topic=vpc-faqs-vpn). Direct Link supports much higher bandwidth up to 5 Gbps or 10 Gbps depending on your configurations. | |
|What is your expected cost for the connectivity option?  \n Site-to-site VPN uses a usage-based pricing that can be estimated using the [Cost Estimator](https://www.ibm.com/cloud/cloud-calculator){: external}. Direct Link has multiple pricing plans, varies by provider, and has higher cost. See [Direct Link Dedicated] (/docs/private-connectivity?topic=private-connectivity-reference-direct-link-dedicated) and [Direct Link Connect](/docs/private-connectivity?topic=private-connectivity-reference-direct-link-connect) for more information.
| |
{: caption="Part 2. Performance and other things" caption-side="bottom"}

---



copyright:
  years: 2023, 2024
lastupdated: "2024-02-04"

keywords: private connectivity options

subcollection: private-connectivity

---

{{site.data.keyword.attribute-definition-list}}

# Site-to-site VPN use cases
{: #use-cases-vpn-s2s}

Primary use cases include administrative remote access to various hosts across the cloud. Other use cases include low to moderate volume transactional or batch data exchange across business-critical application workloads tolerant to higher latency applications.

* Direct administrative access to hosts on the cloud is accomplished with jump servers, SSH, remote desktop protocol, and so on.
* Application data exchange is accomplished through RESTful APIs or TCP host/ports for synchronous/real-time calls between systems and components.
* Data transfer is accomplished using SFTP or simple data migration applications.

## Site-to-Site VPN for secure connectivity using a policy-based VPN
{: #use-case-vpn-1}

Traffic that matches negotiated CIDR ranges passes through a policy-based VPN. You can use policy-based VPN gateways and ingress routing to forward POWER incoming traffic from transit gateways to your on-premises network. VPC 1 adds an on-premises CIDR as the VPC address prefix to allow route propagation.

![Site-to-site VPN use case](/images/VPN-s2s-usecase.png "Site-to-site VPN use case"){: caption="Figure 1. Site-to-site VPN use case" caption-side="bottom"}

Related link: [VPN for VPC use cases](/docs/vpc?topic=vpc-using-vpn#vpn-use-cases)

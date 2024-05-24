---



copyright:
  years: 2023, 2024
lastupdated: "2024-02-04"

keywords: private connectivity options

subcollection: private-connectivity

---

{{site.data.keyword.attribute-definition-list}}

# Client-to-site VPN use cases
{: #use-cases-vpn-c2s}

Primary use cases include ad-hoc or on-demand connectivity for low volume administrative remote access from a client host to hosts on a VPC network. Other use cases include ad-hoc or on-demand low volume batch data transfers from a client host to hosts on a VPC network. These connections are tolerant to higher latency.

* Direct administrative access to hosts on the cloud is accomplished using jump servers, SSH, remote desktop protocol, and so on.
* Data transfer is accomplished using SFTP or simple data migration applications.

## Client-to-site VPN for secure connectivity
{: #use-case-c2s-1}

With Client VPN for VPC (client-to-site VPN) you can securely connect from remote devices to the IBM Cloud network using an OpenVPN client.

To access the resources in `VPC1`, in your routing table set **Accept routes from** to **VPN server** to allow route propagation by the VPN server.

To access resources in the `POWER VM`, in your routing table, create a VPN server route with the POWER network as the destination using the **Translate** action. This translates the source IP to the VPN server's private IP, making your VPN client IP invisible to the destination in the POWER network.

![Client-to-site VPN use case](/images/vpn-client-to-site.png "Client-to-site VPN use case"){: caption="Figure 1. Client-to-site VPN use case" caption-side="bottom"}

Related link: [VPN server use cases](/docs/vpc?topic=vpc-vpn-client-to-site-overview#vpn-client-to-site-use-cases)

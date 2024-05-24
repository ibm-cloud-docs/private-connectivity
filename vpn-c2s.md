---



copyright:
  years: 2023, 2024
lastupdated: "2024-02-04"

keywords: private connectivity options

subcollection: private-connectivity

---

{{site.data.keyword.attribute-definition-list}}

# Client-to-site VPN provisioning walk-through
{: #provisioning-scenario-vpn-c2s}

Client VPN for VPC provides client-to-site connectivity, which allows remote devices to securely connect to the VPC network using an OpenVPN software client. This solution is useful for telecommuters who want to connect to the IBM Cloud from a remote location, such as a home office, while still maintaining secure connectivity.
{: shortdesc}

The provisioning process takes approximately 20 minutes to one hour to complete. The provisioning process is as follows:

1. [10 mins]{: tag-blue} - Review [planning considerations for VPN servers](/docs/vpc?topic=vpc-client-to-site-vpn-planning) and decide which VPN client authentication that you want to use: certificate-based, user ID and passcode, or both. For more information, see [Setting up client-to-site authentication](/docs/vpc?topic=vpc-client-to-site-authentication).
1. [10 mins]{: tag-blue} - For user ID and passcode authentication only, [create an IAM access group and grant users the role to connect to the VPN server](/docs/vpc?topic=vpc-create-iam-access-group).
1. [15 mins]{: tag-blue} - [Create a Secrets Manager instance and import certificates](/docs/vpc?topic=vpc-client-to-site-authentication#creating-cert-manager-instance-import).
1. [10 mins]{: tag-blue} - [Create a VPC](/docs/vpc?topic=vpc-creating-a-vpc-using-the-ibm-cloud-console#creating-a-vpc-and-subnet). Optionally, [configure security groups and ACLs for use with VPN](/docs/vpc?topic=vpc-vpn-client-to-site-security-groups).

   **Notes:**

   * For a high available VPN server, create a VPC and two subnets in two different zones.
   * For a stand-alone VPN server, create a VPC and one subnet in one zone.
   * Ensure your security groups and ACLs allow VPN traffic.
   * When creating a new VPC, the default security group attached only allows ICMP and SSH communications. Ensure that you add an inbound rule for client-to-site VPN traffic in this security group.
1. [5 mins]{: tag-blue} - For server authentication only, [create IAM service-to-service authorization](/docs/vpc?topic=vpc-client-to-site-authentication#creating-iam-service-to-service).
1. [5 mins]{: tag-blue} - [Create a VPN server](/docs/vpc?topic=vpc-vpn-create-server) and validate status.
1. [5 mins]{: tag-blue} - [Create VPN routes](/docs/vpc?topic=vpc-vpn-client-to-site-routes).
1. [10 mins]{: tag-blue} - [Set up a VPN client environment and connect to the VPN server](/docs/vpc?topic=vpc-vpn-client-environment-setup).

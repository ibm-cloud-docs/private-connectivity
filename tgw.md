---



copyright:
  years: 2023, 2024
lastupdated: "2024-02-04"

keywords: private connectivity options

subcollection: private-connectivity

---

{{site.data.keyword.attribute-definition-list}}

# Transit Gateway provisioning walk-through
{: #provisioning-scenario-tgw}

Use IBM Cloud Transit Gateway to interconnect IBM Cloud resources and Virtual Private Cloud (VPC) infrastructures worldwide, keeping traffic within the IBM Cloud network.

The provisioning process takes approximately 20-55 minutes to complete. The provisioning process is as follows:
1. [5-10 mins]{: tag-blue} - Review [Planning for IBM Cloud Transit Gateway](/docs/transit-gateway?topic=transit-gateway-helpful-tips) and plan the networks to be connected.
1. [5-20 mins]{: tag-blue} - [Create a transit gateway](/docs/transit-gateway?topic=transit-gateway-ordering-transit-gateway&interface=ui).
1. [5-20 mins]{: tag-blue} - [Add desired network connections](/docs/transit-gateway?topic=transit-gateway-adding-connections&interface=ui) to the transit gateway. These can be added while the gateway is still provisioning.
1. [5 mins]{: tag-blue} - Verify that you can ping between networks via the transit gateway.

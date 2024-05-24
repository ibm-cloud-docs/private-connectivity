---



copyright:
  years: 2023, 2024
lastupdated: "2024-02-04"

keywords: private connectivity options

subcollection: private-connectivity

---

{{site.data.keyword.attribute-definition-list}}

# Direct Link Connect deployment considerations
{: #direct-link-connect-deployment-considerations}

Here are some deployment considerations to review when choosing Direct Link Connect.
{: shortdesc}

|   |   |
|:----|:--------|
| Set up a second, diverse direct link to prevent outages? [Learn more](/docs/dl?topic=dl-models-for-diversity-and-redundancy-in-direct-link) |  |
| Contact your service provider to determine the location to IBM Cloud by verifying your colocation or provider's capabilities to reach the Meet Me Room (MMR) and cross-connect into IBM Cloud. Also, make sure that you understand your provider's deployment process.|  |
| Review Direct Link Connect [prerequisites](/docs/dl?topic=dl-ibm-cloud-dl-prerequisites). | |
| Consider whether you want a metered or unmetered pricing plan. Metered has a lower port fee and charges a per GB usage fee for egress traffic across the direct link. Unmetered billing has a higher port fee and no usage charges, which is ideal for customers who have higher egress traffic across their direct link. | |
| Review Direct Link Connect [planning considerations](/docs/dl?topic=dl-how-to-order-ibm-cloud-dl-connect&interface=ui#before-you-begin-connect) and [planning for virtual connections](/docs/dl?topic=dl-dl-planning-considerations#dl-planning-virtual-connections). |
| Review Direct Link Connect [known limitations](/docs/dl?topic=dl-known-limitations). |   |
| Decide whether you want to activate optional BGP settings. See the following links for details. \n * [MD5 authentication](/docs/dl?topic=dl-enable-disable-md5&interface=ui)  \n * [Bidirectional Forwarding Detection (BFD)](/docs/dl?topic=dl-activate-deactivate-bfd&interface=ui)  \n * [Prepending an AS path to influence route priority](/docs/dl?topic=dl-prepend-as-paths&interface=ui)  \n * [Route filtering](/docs/dl?topic=dl-filter-routes) | |
| Decide what type of network connection that you want to bind to your direct link. For example, you can create a direct, private connection between your on-premises network and IBM Cloud, or bind your direct link to transit gateways. Your on-premises network can then access IBM Cloud resources connected through the transit gateways. [Learn more](/docs/transit-gateway?topic=transit-gateway-about)  | |
{: caption="Part 1: Direct Link Connect deployment considerations" caption-side="bottom"}

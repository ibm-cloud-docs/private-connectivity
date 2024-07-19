---



copyright:
  years: 2023, 2024
lastupdated: "2024-02-04"

keywords: private connectivity options

subcollection: private-connectivity

---

{{site.data.keyword.attribute-definition-list}}

Here are some deployment considerations to review when choosing Transit Gateway.
{: shortdesc}

# Transit Gateway deployment considerations
{: #tgw-deployment-considerations}

| Deployment consideration | Action |
|:----|:--------|
| Have you decided which Transit Gateway location to use? | |
| Do you want to use local or global routing? Your choice is dependent on where the networks to be connected are located. [Learn more](/docs/transit-gateway?topic=transit-gateway-helpful-tips&interface=ui#routing-considerations)  | |
| Have you addressed any overlapping routes in the connected networks? Overlapping routes are a common issue when configuring a transit gateway. If the routes from two or more connections overlap, traffic might not be routed as intended. [Learn more](/docs/transit-gateway?topic=transit-gateway-route-reports&interface=ui#route-conflicts)| |
| Are there routes that you don't want advertised over the transit gateway? Do you need to create [prefix filters](/docs/transit-gateway?topic=transit-gateway-adding-prefix-filters)? | |
| Have you considered what connection type you plan to use? | |
| For a GRE tunnel or unbound GRE tunnel, have you configured redundant tunnels for high availability? There's no out-of-the-box redundancy with either GRE connection type. You must configure two GREs in different zones advertising the same routes to get redundancy. [Learn more](/docs/transit-gateway?topic=transit-gateway-helpful-tips&interface=ui#gre-considerations) |
{: caption="Part 1: Direct Link Dedicated deployment considerations" caption-side="bottom"}

Related link: [Planning for IBM Cloud Transit Gateway](/docs/transit-gateway?topic=transit-gateway-helpful-tips)

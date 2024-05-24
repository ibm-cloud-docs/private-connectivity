---



copyright:
  years: 2023, 2024
lastupdated: "2024-02-01"

keywords: private connectivity options

subcollection: private-connectivity

---

{{site.data.keyword.attribute-definition-list}}

# Client-to-site VPN deployment considerations
{: #c2s-vpn-deployment-considerations}

Here are some deployment considerations to review when choosing Client VPN for VPC.
{: shortdesc}

|   |   |
|:----|:--------|
|Do you need your individual users to have private and secure access (client-to-site servers) to your VPC resources from anywhere (for example, the airport, a hotel, or from home)? If yes, where are these users located?|  |
|Do you need your individual users to access service endpoints through your client-to-site VPN? These endpoints securely connect to IBM Cloud services over the IBM Cloud private network.|  |
|Client-to-site VPN is integrated with Secrets Manager for server authentication. Are you familiar with Secrets Manager and do you have an existing public/imported/private certificate with your Secrets Manager instance?|  |
|Client-to-site VPN supports three types of client authentication: a client certificate, added security with a user ID and passcode, or both. Which will be your preferred way of authenticating your users?| Client certificate / User ID/passcode / Both |
|Do you use client-to-site VPN for critical workload that require a multi-zone deployment, or a pilot where multi-zone deployment is not a must?| |
|Do you need the VPN server to do SNAT making your VPN client IP invisible to the destination devices?|  |
{: caption="Part 1. Client-to-site VPN deployment considerations" caption-side="bottom"}

## Performance and other things
{: #performance-c2s}

|   |   |
|:----|:--------|
|If you need individual access to VPC (client-to-site connectivity) from remote, how many users can be connecting to VPC concurrently through VPN?|  |
|What is your expected cost for the connectivity option?  \n  \n Client-to-site VPN uses usage-based pricing that can be estimated using the [Cost Estimator](https://www.ibm.com/cloud/cloud-calculator){: external}.  \n  \n Direct Link has multiple pricing plans, varies by provider, and has higher cost. See [Direct Link Dedicated](/docs/private-connectivity?topic=private-connectivity-reference-direct-link-dedicated) and [Direct Link Connect](/docs/private-connectivity?topic=private-connectivity-reference-direct-link-connect) for more information.|  |
{: caption="Part 2. Performance and other things" caption-side="bottom"}

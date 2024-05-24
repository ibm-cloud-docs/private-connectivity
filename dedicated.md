---



copyright:
  years: 2023, 2024
lastupdated: "2024-02-04"

keywords: private connectivity options

subcollection: private-connectivity

---

{{site.data.keyword.attribute-definition-list}}

# Direct Link Dedicated provisioning walk-through
{: #provisioning-scenario-dedicated}

Direct Link Dedicated requires that you install an edge router (CER) to physically connect to the IBM cross-connect router (XCR) in the meet me room (MMR) at the IBM Cloud location. The setup is initiated by requesting an LOA/CFA from IBM to proceed.
{: shortdesc}

You are issued a letter of authorization (LOA) that allows you and your service provider to work with the IBM Cloud site manager to install the CER. The site manager then provides a completion notice indicating that the install happened. This completion notice is approved by the IBM Implementation team for accuracy. After which, the team will ensure IBM side Layer-1 connectivity.

After there is compete Layer-1 connectivity (customer and IBM side), and the direct link is configured on the XCR and cross-connect switch (XCS), the provisioning process is complete. The direct link is now able to establish the boarder gateway protocol (BGP) session between the CER and XCR.

You must have your Direct Link planned and built out before ordering a dedicated direct link to prevent delays. The Dedicated Direct Link physical demarcation is a Patch Panel Port. It is up to the client to build to the Patch Panel Port. If this is the first Direct Link order or is a new order into a new region, please allow yourself plenty of time. Depending on where your network's Points Of Presence (PoPs) are, it can take 20 to 40 days to build out to an IBM site.
{: important}

When all prerequisites are met, the Direct Link Dedicated provisioning process takes approximately 4 weeks to complete. The provisioning process is as follows:

1. [1 day]{: tag-blue} - Read planning considerations and order a Dedicated direct link. For instructions, see [Ordering IBM Cloud Direct Link Dedicated](/docs/dl?topic=dl-how-to-order-ibm-cloud-dl-dedicated).
1. [1 day]{: tag-blue} - You receive a letter of authorization (LOA), which allows your service provider to order and set up the cross-connect for your direct link. You are notified when the LOA becomes available for review on the IBM Cloud console.
1. [Depends on customer]{: tag-blue} - Review the LOA with your service provider for accuracy and accept it. If anything is incorrect, discuss your concern with the IBM implementation team directly through this case.

   If the LOA is incorrect, or you have any questions, open a case with IBM Support case, upload your concerns or questions to the case.
   {: note}

1. [Depends on site provider]{: tag-blue} - Give the approved LOA to your service provider. Work with your service provider to set up the cross-connect within your chosen IBM Cloud location.
1. [Depends on customer]{: tag-blue} - Upload the completion notice received from your service provider on the IBM Cloud console. Ensure that your physical connection is patched down between the device and patch panel. Also, check to make sure you're sending light to IBM. For more information, see [How do I troubleshoot a Direct Link Dedicated connection during activation?](/docs/dl?topic=dl-troubleshoot-level-1) and this [completion notice example](/docs/dl?topic=dl-completion-notice-example).
1. [1-2 days]{: tag-blue} - The IBM Implementation team reviews the completion notice to ensure that it aligns with the LOA. If the completion notice is rejected, you are notified through an existing case or via the Direct Link console.
1. [1-4 days]{: tag-blue} - The IBM implementation team checks Layer-1 connectivity between the cross-connect router (XCR) and the Edge router and begins the patch cable installation process to established Layer-1 connectivity.
1. [1-4 days]{: tag-blue} - After the cross-connect completion notice is accepted, the patch cable installation between the IBM Cloud device to the patch panel begins.

   Some DC sites cannot work on the patch cable installation process until they receive management approval.
   {: note}

After connectivity is established successfully, your gateway moves to `Provisioned` status. Then, this case is closed. For further assistance with your direct link, contact [IBM Support](/unifiedsupport/supportcenter){: external}.

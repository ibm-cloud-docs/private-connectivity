---



copyright:
  years: 2023, 2024
lastupdated: "2024-02-04"

keywords: private connectivity options

subcollection: private-connectivity

---

{{site.data.keyword.attribute-definition-list}}

# Satellite Connector
{: #reference-satellite-connector}

Provides additional information on the Satellite Connector offering.
{: shortdesc}

Satellite Connector provides a lightweight solution for IBM Cloud services to reach out to on-premises data sources. If bidirectional communication is needed, or Cloud services to be deployed on the client on-premises, refer to [Understanding Satellite location and hosts](/docs/satellite?topic=satellite-location-host).

## Pricing
{: #reference-pricing-satellite}

To calculate pricing for IBM Cloud offerings, use the [IBM Cloud cost estimator](https://www.ibm.com/cloud/cloud-calculator){: external}.
{: tip}

* Low cost, [pay-as-you-go](https://www.ibm.com/cloud/pricing/pay-as-you-go){: external} pricing with a single flat rate charge without bandwidth caps.
* Flat rate per on-premises instance. Satellite locations and connections are priced at the same rate with no additional charges.
* The client is responsible for on-premises compute/storage/network components and internet connection back to the IBM Cloud MZR.

## Connectivity
{: #reference-connectivity-satellite}

* Establishes secure TLS 1.3 endpoint communications over the internet or Direct Link. The client always maintains control over whatever data is transferred.
* Communications originate outbound from within the client's network for simplified client networking.
* Unique DNS names for each instance enable tight firewall controls.
* The client configured unique endpoints for each data transfer at layer 7 of the stack, as opposed to linking L2/L3 networks similar to a VPN.

## Latency and bandwidth
{: #reference-latency-bandwidth-satellite}

*  Fully dependent on the client's underlying internet or Direct Link transport, and is impacted by any bandwidth limitations or latency they might introduce.
* Connection is made to one of IBM's MZRs. Clients are encouraged to pick the MZR closet to them in terms of network performance.
* Maximum latency requirements exist between the on-premises hosts for a satellite location. The maximum host-to-host communication at the satellite location is _x_ ms.

## Provisioning
{: #reference-provisioning-satellite}

* Ordered and configured through IBM Cloud UI, CLI, or API.
* Satellite Locations support an on-premises service control plan that operates all local services, and establishes management connectivity with IBM Cloud. This requires three hosts for the HA control plane, plus an additional host to support local management services.
* Satellite connectors support cloud endpoints that enable communication to the client premises. These require a client-supported docker host (x86), and can also be deployed in redundant and HA configurations.

For deployment options, including redundant and HA patterns, see the [Satellite Connector overview](/docs/satellite?topic=satellite-understand-connectors).
{: note}

Related links:
* [Connector overview](/docs/satellite?topic=satellite-understand-connectors)
* [FAQs](/docs/satellite?topic=satellite-faqs)
* [Limitations, default settings, usage requirements](/docs/satellite?topic=satellite-requirements)
* [Access management](/docs/satellite?topic=satellite-iam)

## Security and data encryption
{: #reference-security-data-encryption-satellite}

* Uses TLS 1.3 encryption for all communications, with managed key rotation implemented through an IBM Site Recovery Engineer.
* The client always has control on communication and is able to individually disable and enable any set of endpoints on demand.
* Client can specify their own encryption for individual endpoints they create, if wanted.
* Fully supports IAM roles and responsibility assignment to control access and data exposure risk.

Related links:
* [Access management](/docs/satellite?topic=satellite-iam)
* [Architecture](/docs/satellite?topic=satellite-service-architecture)
* [Compliance](/docs/satellite?topic=satellite-compliance)
* [Service connection](/docs/satellite?topic=satellite-service-connection)
* [Data security](/docs/satellite?topic=satellite-data-security)

## Resiliency
{: #reference-resiliency-satellite}

* Satellite Locations and Satellite Connectors both support High Availability (HA) deployments across multiple client availability zones.
* The client premise deployment is the responsibility of the client to deploy across hosts that are logically and physically independent of give the greatest failure resiliency.
* For resiliency the IBM Cloud infrastructure is deployed across three independent zones, each zone is a separate data center with independent power, cooling, and networking for maximum reliability.

Related links:
* [Architecture](/docs/satellite?topic=satellite-service-architecture)
* [High availability](/docs/satellite?topic=satellite-ha)

## Monitoring and logging
{: #reference-monitoring-logging-satellite}

IBM Satellite connectivity uses a combination of IBM Log Analysis and IBM Cloud Monitoring for log analysis and metrics monitoring.

* All operations work through the client's IBM Cloud account, and can be accomplished through the UI, CLI, or API.
* Solution management is provided by an IBM Cloud Site Reliability Engineer. The client is responsible for their on-premises compute, network, and storage management.

### Satellite log analysis
{: #satellite-logging}

You can use IBM Log Analysis to view application and connection logs for satellite connectivity. IBM Log Analysis offers administrators, DevOps teams, and developers advanced features to filter, search, and tail log data, define alerts, and design custom views to monitor application and system logs. For more information, refer to [Logging for Satellite](/docs/satellite?topic=satellite-health).

### Satellite metrics monitoring
{: #satellite-metrics}

IBM Cloud Satellite® comes with basic tools to help you manage the health of your Satellite resources, such as reviewing location and host health. Also, you can integrate Satellite and other IBM Cloud resources with IBM Cloud Monitoring to get a comprehensive view and tools to manage all your resources. 

Related links:
* [Monitoring for Satellite](/docs/satellite?topic=satellite-monitor)
* [Auditing, logging, and monitoring Satellite Link endpoints](/docs/satellite?topic=satellite-link-cloud-monitor)

# AZ-900: Describe Azure Pricing, Service Level Agreements, and Lifecycles (20-25%)

## Describe Azure Subscriptions

* Describe an [Azure Subscription](https://docs.microsoft.com/en-us/azure/architecture/cloud-adoption/getting-started/azure-resource-access#what-is-an-azure-subscription)
* Describe the uses and options with Azure Subscriptions such as:
    * Access Control
    * Offer Types
* Describe subscription management using Management Groups

## Describe planning and management of costs

* Describe options for purchasing Azure products and services
   * Enterprise Agreement
      * Custom Pricing / Annual Billing
   * Web Direct
      * Pay-As-You-Go (Pay for what you use)
   * Cloud Solutions Provider
      * Go through a third party to manage your resources and pay your azure bill.
   
* Describe options around [Azure Free account](https://azure.microsoft.com/en-ca/free/free-account-faq/)
* Describe the factors affecting costs such as:
    * Resource Types
      * Not all resources are created equal
      * Some resources are charged by different metrics
      * Storage - Charged by how much data is stored
      * Network - Charged by bandwith used
    * Services
      * Some services may cost extra (RedHat(Enterprise OS))
    * Locations
      * Based off billing zones.
    * Ingress traffic
      * Uploading data is typically free
    * Egress traffic
      * Downloading data does incure a charge, how much you are charged is based on your zone
* Describe Zones for billing purposes
    * Zones have their own price points for things (Zones are based on geographical location)
* Describe the [Pricing calculator](https://azure.microsoft.com/en-ca/pricing/calculator/)
    * Provides a pricing estimate based on resource(OS,Storage,Networking,Support,etc)/region/etc
* Describe the [Total Cost of Ownership (TCO) calculator](https://azure.microsoft.com/en-ca/pricing/tco/)
    * Estimates costs savings by comparing your on-premise workloads to a deployment in the cloud
* Describe [best practices for minimizing Azure costs](https://docs.microsoft.com/en-us/azure/billing/billing-getting-started) such as:
    * Performing [Cost Analysis](https://docs.microsoft.com/en-us/azure/cost-management/quick-acm-cost-analysis)
    * Creating [spending limits](https://docs.microsoft.com/en-us/azure/billing/billing-spending-limit) and [quotas](https://docs.microsoft.com/en-us/azure/azure-subscription-service-limits)
    * [Using tags to identify cost owners](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-using-tags)
    * Using [Azure reservations](https://azure.microsoft.com/en-ca/reservations/)
    * Using [Azure Advisor recommendations](https://docs.microsoft.com/en-ca/azure/advisor/advisor-overview)
        * Gives advise on things that you can do the cut costs (Resize VM's, Unused Gateways)
        * Express route circuits 
* Describe [Azure Cost Management](https://docs.microsoft.com/en-us/azure/cost-management/overview-cost-mgt)
    * You use Azure Cost Management and Billing features to conduct billing administrative tasks and manage billing access to costs
    * Gives you a breakdown on your spendings
## Describe Azure Service Level Agreements (SLAs)

* Describe a [Service Level Agreement (SLA)](https://azure.microsoft.com/en-ca/support/legal/sla/)
   * a commitment between a service provider and a client. Particular aspects of the service – quality, availability, responsibilities – are agreed between the service provider and the service user
* Describe Composite SLAs
   * A compostie SLA is when you combine the SLA of two solutions (A virtual machine SLA/SQL Server Database SLA)
* Describe how to determine an appropriate SLA for an application

## Describe service lifecycle in Azure

* Describe Public Preview features
* Describe [Private Preview features](https://azure.microsoft.com/en-ca/support/legal/preview-supplemental-terms/)
* Describe the term General Availability (GA)
    * GA means a service is in production and can be used by anyone with an Azure subscription
* Describe how to [monitor feature updates and product changes](https://azure.microsoft.com/en-ca/updates/)

[Return to Table of Contents](README.md)

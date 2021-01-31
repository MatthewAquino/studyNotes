# AZ-900: Describe Security, Privacy, Compliance, and Trust (25-30%)

## Describe securing network connectivity in Azure

* Describe [Network Security Groups (NSG)](https://docs.microsoft.com/en-us/azure/virtual-network/security-overview)
   * Filters traffic to and from Azure Resources inside of a virtual Network  
   * Contains Security rules that allow or deny traffic  
   * Can define a source/destination port and protocol
   * Manages communication between your resources within or between Virtual Networks  
   * A stateless firewall  (Traffic is only analyzed at one end)  
* Describe [Application Security Groups (ASG)](https://docs.microsoft.com/en-us/azure/virtual-network/security-overview#application-security-groups)
   * Allows you to group Virtual machines together and define network securtiy policies based on those groups
   * NIC can be a memeber of multiple application securtiy groups Up to the [Azure Limit](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/azure-subscription-service-limits?toc=/azure/virtual-network/toc.json#azure-resource-manager-virtual-networking-limits)
   * Can Deny traffic based on port/protocol
* Describe User Defined Routing (UDR)
  * Allows network admins to control the routing tables between subnets within a subnet as well as between virtual networks allowing greater control over traffic flow.
* Describe [Azure Firewall](https://docs.microsoft.com/en-us/azure/firewall/overview)
   * Edge Device  
   * The azure firewall provides protection against Non-HTTP/S traffic  
   * Public IP gets attached to the firewall instead of the NIC on the Virtual Machine  
   * Analyzes Inbound/Outbound traffic  
   * Allows/Denies traffic based on IP/Ports/FQDN  
   * Stateful Firewall (Traffic is analyzed end to end)  
   * Easily Scaleable, built in high avability  
* Describe [Azure DDoS Protection](https://docs.microsoft.com/en-us/azure/virtual-network/ddos-protection-overview)
   * All traffic to Azure flows through the azure backbone, Traffic is analyzed here and DDOS Traffics is stopped this happens before it gets to your infrastructure
   * Tiers - Basic : Real time mitigation of common network attacks Standard (Is always on and built in  : Is fine tuned for Azure Virtual networks, stops more advanced attacks  
* Choose an appropriate Azure security solution
   * Microsoft recommends you choose all of them (Take a layered approach)
   * Azure firewall acts as an edge device analyzing traffic going in and out of your azure infrastructure
   * Network Securtiy groups filter traffic that moves between/within your virtual networks 

## Describe core Azure Identity services

* Describe the difference between [Authentication and Authorization](https://docs.microsoft.com/en-us/azure/app-service/overview-authentication-authorization)
   * Authentication - This is the process of verifying who a user is  (Who are you?)
   * Authorization -  This  is the process of what they have access to (What can you access?)
* Describe [Azure Active Directory](https://docs.microsoft.com/en-ca/azure/active-directory/fundamentals/active-directory-whatis)
   * Acts as authentication within azure
   * A cloud based identity service
   * Applications launch in the cloud can use this as a centralized place that handles authentication/authorization
   * Can be synced with your on-prem Active Directory
   * Handles : Single-Sign-on, Buisness to Buisness, Buisness to Customer :
     * Single-Sign-On Centralizes your logins for your apps are services (One password to rule them all)  
* Describe [Azure Multi-Factor Authentication](https://docs.microsoft.com/en-us/azure/active-directory/authentication/concept-mfa-howitworks)
   * Provides additional security  by requring a second piece of information to sign in
   * Another piece of information to verify who you are (Phone Code, Physical Key,etc.)
   * Types of MFA :
     * Something you know - Password, Pin, Etc  
     * Something you have - SMS Code, Authenticator Token  
     * Something you are - Fingerprint, Retina, etc  
   * Global admins have this be default, all other types of accounts require a license to have MFA 

## Describe security tools and features of Azure

* Describe [Azure Security Center](https://docs.microsoft.com/en-us/azure/security/azure-security)
   * Helps insure that your cloud enviroments is secure.
   * A Monitoring service that manages threat protection for your cloud resoruces and on-prem servers  
   * Will Monitor and analyze securtiy based on policies that you set  
   * Uses machine learning to detect if malware is present on your reosource, Can also monitor your network and detect attacks (DDOS)  
   * Azure Security Center Tiers : Free - Assessments, Recommendations Standard : Full Securtiy Center Suite (Advanced Monitoring, Threat Detection,etc.) 
   * Can be used incident response (Detect,Asses,Diagnose)  
* Describe [Azure Security Center](https://docs.microsoft.com/en-ca/azure/security-center/security-center-intro) usage scenarios  
* Describe [Key Vault](https://docs.microsoft.com/en-us/azure/key-vault/key-vault-whatis)
   * A centralzied cloud service for securely storing and accessing secrets (API Keys, Password, Certificate,etc) A Key vault is a logical group of secrets
   * Key Vaults Terms :
     * Tenant -  A tenant is the organization that owns and manages the instace of Micrsoft cloud services
     * Vault Owner - Can create a vault key and gain full access/control over it
     * Vault Comsumer - Can perform actiosn on the assets inside the key vault, the available actions depends on permissions granted
* Describe [Azure Information Protection (AIP)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection)
   * Cloud based solution that helps us classify and "Maybe" protect our documents and emails.
   * Allows organizations to classify and protect documents and emails by applying labels
   * Labels can be applied : 
      * Automatically by administrators using rules and conditions
      * Manually by users
      * By a combiantion where the administrators define the recomendations shown to users
   * Labeling content includes :
      * Classification that can be detected regardless of where data is stored or wtih whom it is shared
      * Visual markings such as headers, footers, or watermarks
      * Metadata added to files and emails headers in clear text, this insures other services can identify the classification
* Describe [Azure Advanced Threat Protection (ATP)](https://docs.microsoft.com/en-us/azure-advanced-threat-protection/what-is-atp)
   * A cloud based security solution that leverages your on-premise active directory signals to identify, detect and investigate advanced threats, compromised identities and malicious insider actions
   * Monitors and profile user behavior and activities
   * Protect user identities and reduce the attack surface
   * Identify suspicious activities and advanced attacks across the cyber-attack kill-chain
   * Components of ATP :
     * ATP Portal (portal.atp.azure.com)
     * ATP Sensor : Installed on your Domain Controller Sends data to the ATP Cloud Service
     * ATP Cloud service : Runs on Azure Infrastructure
 * Azure Information Protection and Azure Threat Detection are premium services (Cost Extra to get)

## Describe Azure governance methodologies

* Describe policies and initiatives with [Azure Policy](https://docs.microsoft.com/en-us/azure/governance/policy/overview)
  * A Service you use to define, assign and manage standards for resources in your enviroment (Giving the engineers the ability to spin up VM but limit the resources they can give it)
  * Can force a policy for any kind of standard you want to support (SQL Server Version, Only Linux, All sites with HTTPS,etc)
  * Parts of an Azure Policy :
     * Policy Definition : What we are evaluating and what action we will take (Json Format)
         * Actions : Deny,  Disabled(Ignore), Append(Tags), Audit, Deploy if not Exists(Template)
     * Policy Assignment : Assign a policy to a specific Scope, can also add exclusions to the scope.
  * An Azure policy initiative is a grouping of policy definitions that are grouped together towards a specific goal
* Describe [Role-Based Access Control (RBAC)](https://docs.microsoft.com/en-us/azure/role-based-access-control/overview)
  * Acts as authorization in azure
  * A role is a set of permissions that users can be granted to access Azure Services
  * A scope is the set of resources that the access applies to
  * Different Kinds of Roles :
    * Contributor - Is able to edit items within the resource group
    * Reader - can read the resources but cannot edit them
* Describe [Locks](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-lock-resources)
  * Allows you to lock subscriptiosn,resources groups or resources to prevent other users from accidentally deleting or modifiying critcal resources
  * The Azure lock levels are : 
    * CanNotDelete - Authorized users can still read and modify a resource but they cannot delete it
    * ReadOnly - Authorized users can read a resource but they cannot delete or update the resource
* Describe [Azure Advisor](https://docs.microsoft.com/en-us/azure/advisor/advisor-overview) security assistance
  * A personalized cloud consultant that helps you follow best practices to optimize your Azure deployments
  * It analyzes your resource configurations and usage telemetry and then recommends solutions that can help you improve the cost effectiveness,performance,reliability, and security of your Azure resoruces.
* Describe [Azure Blueprints](https://docs.microsoft.com/en-us/azure/governance/blueprints/overview)
  * A repeatable set of Azure Resources that adhere to standards, patterns and requirements.
  * What's inside a Blueprint
     * Role Agginments
     * Policy Assignments
     * ARM Templates
     * Resource Groups
   * Changes made to the blueprint propgates the changes to any resources associated with it.
* [Azure Management Groups](https://docs.microsoft.com/en-us/azure/governance/management-groups/overview)
  * Containers for managing access,policies and compliance accross multiple subscriptions
  * Instead of appying policies at the management group level instead of at the subscription level
  * Provides governonce over all subscriptions
## Describe monitoring and reporting options in Azure

* Describe [Azure Monitor](https://docs.microsoft.com/en-us/azure/azure-monitor/overview)
  * Collects,Analyze,Act on Telemetry(Data, What your resources are doing)
  * Can collect data from Cloud(Apps,Virtual Machines, Azure Active Directory,etc)/On-Prem Infrastructure/App Monitoring
  * Provides a whole subscription overview
  * Give you the ability to autoscale and if a certain threshold is met Azure will scale your infrastructure automatically
* Describe [Azure Service Health](https://docs.microsoft.com/en-ca/azure/service-health/)
  * Is a suite of tools that provide personalized guidance and support when issues in Azure Service are or may affect you in the future
  * Provides updates on the health of Azure Services
* Describe the use cases and benefits of:
    * Azure Monitor
    * Azure Service Health

## Describe privacy, compliance and data protection standards in Azure

* Describe industry compliance terms such as:
    * [GDPR](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-overview) | [More info](https://docs.microsoft.com/en-us/office365/securitycompliance/manage-gdpr-data-subject-requests-with-the-dsr-case-tool)
    * [ISO](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27018)
    * [NIST](https://www.microsoft.com/en-us/trustcenter/compliance/NIST_CSF)
* Describe the [Microsoft Privacy Statement](https://privacy.microsoft.com/en-ca/privacystatement)
    * Explains what personal data is collected by microsoft
    * How that is used/Why they share it
* Describe the [Trust Center](https://www.microsoft.com/en-us/trustcenter/cloudservices/azure)
    * A website where microsoft outlines how they deal with trust
    * Security/Privacy/Compliance/Transparency
* Describe the [Service Trust Portal](https://servicetrust.microsoft.com/) | [Getting Started](https://docs.microsoft.com/en-us/office365/securitycompliance/get-started-with-service-trust-portal)
   * The Service Trust Portal contains the results of third party audits that microsoft goes through
   * Details on how Microsoft protects your Data
* Describe [Compliance Manager](/)
   * Prvoides a self assessment on how your infrastrucuture meets various standards (GDPR/ISO/etc)
   * Requires the compliance admin roles to login to
* Determine if Azure is compliant for a business need
* Describe [Azure Government cloud services](https://docs.microsoft.com/en-us/azure/azure-government/documentation-government-welcome)
* Describe Azure China cloud services

[Return to Table of Contents](README.md)

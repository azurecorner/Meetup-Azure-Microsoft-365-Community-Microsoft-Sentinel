# Meetup-Azure-Microsoft-365-Community-Microsoft-Sentinelt 

**1. What is security information and event management (SIEM)?**

A SIEM system is a tool that an organization uses to collect, analyze, and perform security operations on its computer systems. Those systems can be hardware appliances, applications, or both.
A SOAR is Security Orchestration, Automation and Response : A set of software programs to collect  security threats from sources and respond to security events 

In its simplest form, a SIEM system enables you to:

Collect and query logs.
Do some form of correlation or anomaly detection.
Create alerts and incidents based on your findings.
A SIEM system might offer functionality such as:

* Log management: The ability to collect, store, and query the log data from resources within your environment.
* Alerting: A proactive look inside the log data for potential security incidents and anomalies.
* Visualization: Graphs and dashboards that provide visual insights into your log data.
* Incident management: The ability to create, update, assign, and investigate incidents that have been identified.
* Querying data: A rich query language, similar to that for log management, that you can use to query and understand your data.

2. **What is Microsoft Sentinel?**
Azure Sentinel is a Security Information and Event Management (SIEM) and Security Orchestration Automation Response (SOAR) solution from Microsoft

In this session I will setup a Microsoft Sentinel Workspace and learn about the followings 
* Data connectors
* Workbooks
*  Analytics alerts
* Threat hunting
* Incidents and investigations
*  Automation playbooks
![01-end-to-end](https://user-images.githubusercontent.com/108787059/205441529-a616e13a-982d-4114-bcb0-fe2939996603.svg)


Microsoft Sentinel workspace

**Single-tenant single workspace**
![single-tenant-workspace](https://user-images.githubusercontent.com/108787059/205441652-79dbed21-48a0-4faa-876c-d16ba12ea2cc.png)

This workspace receives logs from resources in other regions within the same tenant. Because the log data (when collected) will travel across regions and stored in another region, this creates two possible concerns. First, it can incur a bandwidth cost. Second, if there's a data governance requirement to keep data in a specific region, the single workspace option wouldn't be an implementation option.

**Single-tenant with regional Microsoft Sentinel workspaces**
![single-tenant-regional-workspace](https://user-images.githubusercontent.com/108787059/205441664-cd1652b4-0a5e-4b79-b2c0-53474e2621c2.png)

The single-tenant with regional Microsoft Sentinel workspaces will have multiple Sentinel workspaces requiring the creation and configuration of multiple Microsoft Sentinel and Log Analytics workspaces.
* No central pane of glass. You aren't looking in one place to see all the data
* Analytics, Workbooks, etc. must be deployed multiple times.
**Multi-tenant workspaces**
![multi-tenant-workspaces](https://user-images.githubusercontent.com/108787059/205441668-f2482989-ac0b-474d-92d2-3d5579479a64.png)

to manage a Microsoft Sentinel workspace, not in your tenant, you implement Multi-Tenant workspaces using Azure Lighthouse.

Use the same log analytics workspace as Microsoft Defender for Cloud

Create a Microsoft Sentinel workspace
To enable Microsoft Sentinel, you need contributor permissions to the subscription in which the Microsoft Sentinel workspace resides. To use Microsoft Sentinel, you need either contributor or reader permissions on the resource group that the workspace belongs.
Microsoft Sentinel-specific roles
All Microsoft Sentinel built-in roles grant read access to the data in your Microsoft Sentinel workspace:

Microsoft Sentinel Reader: can view data, incidents, workbooks, and other Microsoft Sentinel resources.

Microsoft Sentinel Responder: can, in addition to the above, manage incidents (assign, dismiss, etc.)

Microsoft Sentinel Contributor: can, in addition to the above, create and edit workbooks, analytics rules, and other Microsoft Sentinel resources.

Microsoft Sentinel Automation Contributor: allows Microsoft Sentinel to add playbooks to automation rules. It isn't meant for user accounts.

For best results, these roles should be assigned to the resource group that contains the Microsoft Sentinel workspace. The roles then apply to all the resources that deploy to support Microsoft Sentinel, if those resources are in the same resource group.
![image](https://user-images.githubusercontent.com/108787059/205442362-979c288a-74b9-47bd-8d06-42176ab6274c.png)

**3. Enable Microsoft Sentinel**
Create a Log Analytics workspace, a storage account , a keyvault and a virtual machine

**Data Connectors**

**Azure Sentinel Workbook**  

**Analytics alerts**

**Thread hunting**

Threat hunting is the process of iteratively searching through a variety of data with the objective to identify threats in the systems.
**Incidents and investigations**

**Automation playbooks**



https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/AzureActivity/Creating_Anomalous_Number_Of_Resources.yaml

https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/SigninLogs/DisabledAccountSigninAttempts.yaml


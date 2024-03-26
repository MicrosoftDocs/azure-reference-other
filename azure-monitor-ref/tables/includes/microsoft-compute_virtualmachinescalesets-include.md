---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.compute/virtualmachinescalesets
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|
| [CommonSecurityLog](/azure/azure-monitor/reference/tables/CommonSecurityLog)<p>This table is for collecting events in the Common Event Format, that are most often sent from different security appliances such as Check Point, Palo Alto and more. | security | Security, SecurityInsights | No| [Yes](/azure/azure-monitor/reference/queries/commonsecuritylog)|
| [ConfigurationChange](/azure/azure-monitor/reference/tables/ConfigurationChange)<p>View changes to in-guest configuration data such as Files Software Registry Keys Windows Services and Linux Daemons | management | ChangeTracking | No| [Yes](/azure/azure-monitor/reference/queries/configurationchange)|
| [ConfigurationData](/azure/azure-monitor/reference/tables/ConfigurationData)<p>View the last reported state for in-guest configuration data such as Files Software Registry Keys Windows Services and Linux Daemons | management | ChangeTracking | No| [Yes](/azure/azure-monitor/reference/queries/configurationdata)|
| [ContainerLog](/azure/azure-monitor/reference/tables/ContainerLog)<p>Log lines collected from stdout and stderr streams for containers. | container, applications | AzureResources, ContainerInsights, Containers | No| [Yes](/azure/azure-monitor/reference/queries/containerlog)|
| [Event](/azure/azure-monitor/reference/tables/Event)<p>Events from Windows Event Log on Windows computers using the Log Analytics agent. | virtualmachines | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/event)|
| [Heartbeat](/azure/azure-monitor/reference/tables/Heartbeat)<p>Records logged by Log Analytics agents once per minute to report on agent health. | virtualmachines, container, management | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/heartbeat)|
| [InsightsMetrics](/azure/azure-monitor/reference/tables/InsightsMetrics)<p>Table that stores metrics. 'Perf' table also stores many metrics and over time they all will converge to InsightsMetrics for Azure Monitor Solutions  | virtualmachines, container, resources | AzureResources, ContainerInsights, InfrastructureInsights, LogManagement, ServiceMap, VMInsights | No| [Yes](/azure/azure-monitor/reference/queries/insightsmetrics)|
| [Perf](/azure/azure-monitor/reference/tables/Perf)<p>Performance counters from Windows and Linux agents that provide insight into the performance of hardware components operating systems and applications. | virtualmachines, container | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/perf)|
| [ProtectionStatus](/azure/azure-monitor/reference/tables/ProtectionStatus)<p>Antimalware installation info and security health status of the machine: | security | AntiMalware, Security, SecurityCenter, SecurityCenterFree | No| [Yes](/azure/azure-monitor/reference/queries/protectionstatus)|
| [SecurityBaseline](/azure/azure-monitor/reference/tables/SecurityBaseline)<p> | security | Security, SecurityCenter, SecurityCenterFree | No| -|
| [SecurityEvent](/azure/azure-monitor/reference/tables/SecurityEvent)<p>Security events collected from windows machines by Azure Security Center or Azure Sentinel. | security | Security, SecurityInsights | No| [Yes](/azure/azure-monitor/reference/queries/securityevent)|
| [Syslog](/azure/azure-monitor/reference/tables/Syslog)<p>Syslog events on Linux computers using the Log Analytics agent. | virtualmachines, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/syslog)|
| [Update](/azure/azure-monitor/reference/tables/Update)<p>Details for update schedule run. Includes information such as which updates where available and which were installed. | management, security | Security, SecurityCenter, SecurityCenterFree, Updates | No| [Yes](/azure/azure-monitor/reference/queries/update)|
| [UpdateRunProgress](/azure/azure-monitor/reference/tables/UpdateRunProgress)<p>Breaks down each run of your update schedule by the patches available at the time with details on the installation status of each patch. | management | Updates | No| [Yes](/azure/azure-monitor/reference/queries/updaterunprogress)|
| [UpdateSummary](/azure/azure-monitor/reference/tables/UpdateSummary)<p>Summary for each update schedule run. Includes information such as how many updates were not installed. | virtualmachines | Security, SecurityCenter, SecurityCenterFree, Updates | No| [Yes](/azure/azure-monitor/reference/queries/updatesummary)|
| [VMBoundPort](/azure/azure-monitor/reference/tables/VMBoundPort)<p>Traffic for open server ports on the monitored machine. | virtualmachines | AzureResources, InfrastructureInsights, ServiceMap, VMInsights | No| -|
| [VMComputer](/azure/azure-monitor/reference/tables/VMComputer)<p>Inventory data for servers collected by the Service Map and VM Insights solutions using the Dependency agent and Log analytics agent. | virtualmachines | AzureResources, ServiceMap, VMInsights | No| -|
| [VMConnection](/azure/azure-monitor/reference/tables/VMConnection)<p>Traffic for inbound and outbound connections to and from monitored computers. | virtualmachines | AzureResources, InfrastructureInsights, ServiceMap, VMInsights | No| -|
| [VMProcess](/azure/azure-monitor/reference/tables/VMProcess)<p>Process data for servers collected by the Service Map and VM Insights solutions using the Dependency agent and Log analytics agent. | virtualmachines | AzureResources, ServiceMap, VMInsights | No| -|
| [W3CIISLog](/azure/azure-monitor/reference/tables/W3CIISLog)<p>Internet Information Server (IIS) log on Windows computers using the Log Analytics agent. | management, virtualmachines | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/w3ciislog)|
| [WindowsFirewall](/azure/azure-monitor/reference/tables/WindowsFirewall)<p> | security | Security, WindowsFirewall | No| -|
| [WireData](/azure/azure-monitor/reference/tables/WireData)<p>Network data collected by the WireData solution using by the Dependency agent and Log analytics agent. | virtualmachines, security | WireData, WireData2 | No| [Yes](/azure/azure-monitor/reference/queries/wiredata)|

  

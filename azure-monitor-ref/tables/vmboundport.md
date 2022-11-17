---
title: Azure Monitor Logs reference - VMBoundPort
description: Reference for VMBoundPort table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# VMBoundPort

 Traffic for open server ports on the monitored machine.

## Categories

- Virtual Machines
## Solutions

- AzureResources
- InfrastructureInsights
- Service Map
- Azure Monitor for VMs
## Resource types

- Virtual machines
- VMware
- Azure Stack HCI
- System Center Virtual Machine Manager
- Virtual Machine Scale Sets




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AgentId | string | Unique agent GUID for the agent reporting data on the server. |
| BytesReceived | long | Bytes received on the port |
| BytesSent | long | Bytes sent on the port |
| Computer | string | Name of the server |
| Ip | string | Port IP address. Can be wildcard IP 0.0.0.0. |
| IsWildcardBind | bool | Specifies whether connection made as a wildcard bind request. |
| LinksEstablished | long | Count of links established on the port. |
| LinksLive | long | Count of live links at the end of the time period recorded. |
| LinksTerminated | long | Count of terminated links over the time periof recorded. |
| Machine | string | Unique identifier to the machine in the ServiceMapComputer_CL table. |
| Port | int | Port number. |
| PortId | string | Port ID. |
| Process | string | Identity of the process or group of processes that the port is associated with. |
| ProcessName | string | Unique identifier for the process in the ServiceMapProcess_CL table. |
| Protocol | string | The protocol. Example tcp or udp (only tcp is currently supported). |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Responses | long | Count of responses in the time period recorded. |
| ResponseTimeMax | long | Measurement of the maximum time between first and last byte received. |
| ResponseTimeMin | long | Measurement of the minimum time between first and last byte received. |
| ResponseTimeSum | long | Measurement of the total time between first and last byte received |
| SourceSystem | string | Value is OpsManager for all records. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime | Date and time the record was created. |
| Type | string | The name of the table |

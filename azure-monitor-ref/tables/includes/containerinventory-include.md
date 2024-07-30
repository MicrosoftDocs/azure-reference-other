---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: ContainerInventory
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Command | string | entrypoint and the command executed for all running containers |
| ComposeGroup | string | Docker Compose Project name. Comes from container label : com.docker.compose.project |
| Computer | string | Computer name/Node name |
| ContainerHostname | string |   |
| ContainerID | string | Unique ContainerID |
| ContainerState | string | Last known state of the container |
| CreatedTime | datetime | Container creation time |
| EnvironmentVar | string | Container's environment variables |
| ExitCode | int | Container exit code |
| FinishedTime | datetime | Container termination time |
| Image | string | Container Image Name  |
| ImageID | string | Container Image ID |
| ImageTag | string | Container Image Tag  |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Links | string | Container's legacy Hostconfig links |
| Name | string | Name of the container |
| Ports | string | Container's port bindings |
| Repository | string | Container's Remote repository |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StartedTime | datetime | Container start time |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime | Date and time the record was created. |
| Type | string | The name of the table |

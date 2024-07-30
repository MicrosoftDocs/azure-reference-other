---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: IoTHubDistributedTracing
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CallerLocalTimeUtc | datetime | Creation time of the message as reported by the device local clock |
| Category | string | Category of the log event |
| DependencyType | string | For outgoing requests (dependencies), describes type of the dependency |
| DurationMs | int | Duration of the operation in milliseconds |
| EventKind | string | Kind of the event |
| InstanceId | string | Name of the instance that processed request |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsRoutingEnabled | bool | Either true or false, indicates whether or not message routing is enabled in the IoT Hub |
| Level | string | Level of severity of the event |
| Location | string | Azure region in which the Iot Hub is located |
| MessageSize | int | The size of the message in bytes |
| OperationName | string | Operation name of the event |
| ParentId | string | Unique identifier of current span within trace (16 hex characters). A request without a parent id is the root of the trace. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceSubName | string | Name of sub-component that reports this message |
| ResultDescription | string | Result description of the event, typically elaborates on the error |
| ResultSignature | int | The status code of the event |
| ResultType | string | Result type of the event, typically empty unless it's an error |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SpanId | string | Unique identifier of current span within trace (16 hex characters) |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time at which this event is generated and logged |
| TraceFlags | int | A bit field for controlling tracing options. For example, sampling and trace level. |
| TraceId | string | Globally unique identifier of the trace (32 hex characters) |
| Type | string | The name of the table |
| Uri | string | Absolute request URI |

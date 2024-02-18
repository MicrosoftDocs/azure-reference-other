---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: MicrosoftDynamicsTelemetryPerformanceLogs
---


| Column | Type | Description |
|---|---|---|
| ActivityId | string | Unique identifier for an activity |
| BatchJobId | long | Id of the batch job |
| BatchJobTaskId | long | Task Id of the batch job |
| _BilledSize | real | The record size in bytes |
| CallStack | string | Execution call stack |
| Category | string | Log category |
| ClassName | string | Name of the class |
| ConnectionType | string | Type of the connection |
| CountOfDdl | int | Count of data definition requests |
| CountOfDelete | int | Count of delete requests |
| CountOfInsert | int | Count of insert requests |
| CountOfOther | int | Count of other requests |
| CountOfProc | int | Count of procedure requests |
| CountOfSelect | int | Count of select requests |
| CountOfUpdate | int | Count of update requests |
| Duration | int | Duration (in milliseconds) of the form execution time |
| DurationInMilliSeconds | int | Duration in milliseconds of the batch jobs |
| Environment | string | Name of the environment as deployed in Lifecycle Services |
| EnvironmentId | string | Unique identifier for an environment as shown in Lifecycle Services |
| ErrorMessage | string | Error message logged in the application  |
| EventMessage | string | Additional information about the event |
| EventName | string | Name of the event |
| ExecutionResultRowCount | int | Returned rowCount from the executed SQL query |
| ExecutionStatus | int | Execution Status of the query |
| ExecutionTimeSeconds | real | Execution time in seconds for the AosDatabaseSlowQuery event |
| formName | string | Name of the form in Finance and Operations |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsValid | bool | Is it valid |
| IsWarmEvent | bool | Is this a warm event |
| LegalEntity | long | Legal entity |
| Parameters | dynamic | Collection of SQL performance metrics |
| Pid | int | Process id |
| QueryType | string | Type of the executed SQL query |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Role | string | Type of the machine (AOS/BI) emitting the events |
| RoleInstance | string | Name of the machine emitting the events |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SqlCpu | real | SqlCpu Utilization |
| SqlSpid | int | Process id for the SQL statement (SqlSpid) |
| SqlStatement | string | SQL query statement |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of the log. |
| TransactionDurationSeconds | real | Transaction duration in seconds for Aos Large Active Transactions |
| Type | string | The name of the table |

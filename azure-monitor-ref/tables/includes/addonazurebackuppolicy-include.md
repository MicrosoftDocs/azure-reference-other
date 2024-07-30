---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AddonAzureBackupPolicy
---


| Column | Type | Description |
|---|---|---|
| ArchiveTierDailyRetentionDuration | int |   |
| ArchiveTierDefaultRetentionDuration | int |   |
| ArchiveTieringDuration | int |   |
| ArchiveTieringDurationType | string |   |
| ArchiveTieringMode | string |   |
| ArchiveTierMonthlyRetentionDuration | int |   |
| ArchiveTierStorageReplicationType | string |   |
| ArchiveTierWeeklyRetentionDuration | int |   |
| ArchiveTierYearlyRetentionDuration | int |   |
| AzureDataCenter | string |   |
| BackupDaysOfTheWeek | string |   |
| BackupFrequency | string |   |
| BackupIntervalInHours | int |   |
| BackupManagementServerUniqueId | string |   |
| BackupManagementType | string |   |
| BackupTimes | string |   |
| _BilledSize | real | The record size in bytes |
| Category | string |   |
| DailyRetentionDuration | int |   |
| DailyRetentionTimes | string |   |
| DatasourceType | string |   |
| DiffBackupDaysofTheWeek | string |   |
| DiffBackupFormat | string |   |
| DiffBackupRetentionDuration | int |   |
| DiffBackupTime | string |   |
| DifferentialBackupDaysOfTheWeek | string |   |
| DifferentialBackupFrequency | string |   |
| DifferentialBackupTimes | string |   |
| ExtendedProperties | dynamic |   |
| FullBackupDaysOfTheWeek | string |   |
| FullBackupFrequency | string |   |
| FullBackupTimes | string |   |
| IncrementalBackupDaysOfTheWeek | string |   |
| IncrementalBackupFrequency | string |   |
| IncrementalBackupTimes | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LogBackupFrequency | int |   |
| LogBackupRetentionDuration | int |   |
| MonthlyRetentionDaysOfTheMonth | string |   |
| MonthlyRetentionDaysOfTheWeek | string |   |
| MonthlyRetentionDuration | int |   |
| MonthlyRetentionFormat | string |   |
| MonthlyRetentionTimes | string |   |
| MonthlyRetentionWeeksOfTheMonth | string |   |
| OperationName | string |   |
| PolicyId | string |   |
| PolicyName | string |   |
| PolicySubType | string |   |
| PolicyTimeZone | string |   |
| PolicyUniqueId | string |   |
| ResourceGroupName | string |   |
| ResourceId | string |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RetentionDuration | int |   |
| RetentionType | string |   |
| ScheduleWindowDuration | int |   |
| ScheduleWindowStartTime | datetime |   |
| SchemaVersion | string |   |
| SnapshotTierDailyRetentionDuration | int |   |
| SnapshotTierDefaultRetentionDuration | int |   |
| SnapshotTierMonthlyRetentionDuration | int |   |
| SnapshotTierWeeklyRetentionDuration | int |   |
| SnapshotTierYearlyRetentionDuration | int |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StandardTierDefaultRetentionDuration | int |   |
| State | string |   |
| StorageReplicationType | string |   |
| SubscriptionId | string |   |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SynchronisationFrequencyPerDay | string |   |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
| VaultName | string |   |
| VaultTags | string |   |
| VaultType | string |   |
| VaultUniqueId | string |   |
| WeeklyRetentionDaysOfTheWeek | string |   |
| WeeklyRetentionDuration | int |   |
| WeeklyRetentionTimes | string |   |
| YearlyRetentionDaysOfTheMonth | string |   |
| YearlyRetentionDaysOfTheWeek | string |   |
| YearlyRetentionDuration | int |   |
| YearlyRetentionFormat | string |   |
| YearlyRetentionMonthsOfTheYear | string |   |
| YearlyRetentionTimes | string |   |
| YearlyRetentionWeeksOfTheMonth | string |   |

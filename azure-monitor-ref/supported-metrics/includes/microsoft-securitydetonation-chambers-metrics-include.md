---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: microsoft.securitydetonation/chambers, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Saturation|**Capacity Utilization**<br><br>The percentage of the allocated capacity the resource is actively using. |`CapacityUtilization` |Percent |Maximum, Minimum |`Region`|PT1M |No|
|Saturation|**CPU Utilization**<br><br>The percentage of the CPU that is being utilized across the resource. |`CpuUtilization` |Percent |Average, Maximum, Minimum |`Region`|PT1M |No|
|Traffic|**CreateSubmission Api Results**<br><br>The total number of CreateSubmission API requests, with return code. |`CreateSubmissionApiResult` |Count |Count |`OperationName`, `ServiceTypeName`, `Region`, `HttpReturnCode`|PT1M |No|
|Saturation|**Available Disk Space**<br><br>The percent amount of available disk space across the resource. |`PercentFreeDiskSpace` |Percent |Average, Maximum, Minimum |`Region`|PT1M |No|
|Latency|**Submission Duration**<br><br>The submission duration (processing time), from creation to completion. |`SubmissionDuration` |MilliSeconds |Maximum, Minimum |`Region`|PT1M |No|
|Traffic|**Completed Submissions / Hr**<br><br>The number of completed submissions / Hr. |`SubmissionsCompleted` |Count |Maximum, Minimum |`Region`|PT1M |No|
|Traffic|**Failed Submissions / Hr**<br><br>The number of failed submissions / Hr. |`SubmissionsFailed` |Count |Maximum, Minimum |`Region`|PT1M |No|
|Saturation|**Outstanding Submissions**<br><br>The average number of outstanding submissions that are queued for processing. |`SubmissionsOutstanding` |Count |Average, Maximum, Minimum |`Region`|PT1M |No|
|Traffic|**Successful Submissions / Hr**<br><br>The number of successful submissions / Hr. |`SubmissionsSucceeded` |Count |Maximum, Minimum |`Region`|PT1M |No|
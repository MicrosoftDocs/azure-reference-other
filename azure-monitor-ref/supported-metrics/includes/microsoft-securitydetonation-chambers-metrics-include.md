---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.securitydetonation/chambers, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Saturation|**Capacity Utilization**<p><p>The percentage of the allocated capacity the resource is actively using. |`CapacityUtilization` |Percent |Maximum, Minimum |`Region`|PT1M |No|
|Saturation|**CPU Utilization**<p><p>The percentage of the CPU that is being utilized across the resource. |`CpuUtilization` |Percent |Average, Maximum, Minimum |`Region`|PT1M |No|
|Traffic|**CreateSubmission Api Results**<p><p>The total number of CreateSubmission API requests, with return code. |`CreateSubmissionApiResult` |Count |Count |`OperationName`, `ServiceTypeName`, `Region`, `HttpReturnCode`|PT1M |No|
|Saturation|**Available Disk Space**<p><p>The percent amount of available disk space across the resource. |`PercentFreeDiskSpace` |Percent |Average, Maximum, Minimum |`Region`|PT1M |No|
|Latency|**Submission Duration**<p><p>The submission duration (processing time), from creation to completion. |`SubmissionDuration` |MilliSeconds |Maximum, Minimum |`Region`|PT1M |No|
|Traffic|**Completed Submissions / Hr**<p><p>The number of completed submissions / Hr. |`SubmissionsCompleted` |Count |Maximum, Minimum |`Region`|PT1M |No|
|Traffic|**Failed Submissions / Hr**<p><p>The number of failed submissions / Hr. |`SubmissionsFailed` |Count |Maximum, Minimum |`Region`|PT1M |No|
|Saturation|**Outstanding Submissions**<p><p>The average number of outstanding submissions that are queued for processing. |`SubmissionsOutstanding` |Count |Average, Maximum, Minimum |`Region`|PT1M |No|
|Traffic|**Successful Submissions / Hr**<p><p>The number of successful submissions / Hr. |`SubmissionsSucceeded` |Count |Maximum, Minimum |`Region`|PT1M |No|
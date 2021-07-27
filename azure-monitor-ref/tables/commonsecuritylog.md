---
title: Azure Monitor Logs reference - CommonSecurityLog
description: Reference for CommonSecurityLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 6/1/2021
---

# CommonSecurityLog

 Syslog messages using Common Event Format (CEF) streamed from variety of security solutions.
 
> [!NOTE]
> An Azure Sentinel workspace is required in order to ingest CEF data. For more information, see [Connect your external solution using Common Event Format](/azure/sentinel/connect-common-event-format#prerequisites).
>
 

## Categories

- Security
## Solutions

- Security and Audit
- Azure Sentinel
## Resource types

- Azure Sentinel CEF Table
- Virtual machines
- VMware
- Azure Stack HCI
- System Center Virtual Machine Manager
- Virtual Machine Scale Sets




## Columns

|Column|Type|Description|
|---|---|---|
|Activity|string||
|AdditionalExtensions|string||
|ApplicationProtocol|string||
|CommunicationDirection|string||
|Computer|string||
|DestinationDnsDomain|string||
|DestinationHostName|string||
|DestinationIP|string||
|DestinationMACAddress|string||
|DestinationNTDomain|string||
|DestinationPort|int||
|DestinationProcessId|int||
|DestinationProcessName|string||
|DestinationServiceName|string||
|DestinationTranslatedAddress|string||
|DestinationTranslatedPort|int||
|DestinationUserID|string||
|DestinationUserName|string||
|DestinationUserPrivileges|string||
|DeviceAction|string||
|DeviceAddress|string||
|DeviceCustomDate1|string||
|DeviceCustomDate1Label|string||
|DeviceCustomDate2|string||
|DeviceCustomDate2Label|string||
|DeviceCustomFloatingPoint1|real||
|DeviceCustomFloatingPoint1Label|string||
|DeviceCustomFloatingPoint2|real||
|DeviceCustomFloatingPoint2Label|string||
|DeviceCustomFloatingPoint3|real||
|DeviceCustomFloatingPoint3Label|string||
|DeviceCustomFloatingPoint4|real||
|DeviceCustomFloatingPoint4Label|string||
|DeviceCustomIPv6Address1|string||
|DeviceCustomIPv6Address1Label|string||
|DeviceCustomIPv6Address2|string||
|DeviceCustomIPv6Address2Label|string||
|DeviceCustomIPv6Address3|string||
|DeviceCustomIPv6Address3Label|string||
|DeviceCustomIPv6Address4|string||
|DeviceCustomIPv6Address4Label|string||
|DeviceCustomNumber1|int||
|DeviceCustomNumber1Label|string||
|DeviceCustomNumber2|int||
|DeviceCustomNumber2Label|string||
|DeviceCustomNumber3|int||
|DeviceCustomNumber3Label|string||
|DeviceCustomString1|string||
|DeviceCustomString1Label|string||
|DeviceCustomString2|string||
|DeviceCustomString2Label|string||
|DeviceCustomString3|string||
|DeviceCustomString3Label|string||
|DeviceCustomString4|string||
|DeviceCustomString4Label|string||
|DeviceCustomString5|string||
|DeviceCustomString5Label|string||
|DeviceCustomString6|string||
|DeviceCustomString6Label|string||
|DeviceDnsDomain|string||
|DeviceEventClassID|string||
|DeviceExternalID|string||
|DeviceFacility|string||
|DeviceInboundInterface|string||
|DeviceMacAddress|string||
|DeviceName|string||
|DeviceNtDomain|string||
|DeviceOutboundInterface|string||
|DevicePayloadId|string||
|DeviceProduct|string||
|DeviceTimeZone|string||
|DeviceTranslatedAddress|string||
|DeviceVendor|string||
|DeviceVersion|string||
|EndTime|datetime||
|EventCount|int||
|EventType|int||
|ExternalID|int||
|FileCreateTime|string||
|FileHash|string||
|FileID|string||
|FileModificationTime|string||
|FileName|string||
|FilePath|string||
|FilePermission|string||
|FileSize|int||
|FileType|string||
|FlexDate1|string||
|FlexDate1Label|string||
|FlexNumber1|int||
|FlexNumber1Label|string||
|FlexNumber2|int||
|FlexNumber2Label|string||
|FlexString1|string||
|FlexString1Label|string||
|FlexString2|string||
|FlexString2Label|string||
|IndicatorThreatType|string||
|LogSeverity|string||
|MaliciousIP|string||
|MaliciousIPCountry|string||
|MaliciousIPLatitude|real||
|MaliciousIPLongitude|real||
|Message|string||
|OldFileCreateTime|string||
|OldFileHash|string||
|OldFileID|string||
|OldFileModificationTime|string||
|OldFileName|string||
|OldFilePath|string||
|OldFilePermission|string||
|OldFileSize|int||
|OldFileType|string||
|OriginalLogSeverity|string||
|ProcessID|int||
|ProcessName|string||
|Protocol|string||
|ReceiptTime|string||
|ReceivedBytes|long||
|RemoteIP|string||
|RemotePort|string||
|RequestClientApplication|string||
|RequestContext|string||
|RequestCookies|string||
|RequestMethod|string||
|RequestURL|string||
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|SentBytes|long||
|SimplifiedDeviceAction|string||
|SourceDnsDomain|string||
|SourceHostName|string||
|SourceIP|string||
|SourceMACAddress|string||
|SourceNTDomain|string||
|SourcePort|int||
|SourceProcessId|int||
|SourceProcessName|string||
|SourceServiceName|string||
|SourceSystem|string||
|SourceTranslatedAddress|string||
|SourceTranslatedPort|int||
|SourceUserID|string||
|SourceUserName|string||
|SourceUserPrivileges|string||
|StartTime|datetime||
|_SubscriptionId|string|A unique identifier for the subscription that the record is associated with|
|ThreatConfidence|string||
|ThreatDescription|string||
|ThreatSeverity|int||
|TimeGenerated|datetime||
|Type|string|The name of the table|

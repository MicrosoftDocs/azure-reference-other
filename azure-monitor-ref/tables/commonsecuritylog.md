---
title: Azure Monitor Logs reference - CommonSecurityLog
description: Reference for CommonSecurityLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# CommonSecurityLog

 Syslog messages using Common Event Format (CEF) streamed from variety of security solutions.

## Categories

- Security
## Solutions

- Security and Audit
- SecurityInsights




## Columns

|Column|Type|Description|
|---|---|---|
|SourceSystem|string||
|TimeGenerated|datetime||
|ReceiptTime|string||
|DeviceVendor|string||
|DeviceProduct|string||
|DeviceVersion|string||
|DeviceEventClassID|string||
|Activity|string||
|LogSeverity|string||
|DeviceAction|string||
|SimplifiedDeviceAction|string||
|Computer|string||
|ApplicationProtocol|string||
|EventCount|int||
|DestinationDnsDomain|string||
|DestinationServiceName|string||
|DestinationTranslatedAddress|string||
|DestinationTranslatedPort|int||
|CommunicationDirection|string||
|DeviceDnsDomain|string||
|DeviceExternalID|string||
|DeviceFacility|string||
|DeviceInboundInterface|string||
|DeviceNtDomain|string||
|DeviceOutboundInterface|string||
|DevicePayloadId|string||
|ProcessName|string||
|DeviceTranslatedAddress|string||
|DestinationHostName|string||
|DestinationMACAddress|string||
|DestinationNTDomain|string||
|DestinationProcessId|int||
|DestinationUserPrivileges|string||
|DestinationProcessName|string||
|DestinationPort|int||
|DestinationIP|string||
|DeviceTimeZone|string||
|DestinationUserID|string||
|DestinationUserName|string||
|DeviceAddress|string||
|DeviceName|string||
|DeviceMacAddress|string||
|ProcessID|int||
|ExternalID|int||
|FileCreateTime|string||
|FileHash|string||
|FileID|string||
|FileModificationTime|string||
|FilePath|string||
|FilePermission|string||
|FileType|string||
|FileName|string||
|FileSize|int||
|ReceivedBytes|long||
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
|SentBytes|long||
|Protocol|string||
|RequestURL|string||
|RequestClientApplication|string||
|RequestContext|string||
|RequestCookies|string||
|RequestMethod|string||
|SourceHostName|string||
|SourceMACAddress|string||
|SourceNTDomain|string||
|SourceDnsDomain|string||
|SourceServiceName|string||
|SourceTranslatedAddress|string||
|SourceTranslatedPort|int||
|SourceProcessId|int||
|SourceUserPrivileges|string||
|SourceProcessName|string||
|SourcePort|int||
|SourceIP|string||
|SourceUserID|string||
|SourceUserName|string||
|EventType|int||
|RemoteIP|string||
|RemotePort|string||
|DeviceCustomIPv6Address1|string||
|DeviceCustomIPv6Address1Label|string||
|DeviceCustomIPv6Address2|string||
|DeviceCustomIPv6Address2Label|string||
|DeviceCustomIPv6Address3|string||
|DeviceCustomIPv6Address3Label|string||
|DeviceCustomIPv6Address4|string||
|DeviceCustomIPv6Address4Label|string||
|DeviceCustomFloatingPoint1|real||
|DeviceCustomFloatingPoint1Label|string||
|DeviceCustomFloatingPoint2|real||
|DeviceCustomFloatingPoint2Label|string||
|DeviceCustomFloatingPoint3|real||
|DeviceCustomFloatingPoint3Label|string||
|DeviceCustomFloatingPoint4|real||
|DeviceCustomFloatingPoint4Label|string||
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
|DeviceCustomDate1|string||
|DeviceCustomDate1Label|string||
|DeviceCustomDate2|string||
|DeviceCustomDate2Label|string||
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
|AdditionalExtensions|string||
|MaliciousIP|string||
|ThreatSeverity|int||
|IndicatorThreatType|string||
|ThreatDescription|string||
|ThreatConfidence|string||
|MaliciousIPLongitude|real||
|MaliciousIPLatitude|real||
|MaliciousIPCountry|string||
|StartTime|datetime||
|EndTime|datetime||
|OriginalLogSeverity|string||
|Type|string||
|_ResourceId|string||

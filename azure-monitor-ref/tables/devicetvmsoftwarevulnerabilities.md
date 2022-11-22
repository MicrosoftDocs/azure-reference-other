---
title: Azure Monitor Logs reference - DeviceTvmSoftwareVulnerabilities
description: Reference for DeviceTvmSoftwareVulnerabilities table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# DeviceTvmSoftwareVulnerabilities

 Captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.

## Categories

- Security
## Solutions

- Microsoft Sentinel




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CveId | string | Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system |
| CveTags | dynamic | Array of tags relevant to the CVE; example: ZeroDay, NoSecurityUpdate |
| DeviceId | string | Unique identifier for the device in the service |
| DeviceName | string | Fully qualified domain name (FQDN) of the device |
| OSArchitecture | string | Architecture of the operating system running on the machine |
| OSPlatform | string | Platform of the operating system running on the device. This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7 |
| OSVersion | string | Version of the operating system running on the machine |
| RecommendedSecurityUpdate | string | Name or description of the security update provided by the software vendor to address the vulnerability |
| RecommendedSecurityUpdateId | string | Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles |
| SoftwareName | string | Name of the software product |
| SoftwareVendor | string | Name of the software vendor |
| SoftwareVersion | string | Version number of the software product |
| SourceSystem | string |  |
| TenantId | string |  |
| TimeGenerated | datetime | Date and time when the record was generated |
| Type | string | The name of the table |
| VulnerabilitySeverityLevel | string | Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape |

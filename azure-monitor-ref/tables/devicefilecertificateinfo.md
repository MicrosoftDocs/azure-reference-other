---
title: Azure Monitor Logs reference - DeviceFileCertificateInfo
description: Reference for DeviceFileCertificateInfo table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# DeviceFileCertificateInfo

 Certificate information of signed files obtained from certificate verification events on endpoints.

## Categories

- Security
## Solutions

- Microsoft Sentinel




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CertificateCountersignatureTime | datetime | Date and time (UTC) the certificate was countersigned. |
| CertificateCreationTime | datetime | Date and time (UTC) the certificate was created. |
| CertificateExpirationTime | datetime | Certificate expiry date and time (UTC). |
| CertificateSerialNumber | string | Identifier for the certificate that is unique to the issuing certificate authority (CA). |
| CrlDistributionPointUrls | string | A list of network shares URLs that contains certificates and certificate revocation (CRLs). |
| DeviceId | string | Unique identifier for the device in the service. |
| DeviceName | string | Fully qualified domain name (FQDN) of the device. |
| IsRootSignerMicrosoft | bool | Indicates whether the signer of the root certificate is Microsoft. |
| IsSigned | bool | Indicates whether the file is signed. |
| Issuer | string | Information about the issuing certificate authority (CA). |
| IssuerHash | string | Unique hash value identifying issuing certificate authority (CA). |
| IsTrusted | bool | Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes. |
| MachineGroup | string | Machine group of the machine. This group is used by role-based access control to determine access to the machine. |
| ReportId | long | Unique identifier for the event. |
| SHA1 | string | SHA-1 hash of the file that the recorded action was applied to. |
| SignatureType | string | Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file. |
| Signer | string | Information about the signer of the file. |
| SignerHash | string | Unique hash value identifying the signer. |
| SourceSystem | string |  |
| TenantId | string |  |
| TimeGenerated | datetime | Date and time (UTC) when the record was generated. |
| Type | string | The name of the table |

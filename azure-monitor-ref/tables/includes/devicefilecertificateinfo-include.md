---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/22/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: DeviceFileCertificateInfo
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CertificateCountersignatureTime | datetime | Date and time (UTC) the certificate was countersigned. |
| CertificateCreationTime | datetime | Date and time (UTC) the certificate was created. |
| CertificateExpirationTime | datetime | Certificate expiry date and time (UTC). |
| CertificateSerialNumber | string | Identifier for the certificate that is unique to the issuing certificate authority (CA). |
| CrlDistributionPointUrls | string | A list of network shares URLs that contains certificates and certificate revocation (CRLs). |
| DeviceId | string | Unique identifier for the device in the service. |
| DeviceName | string | Fully qualified domain name (FQDN) of the device. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
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
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Date and time the event was recorded by the MDE agent on the endpoint. |
| Type | string | The name of the table |

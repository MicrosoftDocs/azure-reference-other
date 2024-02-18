---
title: Example log table queries for AzureAttestationDiagnostics
description:  Example queries for AzureAttestationDiagnostics log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AzureAttestationDiagnostics table


### Are there any authorization failures?  


Count of Attestation provider requests which failed authorization.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureAttestationDiagnostics
| where toint(ResultSignature) == 403
| summarize count() by ResourceUri, ResultSignature, _ResourceId
// ResultSignature contains HTTP status code returned by the request, (e.g.  200, 300, 401, etc.)
// ResourceUri contains the URI of the request
```



### Are there any slow requests?  


List of Attestation provider requests that took longer than 1 second.  

```query
// To create an alert for this query, click '+ New alert rule'
let threshold=1000; // let operator defines a constant that can be further used in the query
AzureAttestationDiagnostics
| where DurationMs > threshold
| summarize count() by OperationName, _ResourceId
```



### How active has this Attestation provider been?  


Line chart showing trend of Attestation provider requests volume, per operation over time.  

```query
AzureAttestationDiagnostics
| where TimeGenerated > ago(1d)
| summarize count() by bin(TimeGenerated, 1h), OperationName // Aggregate by hour
| render timechart
```



### Who is calling this attestation provider?  


List of callers identified by their IP address and AAD UPN with their request count.  

```query
AzureAttestationDiagnostics
| summarize count() by CallerIpAddress, tostring(Identity.callerAadUPN)
```



### Have there been any changes to attestation policy?  


List of successful Attestation provider requests to change the attestation policy or policy signing certificates.  

```query
// To create an alert for this query, click '+ New alert rule'
let policyOperations = pack_array(
    "AddPolicyCertificate",
    "AddPolicyManagementCertificate",
    "AddPolicyManagementCertificates",
    "RemovePolicyCertificate",
    "RemovePolicyManagementCertificate",
    "RemovePolicyManagementCertificates",
    "ResetAttestationPolicy",
    "SetCurrentPolicy",
    "SetCurrentPolicyWithHttpMessagesAsync",
    "SetEffectiveAttestationPolicy",
    "DeleteCurrentPolicy",
    "DeletePolicy"
);
AzureAttestationDiagnostics
| where toint(ResultSignature) == 200
| where policyOperations contains OperationName
| take 100
```



### Have there been any errors attempting to configure the attestation policy?  


List of any errors attempting to configure the attestation policy or policy signing certificates.  

```query
// To create an alert for this query, click '+ New alert rule'
let policyOperations = pack_array(
    "AddPolicyCertificate",
    "AddPolicyManagementCertificate",
    "AddPolicyManagementCertificates",
    "PrepareToSetPolicy",
    "PrepareToUpdatePolicy",
    "RemovePolicyCertificate",
    "RemovePolicyManagementCertificate",
    "RemovePolicyManagementCertificates",
    "ResetAttestationPolicy",
    "SetCurrentPolicy",
    "SetCurrentPolicyWithHttpMessagesAsync",
    "SetEffectiveAttestationPolicy",
    "DeleteCurrentPolicy",
    "DeletePolicy"
);
AzureAttestationDiagnostics
| where toint(ResultSignature) >= 300
| where policyOperations contains OperationName
| take 100
```


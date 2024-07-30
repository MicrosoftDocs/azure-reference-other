---
title: Azure Monitor Logs reference - AADDomainServicesDNSAuditsGeneral
description: Reference for AADDomainServicesDNSAuditsGeneral table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# AADDomainServicesDNSAuditsGeneral

DNS server audit events enable change tracking on the DNS server. An audit event is logged each time server, zone, or resource record settings are changed. This includes operational events such as zone transfers, and DNSSEC zone signing and unsigning.  This table captures audit events that are not from dynamic updates.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.aad/domainservices|
|**Categories**|-|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|-|



## Columns
  
[!INCLUDE [aaddomainservicesdnsauditsgeneral](./includes/aaddomainservicesdnsauditsgeneral-include.md)]

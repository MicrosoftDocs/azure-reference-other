---
title: Example log table queries for AOIStorage
description:  Example queries for AOIStorage log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AOIStorage table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Ingestion operation on storage  


Lists all the ingestion operation performed on storage of a dataproduct.  

```query
AOIStorage
| where Category has_cs "Ingestion"
| take 100
```



### Delete operation on storage  


Lists all delete operation performed on storage of a dataproduct.  

```query
AOIStorage
| where Category has_cs "IngestionDelete"
| take 100
```



### Read operation on storage  


Lists all Read operation performed on storage of a dataproduct.  

```query
AOIStorage
| where Category has_cs "ReadStorage"
| take 100
```



### Read operation on input storage  


Lists all Read operation performed on the input storage of a dataproduct.  

```query
AOIStorage
| where Category has_cs "IngestionRead"
| take 100
```


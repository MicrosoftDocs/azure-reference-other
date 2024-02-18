---
title: Example log table queries for AOIStorage
description:  Example queries for AOIStorage log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AOIStorage table


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


---
title: Example log table queries for CloudAppEvents
description:  Example queries for CloudAppEvents log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the CloudAppEvents table


### File name extension change  


Display files that were renamed.  

```query
CloudAppEvents 
| where Application in ("Microsoft OneDrive for Business", "Microsoft SharePoint Online") and ActionType == "FileRenamed"
| extend NewFileNameExtension = tostring(RawEventData.DestinationFileExtension)
| extend OldFileNameExtension = tostring(RawEventData.SourceFileExtension)
| extend OldFileName = tostring(RawEventData.SourceFileName)
| extend NewFileName = tostring(RawEventData.DestinationFileName)
| where NewFileNameExtension == "doc" and OldFileNameExtension == "docx" 
| project RenameTime = Timestamp, OldFileNameExtension, OldFileName, NewFileNameExtension, NewFileName, ActionType, Application, AccountDisplayName, AccountObjectId
| join kind=inner (DeviceFileEvents 
| project FileName, AccountObjectId = InitiatingProcessAccountObjectId , DeviceName, SeenOnDevice = Timestamp, FolderPath) on $left.NewFileName == $right.FileName, AccountObjectId
| project RenameTime, NewFileName, OldFileName, Application, AccountObjectId, AccountDisplayName, DeviceName , SeenOnDevice, FolderPath 
| limit 100
```


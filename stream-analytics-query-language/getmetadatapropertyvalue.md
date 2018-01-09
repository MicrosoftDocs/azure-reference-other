---
title: "GetMetadataPropertyValue | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-01"
ms.reviewer: ""
ms.service: "stream-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 7fca3d2c-2475-49e8-8c16-e268b65def22
caps.latest.revision: 10
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# GetMetadataPropertyValue
  Queries input data for specific properties. There are three types of properties, Adapter, User, and Unique EventId Properties.
  
## Adapter metadata Properties
Certain input specific properties have been made accessible by GetMetadataPropertyValue function. Additionally, all properties can be accessed as a single record.

> [!NOTE]  
>  Please be aware when doing passthrough queries with GetMetadataPropertyValue as it produces two columns of metadata properties or records with the same value. Also, avoid column name collision with payload column name and metadata property name. This behavior discrepancies will be addressed in near future.
>
>For example, **`SELECT *, GetMetadataPropertyValue(input, 'User.foo') as foo FROM input`** may produce unintended results.


### Examples

To query from an Event Hub input;  
`select GetMetadataPropertyValue(ehInput, '[EventHub].[EventEnqueuedUtcTime]') as mytime from ehInput`

To query from an IoT Hub input;  
`select GetMetadataPropertyValue(iotInput, 'IoTHub.StreamId') as iotStreamId from iotInput`

To query all adapter related properties as a record;

For Event Hub:  
`select GetMetadataPropertyValue(ehInput, 'EventHub') as myEHPropertiesRecord from ehInput`

For IoT Hub:  
`select GetMetadataPropertyValue(iotInput, 'IoTHub') as iotRecord from iotInput`

For Blob input:  
`select GetMetadataPropertyValue(blobInput, 'Blob') as blobRecord from blobInput`

## User Properties
A custom user property called SenderClientId set on incoming EventHub/IoT/Blob messages will be accessible as shown below.

### Examples

To query from an Event Hub input;  
`select Name, GetMetadataPropertyValue(ehInput, '[User].[SenderClientId]') from ehInput`

To query from an IoT Hub input;  
`select Name, GetMetadataPropertyValue(iotInput, '[User].[SenderClientId]') from iotInput`

To query from a Blob input;  
`select Name, GetMetadataPropertyValue(blobInput, '[User].[SenderClientId]') from blobInput`

To get all user properties as a record;

For Event Hub:  
`select Name, GetMetadataPropertyValue(ehInput, '[User]') as userprops from ehInput`

For IoT Hub:  
`select Name, GetMetadataPropertyValue(iotInput, '[User]') as userprops from iotInput`

For Blob input:  
`select Name, GetMetadataPropertyValue(blobInput, '[User]') as userprops from blobInput`


## Unique EventId Property
Creates a unique id (Guid) for an input event, which can be useful for primary key purposes. It is consistent (not random) i.e., Stream Analytics will produce the same id for an event, if you go back in time and re-read the same input event.

### Example

```SQL
SELECT GetMetadataPropertyValue(ehInput, 'EventId') as eventPrimaryKey from ehInput
``` 


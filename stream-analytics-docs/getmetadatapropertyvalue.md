---
title: GetMetadataPropertyValue (Azure Stream Analytics) | Microsoft Docs
description: Queries input data for specific properties.
applies_to: 
  - "Azure"
services: stream-analytics
author: mamccrea
ms.author: mamccrea
ms.service: stream-analytics
ms.topic: reference
ms.assetid: 7fca3d2c-2475-49e8-8c16-e268b65def22
caps.latest.revision: 11
ms.workload: data-services
ms.date: 12/13/2019
---
# GetMetadataPropertyValue (Azure Stream Analytics)

Queries input data for specific properties. There are three types of properties: Adapter, User, and Unique EventId.
  
## Adapter metadata properties

Certain input-specific properties are accessible by the GetMetadataPropertyValue function. Additionally, all properties can be accessed as a single record. This function cannot be tested on the Azure portal using sample data. You can use Visual Studio tools for Stream Analytics to test this function in your query using [live data](https://docs.microsoft.com/azure/stream-analytics/stream-analytics-live-data-local-testing).

### Examples

To query from an Event Hub input,  
`SELECT GetMetadataPropertyValue(ehInput, '[EventHub].[EventEnqueuedUtcTime]') AS mytime FROM ehInput`
Other valid property names are EventProcessedUtcTime, PartitionId, Offset, SequenceNumber, PartitionKey.

To query from an IoT Hub input,  
`SELECT GetMetadataPropertyValue(iotInput, 'IoTHub.CorrelationId') AS iotCorrelationId FROM iotInput`
Other valid property names are MessageId, ConnectionDeviceId, ConnectionDeviceGenerationId, EnqueuedTime.

To query from Event Hub with IoT Routing enabled,  
`SELECT GetMetadataPropertyValue(ehInput, '[EventHub].[IoTConnectionDeviceId]') AS myIoTDeviceId FROM ehInput`

To query *all possible* adapter-related properties as a record,

For Event Hub:  
`SELECT GetMetadataPropertyValue(ehInput, 'EventHub') AS myEHPropertiesRecord FROM ehInput`

For IoT Hub:  
`SELECT GetMetadataPropertyValue(iotInput, 'IoTHub') AS iotRecord FROM iotInput`

For Blob input:  
`SELECT GetMetadataPropertyValue(blobInput, 'Blob') AS blobRecord FROM blobInput`

## User properties

A custom user property called SenderClientId set on incoming EventHub/IoT/Blob messages is made accessible using GetMetadataPropertyValue, as shown below.

### Examples

To query from an Event Hub input,  
`SELECT Name, GetMetadataPropertyValue(ehInput, '[User].[SenderClientId]') FROM ehInput`

To query from an IoT Hub input,  
`SELECT Name, GetMetadataPropertyValue(iotInput, '[User].[SenderClientId]') FROM iotInput`

To query from a Blob input,  
`SELECT Name, GetMetadataPropertyValue(blobInput, '[User].[SenderClientId]') FROM blobInput`

To get all user properties as a record,

For Event Hub:  
`SELECT Name, GetMetadataPropertyValue(ehInput, '[User]') AS userprops FROM ehInput`

For IoT Hub:  
`SELECT Name, GetMetadataPropertyValue(iotInput, '[User]') AS userprops FROM iotInput`

For Blob input:  
`SELECT Name, GetMetadataPropertyValue(blobInput, '[User]') AS userprops FROM blobInput`


## Unique EventId property

The EventId property creates a unique ID (Guid) for an input event, which can be useful for primary key purposes. EventId is consistent (not random); if you go back in time and re-read the same input event, Stream Analytics will produce the same ID.

### Example

```SQL
SELECT GetMetadataPropertyValue(ehInput, 'EventId') AS eventPrimaryKey FROM ehInput
```

## Limitations and Restrictions

GetMetadataPropertyValue has the following limitations of usage:

* Using `SELECT *` in your query causes duplicate columns. To prevent duplicate columns, list columns individually in your SELECT statement.

* The alias you give your Metadata Property Value will be lowercase regardless of the casing used in your query. For example, `SELECT GetMetadataPropertyValue(ehInput, 'EventId') AS eventPrimaryKey` outputs as `eventprimarykey`. To preserve casing, use compatibility level 1.2.

* This function doesn't work in the Azure portal preview results pane or in Visual Studio or VS Code local query testing. It works only when the job is running in the public cloud.

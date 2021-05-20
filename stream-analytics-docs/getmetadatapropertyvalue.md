---
title: GetMetadataPropertyValue (Azure Stream Analytics)
description: Queries input data for specific properties.
applies_to: 
  - "Azure"
ms.service: stream-analytics
ms.topic: reference
ms.date: 7/24/2020
---
# GetMetadataPropertyValue (Azure Stream Analytics)

Queries input data for specific properties. There are three types of properties: Adapter, User, and Unique EventId.
  
## Adapter metadata properties

Certain input-specific properties are accessible by the GetMetadataPropertyValue function. Additionally, all properties can be accessed as a single record. 

> [!NOTE]
> At this time,this function cannot be tested on the Azure portal (it will return empty results). You can use Visual Studio tools for Stream Analytics to test this function in your query using [live data](/azure/stream-analytics/stream-analytics-live-data-local-testing).

##  Default metadata properties for Event Hubs
* EventEnqueuedUtcTime
* EventProcessedUtcTime
* PartitionId
* Offset
* SequenceNumber
* PartitionKey
* Publisher, when available in the incoming event

### Examples:
#### Retrieve EventEnqueuedUtcTime from Event Hubs:
`SELECT GetMetadataPropertyValue(ehInput, '[EventHub].[EventEnqueuedUtcTime]') AS mytime FROM ehInput`

#### To query *all possible* adapter-related properties as a record:
`SELECT GetMetadataPropertyValue(ehInput, 'EventHub') AS myEHPropertiesRecord FROM ehInput`

### IoT Hub properties when routed to Event Hubs endpoints
When using IoT Hub routing feature to Event Hubs endpoints, metadata properties will be available by reading properties from  Event Hubs. In this case the following properties that can be retrieved:
* IoTConnectionDeviceId
* IoTAuthMethod
* IoTAuthGenerationId
* IoTEnqueueTime
* IoTMessageSource
* IoTConnectionModuleId
* IoTInterfaceName

Example:
`SELECT GetMetadataPropertyValue(ehInput, '[EventHub].[IoTConnectionDeviceId]') AS myIoTDeviceId FROM ehInput`

## Default metadata properties for IoT Hub
* ConnectionDeviceId
* AuthMethod
* AuthGenerationId 
* EnqueueTime
* MessageSource
* ConnectionModuleId
* InterfaceName
* CorrelationId
* MessageId

* ConnectionDeviceGenerationId

### Examples:
#### Retrieve EnqueuedTime from IoT Hub:
`SELECT GetMetadataPropertyValue(iotInput, 'IoTHub.EnqueuedTime') AS myEnqueuedTime FROM iotInput`
#### To query *all possible* adapter-related properties as a record:
`SELECT GetMetadataPropertyValue(iotInput, 'IoTHub') AS iotRecord FROM iotInput`


## Default metadata properties for Blob input:  
* BlobName
* BlobLastModifiedUtcTime
* PartitionId

Example
`SELECT GetMetadataPropertyValue(blobInput, 'BlobName') AS myBlobName FROM blobInput`

## User properties

A custom user property called SenderClientId set on incoming EventHub/IoT/Blob messages is made accessible using GetMetadataPropertyValue, as shown in the example below.

Additionally, twin properties and enriched properties added using [IoT Hub message enrichment](/azure/iot-hub/iot-hub-message-enrichments-overview), can also be retrieved using GetMetadataPropertyValue.

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

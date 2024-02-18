---
title: Example log table queries for ACSCallClientMediaStatsTimeSeries
description:  Example queries for ACSCallClientMediaStatsTimeSeries log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ACSCallClientMediaStatsTimeSeries table


### Metrics per each media type  


List all the media metrics included in the ACSCallClientMediaStatsTimeSeries log for each media stream type.  

```query
ACSCallClientMediaStatsTimeSeries
| distinct MetricName, MediaStreamType
```



### Metric histogram per media type and direction  


Plot the histogram of selected metric, per callId, participantId, media type and meida direction  

```query
let PlotMetricHistogram = (_MetricName: string, _ParticipantId: string = '', _CallId: string = '', _MediaStreamType: string = '', _MediaStreamDirection: string = '') {
    // _MetricName: the name of the metric. This must be set.
    // _ParticipantId: set this variable if want to just plot the metric value histogram for a specific partiticpant.
    // _CallId: set this variable if want to just plot the metric value histogram for a specific call.
    // _MediaStreamType: possible values can be: 'audio', 'video', 'screen'.
    // _MediaStreamDirection: possible values can be: 'recv', 'send'.
    ACSCallClientMediaStatsTimeSeries
    | where MetricName == _MetricName
    | where isempty(_ParticipantId) or ParticipantId == _ParticipantId
    | where isempty(_CallId) or CallId == _CallId
    | where isempty(_MediaStreamType) or MediaStreamType == _MediaStreamType
    | where isempty(_MediaStreamDirection) or MediaStreamDirection == _MediaStreamDirection
    | summarize count=count() by Average
    | render columnchart title=strcat(_MetricName, " Histogram")
};
// Below plots the histogram for jitter for all outbound audio streams
PlotMetricHistogram('JitterInMs', _MediaStreamType='audio', _MediaStreamDirection='send')
```


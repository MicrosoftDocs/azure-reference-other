---
title: Example log table queries for ACSCallDiagnostics
description:  Example queries for ACSCallDiagnostics log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ACSCallDiagnostics table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Streams per call  


Calculates the average number of streams per call.  

```query
ACSCallDiagnostics
// Count the streams and distinct calls
| summarize num_streams=count(), num_calls=dcount(CorrelationId)
// Calculate the average number of streams per call
| extend avg_streams = toreal(num_streams) / toreal(num_calls)
```



### Streams per call histogram  


Produces a histogram of number of streams per call.  

```query
ACSCallDiagnostics
// Counts the number of streams per call 
| summarize streams_per_call=count() by CorrelationId
// Aggregates the numbers of streams per call (e.g. if there are 7 calls that have 6 streams,
// this will produce a row [streams_per_call=6, stream_counts=7])
| summarize stream_counts=count() by streams_per_call
| order by streams_per_call asc
| render columnchart title="Streams per call histogram"
```



### Media type ratio  


Produces a pie chart of the proportion of streams of a particular media types.  

```query
ACSCallDiagnostics
// Count the number of streams per media type
| summarize media_types=count() by MediaType
| render piechart title="Media Type Ratio"
```



### Transport type ratio  


Produces a pie chart of the proportion of streams using a particular transport types.  

```query
ACSCallDiagnostics
// Count the number of streams per transport type
| summarize transport_types=count() by TransportType
| render piechart title="Transport Type Ratio"
```



### Average telemetry values  


Calculates the average values for the six telemetry fields.  

```query
ACSCallDiagnostics
// Calculate the average value for each of the six telemetry fields
| summarize Avg_JitterAvg=avg(JitterAvg),
            Avg_JitterMax=avg(JitterMax),
            Avg_RoundTripTimeAvg=avg(RoundTripTimeAvg),
            Avg_RoundTripTimeMax=avg(RoundTripTimeMax),
            Avg_PacketLossRateAvg=avg(PacketLossRateAvg),
            Avg_PacketLossRateMax=avg(PacketLossRateMax)
```



### Jitter average histogram  


Produces a histogram of average jitter per stream.  

```query
ACSCallDiagnostics
// Filter null values
| where isnotnull(JitterAvg)
// Count jitter values by 10 millisecond intervals
| summarize JitterAvg_counts=count() by bin(JitterAvg, 10)
| order by JitterAvg asc
| render columnchart with (xcolumn = JitterAvg, title="JitterAvg histogram")
```



### Jitter max histogram  


Produces a histogram of max jitter per stream.  

```query
ACSCallDiagnostics
// Filter null values
| where isnotnull(JitterMax)
// Count jitter values by 10 millisecond intervals
|summarize JitterMax_counts=count() by JitterMax
| order by JitterMax asc
| render columnchart with (xcolumn = JitterMax, title="JitterMax histogram")
```



### Packet loss rate average histogram  


Produces a histogram of average packet loss rate per stream.  

```query
ACSCallDiagnostics
// Filter null values
| where isnotnull(PacketLossRateAvg)
// Count packet loss rate values within an inverval of 0.01 (1%)
| summarize PacketLossRateAvg_counts=count() by bin(PacketLossRateAvg, 0.01)
| order by PacketLossRateAvg asc
| render columnchart with (xcolumn = PacketLossRateAvg, title="PacketLossRateAvg histogram")
```



### Packet loss rate max histogram  


Produces a histogram of max packet loss rate per stream.  

```query
ACSCallDiagnostics
// Filter null values
| where isnotnull(PacketLossRateMax)
// Count packet loss rate values within an inverval of 0.01 (1%)
|summarize PacketLossRateMax_counts=count() by bin(PacketLossRateMax, 0.01)
| order by PacketLossRateMax asc
| render columnchart with (xcolumn = PacketLossRateMax, title="PacketLossRateMax histogram")
```



### Round trip time average histogram  


Produces a histogram of average round trip time per stream.  

```query
// RoundTripTime Average Histogram
ACSCallDiagnostics
// Filter null values
| where isnotnull(RoundTripTimeAvg)
// Count round trip time values by 10 millisecond intervals
|summarize RoundTripTimeAvg_counts=count() by bin(RoundTripTimeAvg, 10)
| order by RoundTripTimeAvg asc
| render columnchart with (xcolumn = RoundTripTimeAvg, title="RoundTripTimeAvg histogram")
```



### Round trip time max histogram  


Produces a histogram of max round trip time per stream.  

```query
ACSCallDiagnostics
// Filter null values
| where isnotnull(RoundTripTimeMax)
// Count round trip time values by 10 millisecond intervals
|summarize RoundTripTimeMax_counts=count() by bin(RoundTripTimeMax, 10)
| order by RoundTripTimeMax asc
| render columnchart with (xcolumn = RoundTripTimeMax, title="RoundTripTimeMax histogram")
```



### Jitter quality ratio  


Produces a pie chart of the proportion of streams with good or poor jitter quality.  

```query
ACSCallDiagnostics
// Classify the jitter quality as Poor or Good based on
// whether the average jitter is higher than 30 milliseconds
| project JitterQuality = iff(JitterAvg > 30, "Poor", "Good")
// Counts the number of streams per jitter quality
| summarize count() by JitterQuality
| render piechart title="Jitter Quality"
```



### Packet loss rate quality ratio  


Produces a pie chart of the proportion of streams with good or poor packet loss rate quality.  

```query
ACSCallDiagnostics
// Classify packet loss rate quality as Poor or Good based on
// whether the average packet loss rate is higher than 10%
| project PacketLossRateQuality = iff(PacketLossRateAvg > 0.1, "Poor", "Good")
// Count the number of streams per packet loss rate quality
| summarize count() by PacketLossRateQuality
| render piechart title="Packet Loss Rate Quality"
```



### Round trip time quality ratio  


Produces a pie chart of the proportion of streams with good or poor round trip time quality.  

```query
ACSCallDiagnostics
// Classifying the round trip time quality as Poor or Good based on
// whether the average round trip time is higher than 500 milliseconds
| project RoundTripTimeQuality = iff(RoundTripTimeAvg > 500, "Poor", "Good")
// Count the number of streams per round trip time quality
| summarize count() by RoundTripTimeQuality
| render piechart title="Round Trip Time Quality"
```



### CallDiagnostics log for CallAutomation API call  


Queries the diagnostics log for a call which was interacted with by Call Automation API using correlation ID.  

```query
ACSCallAutomationIncomingOperations 
//| where CorrelationId == "<correlation ID>" // This can be uncommented to filter on a specific correlation ID
| join kind=inner
    (ACSCallDiagnostics)
    on CorrelationId
| limit 100

```



### Search calls by keyword  


List all calls found that contains the keyword, and returns the details of the call including rating, quality, issues breakdown etc. This query is also used in Call Diagnostics to search for calls.  

```query
// Set queryConditions_keyword to be the searching keyword. It can be CallId, ParticipantId, 
// Identifier or any other column values in ACSCallSummary log. If not set, the query will return all calls.
// Note this query is also used to provide the data in Call Diagnostics.
declare query_parameters(queryConditions_keyword:string = '',
                        queryConditions_startTime:string = '',
                        queryConditions_endTime:string = '');
let callIds = 
materialize(ACSCallSummary
| where isempty(queryConditions_startTime) or CallStartTime >= todatetime(queryConditions_startTime)
| extend CallEndTime = CallStartTime + totimespan(strcat(tostring(CallDuration), 's'))
| where isempty(queryConditions_endTime) or CallEndTime <= todatetime(queryConditions_endTime)
| where isempty(queryConditions_keyword) or * contains queryConditions_keyword
| distinct CorrelationId, ParticipantId);
let searchedCalls = 
materialize(ACSCallSummary
| where CorrelationId in ((callIds | project CorrelationId))
| extend CallEndTime = CallStartTime + totimespan(strcat(tostring(CallDuration), 's'))
| where CorrelationId != ParticipantId
| extend ParticipantId = coalesce(ParticipantId, Identifier, EndpointId)
| extend ParticipantId = iff(ParticipantId == 'Redacted', strcat('RedactedParticipant-', EndpointType, '-Identifier-', Identifier), ParticipantId)
| extend EndpointId = iff(EndpointId == 'Redacted', strcat('RedactedEndpoint-', EndpointType, '-Identifier-', Identifier), EndpointId)
| summarize hint.strategy = shuffle CallStartTime = take_any(CallStartTime), CallEndTime = take_any(CallEndTime), CallType = take_any(CallType),
numOfDroppedParticipant = count_distinctif(ParticipantId, ParticipantEndReason in ('380', '400', '407', '408', '409', '410', 
'412', '417', '430', '439', '440', '481', '483', '488', '489', '493', '500', '502', '503', '504', '580')) by CorrelationId);
// client type
let allParticipants = materialize(ACSCallSummary
| where CorrelationId != ParticipantId
| extend ParticipantId = coalesce(ParticipantId, Identifier, EndpointId)
| extend ParticipantId = iff(ParticipantId == 'Redacted', strcat('RedactedParticipant-', EndpointType, '-Identifier-', Identifier), ParticipantId)
| extend EndpointId = iff(EndpointId == 'Redacted', strcat('RedactedEndpoint-', EndpointType, '-Identifier-', Identifier), EndpointId)
| where CorrelationId in ((callIds | project CorrelationId))
| union (ACSCallClientOperations
| where CallId in ((callIds | project CorrelationId))
| where isnotempty(ParticipantId)
| distinct ParticipantId, CorrelationId = CallId, EndpointType = 'VoIP')
| summarize hint.strategy = shuffle take_any(EndpointType) by ParticipantId, CorrelationId);
let clientTypeInfo = materialize(allParticipants
| summarize hint.strategy = shuffle count() by EndpointType, CorrelationId
| extend info = strcat(count_, ' ', EndpointType) 
| summarize hint.strategy = shuffle summaryInfo = make_list(info, 100) by CorrelationId 
| extend ClientType = strcat_array(summaryInfo, ', ')
| project CorrelationId, ClientType);
let totalNumOfParticipants = materialize(allParticipants | summarize hint.strategy = shuffle participantsCount = dcount(ParticipantId) by CorrelationId);
// quality
let qualityInfo = materialize(ACSCallDiagnostics
| where CorrelationId in ((callIds | project CorrelationId))
| where CorrelationId != ParticipantId
| extend ParticipantId = coalesce(ParticipantId, Identifier, EndpointId)
| extend ParticipantId = iff(ParticipantId == 'Redacted', strcat('RedactedParticipant-', EndpointType, '-Identifier-', Identifier), ParticipantId)
| extend EndpointId = iff(EndpointId == 'Redacted', strcat('RedactedEndpoint-', EndpointType, '-Identifier-', Identifier), EndpointId)
| where isnotempty(StreamId)
| summarize hint.strategy = shuffle arg_max(TimeGenerated, *) by ParticipantId, StreamId
| extend 
    MediaType = iff(MediaType == 'VBSS', 'ScreenSharing', MediaType) | extend
    __JitterQuality         = iff(JitterAvg > 30, "Poor", "Good"),
    __JitterBufferQuality = iff(JitterBufferSizeAvg > 200, "Poor", "Good"),
    __PacketLossRateQuality = iff(PacketLossRateAvg > 0.1, "Poor", "Good"),
    __RoundTripTimeQuality  = iff(RoundTripTimeAvg > 500, "Poor", "Good"),
    __HealedDataRatioQuality = iff(HealedDataRatioAvg > 0.1, "Poor", "Good"),
    __VideoFrameRateQuality = iff((VideoFrameRateAvg < 1 and MediaType == 'ScreenSharing') or 
    (VideoFrameRateAvg < 7 and MediaType == 'Video'), "Poor", "Good"),
    __FreezesQuality = iff((RecvFreezeDurationPerMinuteInMs > 25000 and MediaType == 'ScreenSharing') or 
    (RecvFreezeDurationPerMinuteInMs > 6000 and MediaType == 'Video'), "Poor", "Good"),
    __VideoResolutionHeightQuality = iff((RecvResolutionHeight < 768 and MediaType == 'ScreenSharing') or 
    (RecvResolutionHeight < 240 and MediaType == 'Video'), "Poor", "Good")
| extend
    __StreamQuality = iff(
    (__JitterQuality == "Poor") 
    or (__JitterBufferQuality == "Poor")
    or (__PacketLossRateQuality == "Poor") 
    or (__RoundTripTimeQuality == "Poor") 
    or (__HealedDataRatioQuality == "Poor")
    or (__VideoFrameRateQuality == "Poor")
    or (__FreezesQuality == "Poor")
    or (__VideoResolutionHeightQuality == "Poor"), 
    "Poor", "Good"),
    MediaDirection = iff(EndpointType == 'Server', 'InboundStream', 'OutboundStream')
| summarize hint.strategy = shuffle numOfPoorStreams = countif(__StreamQuality == 'Poor') by CorrelationId
| extend Quality = iff(numOfPoorStreams >0, 'Poor', 'Good') | project Quality, numOfPoorStreams, CorrelationId);
// rating
let ratingInfo = materialize(ACSCallSurvey
| where CallId in ((callIds | project CorrelationId))
| extend OverallRatingScoreUpperBound = iff(isnotempty(OverallRatingScoreUpperBound), OverallRatingScoreUpperBound, 5)
| summarize hint.strategy = shuffle Rating = avg(OverallRatingScore*5.0/OverallRatingScoreUpperBound) by CallId
| project CorrelationId=CallId, Rating);
// client operation issues
let rangeEventsWithCorrelation = dynamic(['UserFacingDiagnostics']);
let pointEvents = dynamic([
'SelectedMicrophoneChanged', 'SelectedSpeakerChanged', 'OptimalVideoCount-changed', 'State-changed', 'CallMode-changed',
'IsMuted-changed', 'IsIncomingAudioMuted-changed', 'Id-changed', 'Role-changed', 'SelectedDevice-changed', 'PageHidden',
'optimalVideoCount-changed', 'state-changed', 'callMode-changed', 'isMuted-changed', 'isIncomingAudioMuted-changed', 
'id-changed', 'role-changed', 'selectedDevice-changed', 'pageHidden']);
// We need clientIds to get all operations before call is established.
let callClientIds = materialize(ACSCallClientOperations
| where ParticipantId in ((callIds | project ParticipantId)) or CallId in ((callIds | project CorrelationId))
| distinct ClientInstanceId, ParticipantId, CallId);
//
let allOperations =
materialize(callClientIds | join kind=rightouter hint.strategy=shuffle
(ACSCallClientOperations
| where isempty(queryConditions_startTime) or CallClientTimeStamp >= (todatetime(queryConditions_startTime) - 2h)
| where ParticipantId in ((callIds | project ParticipantId)) or CallId in ((callIds | project CorrelationId)) or ClientInstanceId in ((callClientIds | project ClientInstanceId)) 
| where isnotempty(OperationName) and OperationName != 'CallClientOperations'
and isnotempty(OperationId) and isnotempty(CallClientTimeStamp))
on ClientInstanceId
| extend ParticipantId = coalesce(ParticipantId, ParticipantId1), CallId = coalesce(CallId, CallId1)
| project-away ParticipantId1, ClientInstanceId1, CallId1
| summarize hint.strategy = shuffle arg_max(TimeGenerated, *) by OperationId, CallClientTimeStamp);
//
let correlatedOperations = materialize(allOperations
| where OperationName in (rangeEventsWithCorrelation)
| extend OperationPayload = todynamic(OperationPayload)
| extend 
    UFDQuality = tostring(OperationPayload.DiagnosticQuality),
    UFDType = tostring(OperationPayload.DiagnosticChanged)
| extend UFDType = strcat(toupper(substring(UFDType, 0, 1)),substring(UFDType, 1))
| extend OperationPayloadNew = bag_pack(tostring(CallClientTimeStamp), OperationPayload)
| project-away ResultType
| summarize hint.strategy = shuffle
    arg_max(TimeGenerated, *), ResultType = iff(countif(UFDQuality != 'Good')>0, 'Failed', 'Succeeded'), 
    OperationStartTime = min(CallClientTimeStamp), OperationEndTime = max(CallClientTimeStamp),
    OperationPayloadPacked = make_bag(OperationPayloadNew) by OperationId, UFDType, CallId
| extend ResultType = iff(UFDType has_any ("SpeakingWhileMicrophoneIsMuted", "SpeakerMuted"), 'Succeeded', ResultType), OperationName = UFDType
| where ResultType !in ('Succeeded', 'Success', 'ExpectedError'));
//
let nonCorrelatedOperations = materialize(allOperations
| where OperationName !in (rangeEventsWithCorrelation)
| extend OperationId = coalesce(hash_sha256(strcat(OperationId, tostring(CallClientTimeStamp))), tostring(new_guid()))
| summarize hint.strategy = shuffle arg_max(TimeGenerated, *) by OperationId, CallId
| where ResultType !in ('Succeeded', 'Success', 'ExpectedError'));
let clientOperationIssues = 
materialize(union nonCorrelatedOperations, correlatedOperations
| summarize hint.strategy = shuffle numOfBadOperations=count() by OperationName, CallId
| extend badClientOperations = bag_pack(OperationName, numOfBadOperations)
| summarize hint.strategy = shuffle badClientOperations = make_bag(badClientOperations), numOfBadOperations = sum(numOfBadOperations) by CorrelationId=CallId);
////
searchedCalls 
| join kind=leftouter hint.strategy=shuffle clientTypeInfo on CorrelationId
| join kind=leftouter hint.strategy=shuffle qualityInfo on CorrelationId
| join kind=leftouter hint.strategy=shuffle ratingInfo on CorrelationId
| join kind=leftouter hint.strategy=shuffle clientOperationIssues on CorrelationId
| join kind=leftouter hint.strategy=shuffle totalNumOfParticipants on CorrelationId
| extend numOfPoorStreams = coalesce(numOfPoorStreams, 0)
| extend
    drops=bag_pack('Call Ended Ungracefully',numOfDroppedParticipant),
    badMediaStreams = bag_pack('Poor Media Streams', numOfPoorStreams),
    Issues = coalesce(numOfBadOperations, 0) + numOfDroppedParticipant + numOfPoorStreams
| extend
    IssuesBreakdown=bag_merge(drops, badClientOperations, badMediaStreams)
| project 
    CallId=CorrelationId, CallStartTime, CallEndTime, CallType, 
    Participants=participantsCount, ClientType, 
    Quality=iff(isempty(Quality), 'Unknown', Quality), 
    Rating=case(isempty(Rating), 'Unknown', Rating>=4.5, 'Good', Rating >=3, 'Average', 'Poor'),
    NumOfDroppedParticipant = numOfDroppedParticipant,
    NumOfPoorStreams = numOfPoorStreams,
    Issues, IssuesBreakdown
| order by CallStartTime desc
```



### Search all participants in a call  


Find all participants in a call by callId, and return the details of the participants.This query is also used in Call Diagnostics to search for participants.  

```query
// Set queryConditions_callId to be the CallId you want to query.
// Note this query is used in Call Diagnostics to get all the participant entities of a call.
declare query_parameters(queryConditions_callId:string = '');
let participants = materialize(ACSCallSummary
| where CorrelationId == queryConditions_callId
| where ParticipantId != CorrelationId and isnotempty(ParticipantId)
| distinct ParticipantId, CallType);
let serviceSideParticipants = materialize(ACSCallSummary
| where CorrelationId == queryConditions_callId
// some participants don't have startTime, we use callStartTime instead.
| extend ParticipantStartTime = coalesce(ParticipantStartTime, CallStartTime)
| extend ParticipantEndTime = coalesce(ParticipantStartTime + 1s*ParticipantDuration, ParticipantStartTime + 10ms)
| extend EndReason=case(
    ParticipantEndReason == "0", "Success",
    ParticipantEndReason == "100","Trying",
    ParticipantEndReason == "180","Ringing",
    ParticipantEndReason == "181","Call Is Being Forwarded",
    ParticipantEndReason == "182","Queued",
    ParticipantEndReason == "183","Session Progress",
    ParticipantEndReason == "199","Early Dialog Terminated",
    ParticipantEndReason == "200","Success",
    ParticipantEndReason == "202","Accepted",
    ParticipantEndReason == "204","No Notification",
    ParticipantEndReason == "300","Multiple Choices",
    ParticipantEndReason == "301","Moved Permanently",
    ParticipantEndReason == "302","Moved Temporarily",
    ParticipantEndReason == "305","Use Proxy",
    ParticipantEndReason == "380","Alternative Service",
    ParticipantEndReason == "400","Bad Request",
    ParticipantEndReason == "401","Unauthorized",
    ParticipantEndReason == "402","Payment Required",
    ParticipantEndReason == "403","Forbidden / Authentication failure",
    ParticipantEndReason == "404","Call not found",
    ParticipantEndReason == "405","Method Not Allowed",
    ParticipantEndReason == "406","Not Acceptable",
    ParticipantEndReason == "407","Proxy Authentication Required",
    ParticipantEndReason == "408","Call controller timed out",
    ParticipantEndReason == "409","Conflict",
    ParticipantEndReason == "410","Local media stack or media infrastructure error",
    ParticipantEndReason == "411","Length Required",
    ParticipantEndReason == "412","Conditional Request Failed",
    ParticipantEndReason == "413","Request Entity Too Large",
    ParticipantEndReason == "414","Request-URI Too Large",
    ParticipantEndReason == "415","Unsupported Media Type",
    ParticipantEndReason == "416","Unsupported URI Scheme",
    ParticipantEndReason == "417","Unknown Resource-Priority",
    ParticipantEndReason == "420","Bad Extension",
    ParticipantEndReason == "421","Extension Required",
    ParticipantEndReason == "422","Session Interval Too Small",
    ParticipantEndReason == "423","Interval Too Brief",
    ParticipantEndReason == "424","Bad Location Information",
    ParticipantEndReason == "428","Use Identity Header",
    ParticipantEndReason == "429","Provide Referrer Identity",
    ParticipantEndReason == "430","Unable to deliver message to client application",
    ParticipantEndReason == "433","Anonymity Disallowed",
    ParticipantEndReason == "436","Bad Identity-Info",
    ParticipantEndReason == "437","Unsupported Certificate",
    ParticipantEndReason == "438","Invalid Identity Header",
    ParticipantEndReason == "439","First Hop Lacks Outbound Support",
    ParticipantEndReason == "440","Max-Breadth Exceeded",
    ParticipantEndReason == "469","Bad Info Package",
    ParticipantEndReason == "470","Consent Needed",
    ParticipantEndReason == "480","Remote client endpoint not registered",
    ParticipantEndReason == "481","Failed to handle incoming call",
    ParticipantEndReason == "482","Loop Detected",
    ParticipantEndReason == "483","Too Many Hops",
    ParticipantEndReason == "484","Address Incomplete",
    ParticipantEndReason == "485","Ambiguous",
    ParticipantEndReason == "486","Busy Here",
    ParticipantEndReason == "487","Call canceled, locally declined, ended due to an endpoint mismatch issue, or failed to generate media offer",
    ParticipantEndReason == "488","Not Acceptable Here",
    ParticipantEndReason == "489","Bad Event",
    ParticipantEndReason == "490","Local endpoint network issues",
    ParticipantEndReason == "491","Local endpoint network issues",
    ParticipantEndReason == "493","Undecipherable",
    ParticipantEndReason == "494","Security Agreement Required",
    ParticipantEndReason == "496","Local endpoint network issues",
    ParticipantEndReason == "497","Local endpoint network issues",
    ParticipantEndReason == "498","Local endpoint network issues",
    ParticipantEndReason == "500","Communication Services infrastructure error",
    ParticipantEndReason == "501","Not Implemented",
    ParticipantEndReason == "502","Bad Gateway",
    ParticipantEndReason == "503","Communication Services infrastructure error",
    ParticipantEndReason == "504","Communication Services infrastructure error",
    ParticipantEndReason == "505","Version Not Supported",
    ParticipantEndReason == "513","Message Too Large",
    ParticipantEndReason == "555","Push Notification Service Not Supported",
    ParticipantEndReason == "580","Precondition Failure",
    ParticipantEndReason == "600","Busy Everywhere",
    ParticipantEndReason == "603","Call globally declined by remote Communication Services participant",
    ParticipantEndReason == "604","Does Not Exist Anywhere",
    ParticipantEndReason == "606","Not Acceptable",
    ParticipantEndReason == "607","Unwanted",
    ParticipantEndReason == "608","Rejected", "")
| extend Rank = iff(isempty(ParticipantId) and CallType == 'P2P' and EndpointType == 'VoIP', -1, 1)
| where CorrelationId != ParticipantId
| extend ParticipantId = coalesce(ParticipantId, Identifier, EndpointId)
| extend ParticipantId = iff(ParticipantId == 'Redacted', strcat('RedactedParticipant-', EndpointType, '-Identifier-', Identifier), ParticipantId)
| extend EndpointId = iff(EndpointId == 'Redacted', strcat('RedactedEndpoint-', EndpointType, '-Identifier-', Identifier), EndpointId)
| summarize hint.strategy = shuffle arg_max(TimeGenerated, *) by ParticipantId
| extend CallDroppedUngracefully = ParticipantEndReason in ('380', '400', '407', '408', '409', '410', 
'412', '417', '430', '439', '440', '481', '483', '488', '489', '493', '500', '502', '503', '504', '580')
| project
    ParentEntityId = CorrelationId,
    ParentEntityType = 'Call',
    EntityType = 'Participant',
    EntityId = ParticipantId,
    EntityStartTime=ParticipantStartTime,
    EntityEndTime=ParticipantEndTime,
    EntityDuration=ParticipantDuration,
    EntityDisplayName = strcat('Participant-', ParticipantId),
    EntityPayload = bag_pack(
        'EndReasonCode', toint(ParticipantEndReason),
        'EndReasonPhrase', EndReason,
        'Identifier', Identifier,
        'EndpointId', EndpointId,
        'ParticipantType', ParticipantType,
        'EndpointType', EndpointType,
        'SdkVersion', SdkVersion,
        'OsVersion', OsVersion,
        'PstnParticipantCallType', PstnParticipantCallType
    ),
    Insights_HasIssues = CallDroppedUngracefully,
    Insights_Payload = bag_pack(
        'EndReasonCode', toint(ParticipantEndReason),
        'EndReasonPhrase', EndReason,
        'ParticipantId', ParticipantId,
        'CallDroppedUngracefully', CallDroppedUngracefully),
    GroupName = "lifeCycle",
    Rank);
//
let clientSideParticipants = materialize(ACSCallClientOperations
| where ParticipantId in (participants) or CallId == queryConditions_callId
| where isnotempty(OperationName) and OperationName != 'CallClientOperations' 
and isnotempty(OperationId) and isnotempty(CallClientTimeStamp)
| extend OperationId = coalesce(hash_sha256(strcat(OperationId, tostring(CallClientTimeStamp), OperationName)), tostring(new_guid()))
| summarize hint.strategy = shuffle arg_max(CallId, *) by OperationId
| where isnotempty(ParticipantId)
| extend OS = parse_user_agent(UserAgent, 'os').OperatingSystem
| extend OsVersion = strcat(OS.Family, OS.MajorVersion,'.', OS.MinorVersion)
| project OperationId, ParticipantId, CallId, CallClientTimeStamp, OperationName, OperationPayload, OsVersion, SdkVersion, ResultSignature, ResultType
| extend OperationPayload = todynamic(OperationPayload)
| extend         
    UFDQuality = tostring(OperationPayload.DiagnosticQuality),
    UFDType = tostring(OperationPayload.DiagnosticChanged),
    isUFD = OperationName == 'UserFacingDiagnostics'
| extend 
    ResultType = iff(isUFD, iff(UFDQuality != 'Good' and not(UFDType has_any ("SpeakingWhileMicrophoneIsMuted", "SpeakerMuted")), 'Failed', 'Succeeded'), ResultType),
    CallDroppedUngracefully = iff(OperationName in ('Hangup', 'EnterCall', 'Join'), ResultType !in ('Succeeded', 'Success', 'ExpectedError'), False),
    ParticipantStartTime = iff(OperationName == 'EnterCall', CallClientTimeStamp, datetime(null)),
    ParticipantEndTime = iff(OperationName == 'Hangup', CallClientTimeStamp, datetime(null))
| summarize hint.strategy = shuffle arg_max(CallId, *), ResultType = iff(countif(ResultType == 'Failed') > 0, 'Failed', 'Succeeded'),
    CallDroppedUngracefully = countif(CallDroppedUngracefully) > 0,
    ParticipantStartTimeApprox = min(CallClientTimeStamp), 
    ParticipantEndTimeApprox = max(CallClientTimeStamp) by ParticipantId
| extend 
    ParticipantStartTime = coalesce(ParticipantStartTime, ParticipantStartTimeApprox),
    ParticipantEndTime = coalesce(ParticipantEndTime, ParticipantEndTimeApprox)
| project
    ParentEntityId = queryConditions_callId,
    ParentEntityType = 'Call',
    EntityId = ParticipantId,
    EntityType = 'Participant',
    EntityDisplayName = strcat('Participant-', ParticipantId),
    EntityStartTime=ParticipantStartTime,
    EntityEndTime=ParticipantEndTime,
    EntityDuration=tolong((ParticipantEndTime - ParticipantStartTime)/1s),
    EntityPayload = bag_pack(
        'ParticipantType', 'ACS',
        'EndpointType', 'VoIP',
        'SdkVersion', SdkVersion,
        'OsVersion', OsVersion
    ),
    Insights_HasIssues = ResultType == 'Failed',
    Insights_Payload = bag_pack('ParticipantId', ParticipantId, 'CallDroppedUngracefully', CallDroppedUngracefully),
    GroupName = "lifeCycle",
    Rank = 0);
// Merge participantEntities from service side and client side, and if the participant exists in both sides, we take the one with higher Rank.
union serviceSideParticipants, clientSideParticipants
| summarize hint.strategy = shuffle arg_max(Rank, *), EntityPayload_Merged = make_bag(EntityPayload),
    Insights_Payload_Merged = make_bag(Insights_Payload),
    Insights_HasIssues_Merged = countif(Insights_HasIssues) > 0 by EntityId
| order by Rank
| project 
    ParentEntityId,
    ParentEntityType,
    EntityId,
    EntityType,
    EntityDisplayName,
    EntityStartTime,
    EntityEndTime,
    EntityDuration,
    EntityPayload = EntityPayload_Merged,
    Insights_HasIssues = Insights_HasIssues_Merged, 
    Insights_Payload = Insights_Payload_Merged
```


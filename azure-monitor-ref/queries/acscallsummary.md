---
title: Example log table queries for ACSCallSummary
description:  Example queries for ACSCallSummary log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ACSCallSummary table


### Participants per call  


Calculates the average number of participants per call.  

```query
ACSCallSummary
// Get the distinct participants in a call
| distinct CorrelationId, ParticipantId, EndpointId
// Count the participants and distinct calls
| summarize num_participants=count(), num_calls=dcount(CorrelationId)
// Calculate the average number of distinct participants per call
| extend avg_participants = toreal(num_participants) / toreal(num_calls)
| project num_participants, num_calls, avg_participants
```



### Participant Phone Numbers  


Lists the phone numbers of the participants in the call. (Phone numbers come from ACSBillingUsage table).  

```query
ACSCallSummary
// Get the calls with CallType as Group
| where CallType == 'Group'
| project CorrelationId, ParticipantId, ParticipantStartTime, ParticipantDuration, EndpointType, CallType, CallStartTime, PstnParticipantCallType
// Join with ACSBillingUsage data on ParticipantId
| join kind=leftouter (ACSBillingUsage
                        | where isnotempty(ParticipantId)
                        | project ParticipantId, UserIdA, UserIdB, StartTime, Quantity)
    on ParticipantId
// Combine with calls of CallType P2P
| union (ACSCallSummary
| where CallType == 'P2P'
| project CorrelationId, ParticipantId, ParticipantStartTime, ParticipantDuration, EndpointType, CallType, CallStartTime, PstnParticipantCallType
// Join with ACSBillingUsage data on CorrelationId
| join kind=leftouter (ACSBillingUsage
                        | where isnotempty(ParticipantId)
                        | project CorrelationId, ParticipantId, UserIdA, UserIdB, StartTime, Quantity)
    on CorrelationId)
| order by CallStartTime, ParticipantStartTime
```



### Participants per group call  


Produces a histogram of the number of participants in group calls.  

```query
ACSCallSummary
// Filter out all P2P calls to calculate only participants in Group calls
| where CallType == 'Group'
// Get the distinct participants in a call
| distinct CorrelationId, ParticipantId
// Count the number of participants per call
| summarize num_participants=count() by CorrelationId
// Aggregate the numbers of participants per call (e.g. if there are three calls
// with 5 participants, this will produce a row [num_participants=5, participant_counts=3])
| summarize participant_counts=count() by num_participants
| order by num_participants asc 
| render columnchart with (xcolumn = num_participants, title="Number of participants per group call")
```



### Call type ratio  


Produces a pie chart of the proportion of call types (P2P and group calls).  

```query
ACSCallSummary
// Count distinct calls (dcount(CorrelationId)) per call type
| summarize call_types=dcount(CorrelationId) by CallType
| render piechart title="Call Type Ratio"
```



### Call duration histogram  


Produces a histogram of call durations in seconds.  

```query
ACSCallSummary
// Get the distinct combinations of CorrelationId, CallDuration
| distinct CorrelationId, CallDuration
// Count call duration bins (60 second intervals)
| summarize duration_counts=count() by bin(CallDuration, 60)
| order by CallDuration asc
| render columnchart with (xcolumn = CallDuration, title="Call duration histogram")
```



### Call duration percentiles  


Calculates the average call duration in seconds, as well as the 50%, 90%, and 99% call duration percentiles.  

```query
ACSCallSummary
// Get the distinct combinations of CorrelationId, CallDuration
| distinct CorrelationId, CallDuration
// Calculate average and percentiles (50%, 90%, and 99%) of call durations (in seconds)
| summarize avg(CallDuration), percentiles(CallDuration, 50, 90, 99)
```



### Daily calls  


Produces a histogram of calls made per day in the last week.  

```query
ACSCallSummary
// To filter out calls made over a week ago, uncomment the next line
// | where CallStartTime > ago(7d)
// Get the distinct combinations of CorrelationId and CallStartTime
| distinct CorrelationId, CallStartTime
// Adds a new column with the call start day
| extend day = floor(CallStartTime, 1d)
// Count the number of calls per day
| summarize event_count=count() by day
| sort by day asc
| render columnchart title="Number of calls per day"
```



### Hourly calls  


Produces a histogram of calls made per hour in the last day.  

```query
ACSCallSummary
// Get the distinct combinations of CorrelationId and CallStartTime
| distinct CorrelationId, CallStartTime
// Adds a new column with the call start hour
| extend hour = floor(CallStartTime, 1h)
// Count the number of calls per hour
| summarize event_count=count() by hour
| sort by hour asc
| render columnchart title="Number of calls per hour in last day"
```



### Endpoints per call  


Calculates the average number of distinct endpoints per call.  

```query
ACSCallSummary
// Get the distinct combinations of CorrelationId and EndpointId
| distinct CorrelationId, EndpointId
// Count all endpoints and distinct calls
| summarize num_endpoints=count(), num_calls=dcount(CorrelationId)
// Calculate the average number of distinct endpoints per call
| extend avg_endpoints = toreal(num_endpoints) / toreal(num_calls)
| project num_endpoints, num_calls, avg_endpoints
```



### SDK version ratio  


Produces a pie chart of the proportion of SDK versions used by participants.  

```query
ACSCallSummary
// Get the distinct participants in a call
| distinct CorrelationId, ParticipantId, EndpointId, SdkVersion
// Count participants that are using a particular SDK
| summarize sdk_counts=count() by SdkVersion
| order by SdkVersion asc
| render piechart title="SDK Version Ratio"

```



### OS version ratio  


Produces a pie chart of the proportion of OS versions used by participants.  

```query
ACSCallSummary
// Get the distinct participants in a call
| distinct CorrelationId, ParticipantId, EndpointId, OsVersion
// Simplified OS version name by searching for a specific OS keyword
// and performs a different string split operation per OS type
| extend simple_os = case(  indexof(OsVersion, "Android") != -1, tostring(split(OsVersion, ";")[0]),
                            indexof(OsVersion, "Darwin") != -1, tostring(split(OsVersion, ":")[0]),
                            indexof(OsVersion, "Windows") != -1, tostring(split(OsVersion, ".")[0]),
                            OsVersion
                        )
// Count the participants that are using a particular OS version
| summarize os_counts=count() by simple_os
| order by simple_os asc
| render piechart title="OS Version Ratio"
```



### CallSummary log for CallAutomation API call  


Queries the summary log for a call which was interacted with by Call Automation API using correlation ID.  

```query
ACSCallAutomationIncomingOperations 
//| where CorrelationId == "<correlation ID>" // This can be uncommented to filter on a specific correlation ID
| join kind=inner
    (ACSCallSummary)
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



### Search all client operations in a call  


Find all client operations for all participants in a call by callId. This query is also used in Call Diagnostics to search for client operations.  

```query
// Replace queryConditions_callId with the callId you want to investigate.
declare query_parameters(queryConditions_callId:string = '00000000-0000-0000-0000-000000000000');
let rangeEventsWithCorrelation = dynamic(['UserFacingDiagnostics']);
let pointEvents = dynamic([
'SelectedMicrophoneChanged', 'SelectedSpeakerChanged', 'OptimalVideoCount-changed', 'State-changed', 'CallMode-changed',
'IsMuted-changed', 'IsIncomingAudioMuted-changed', 'Id-changed', 'Role-changed', 'SelectedDevice-changed', 'PageHidden',
'optimalVideoCount-changed', 'state-changed', 'callMode-changed', 'isMuted-changed', 'isIncomingAudioMuted-changed', 
'id-changed', 'role-changed', 'selectedDevice-changed', 'pageHidden']);
let participants = materialize(ACSCallSummary
| where CorrelationId == queryConditions_callId
| where ParticipantId != CorrelationId and isnotempty(ParticipantId)
| extend CallEndTime = CallStartTime + 1s*CallDuration
| distinct ParticipantId, CallStartTime, CallEndTime);
let OperationsTimestampLowerBound = max_of(toscalar(participants | summarize min(CallStartTime) | take 1) - 2h, ago(365d));
let OperationsTimestampUpperBound = min_of(toscalar(participants | summarize max(CallEndTime) | take 1) + 2h, now()+365d);
// We need clientIds to get all operations before call is established.
let callClientIds = materialize(ACSCallClientOperations
| where ParticipantId in ((participants | project ParticipantId)) or CallId == queryConditions_callId
| distinct ClientInstanceId, ParticipantId);
//
let allOperations = 
materialize(ACSCallClientOperations
| where CallClientTimeStamp between (OperationsTimestampLowerBound .. OperationsTimestampUpperBound)
| where ParticipantId in ((participants | project ParticipantId)) or CallId == queryConditions_callId or ClientInstanceId in ((callClientIds | project ClientInstanceId))
| where isnotempty(OperationName) and OperationName != 'CallClientOperations' 
and isnotempty(OperationId) and isnotempty(CallClientTimeStamp)
| join kind=leftouter hint.strategy=shuffle callClientIds on ClientInstanceId 
| extend ParticipantId = coalesce(ParticipantId, ParticipantId1) | project-away ParticipantId1, ClientInstanceId1
| summarize hint.strategy = shuffle arg_max(TimeGenerated, *) by OperationId, OperationName, CallClientTimeStamp);
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
// Make sure the UFD payload are aggregated in time-asc order.
| order by CallClientTimeStamp asc
| summarize hint.strategy = shuffle 
    arg_max(TimeGenerated, *), ResultType = iff(countif(UFDQuality != 'Good')>0, 'Failed', 'Succeeded'), 
    OperationStartTime = min(CallClientTimeStamp), OperationEndTime = max(CallClientTimeStamp),
    OperationPayloadPacked = make_bag(OperationPayloadNew) by OperationId, UFDType
| extend 
    ResultType = iff(UFDType has_any ("SpeakingWhileMicrophoneIsMuted", "SpeakerMuted"), 'Succeeded', ResultType),
    OperationEndTime = max_of(OperationEndTime, OperationStartTime+10ms)
| extend OperationPayload = todynamic(OperationPayload)
| extend UFDType = coalesce(tostring(OperationPayload.DiagnosticChanged), tostring(OperationPayload.diagnosticChanged))
// Capitalize the first letter.
| extend UFDType = strcat(toupper(substring(UFDType, 0, 1)), substring(UFDType, 1))
| extend parent_entity_type = case(OperationName has_any ('MuteMicrophone', 'UnmuteMicrophone', 'SelectedMicrophoneChanged', 
                                'SelectedSpeakerChanged', 'IsMuted-changed', 'IsIncomingAudioMuted-changed', 'StopAudio'),
                                'Audio',
                                // ADP can have both audio and video requested, so assign it to App
                                OperationName has_any ('State-changed', 'CallMode-changed', 'Id-changed', 'Role-changed', 
                                'SelectedDevice-changed', 'PageHidden', 'AcceptIncomingCall', 'RejectIncomingCall', 'Hangup', 
                                'AskDevicePermission', 'EnterCall', 'CallAgentInit'),
                                'App',
                                OperationName has_any ('StartScreenShare', 'StopScreenShare'),
                                'ScreenSharing',
                                OperationName has_any ('OptimalVideoCount-changed'),
                                'Video',
                                OperationName has_any ('CreateView', 'DisposeView', 'StartVideo', 'StopVideo', 'SwitchSource'),
                                case(
                                    tostring(OperationPayload.streamType) == 'Video',
                                    'Video',
                                    tostring(OperationPayload.streamType) == 'ScreenSharing',
                                    'ScreenSharing',
                                    tostring(OperationPayload.streamType) == 'RawMedia',
                                    'RawMedia',
                                    'Video'
                                ),
                                OperationName == 'UserFacingDiagnostics',
                                case(
                                    UFDType contains 'Speak',
                                    'Audio',
                                    UFDType contains 'microphone',
                                    'Audio',
                                    UFDType contains 'camera',
                                    'Video',
                                    UFDType contains 'capture',
                                    'Video',
                                    UFDType contains 'screenshare',
                                    'ScreenSharing',
                                    UFDType contains 'network',
                                    'Network',
                                    'App'
                                ),
                                'App')
| project
    ParentEntityId = strcat(ParticipantId, '-', parent_entity_type),
    ParentEntityType = parent_entity_type,
    OperationRoundtripId = OperationId,
    OperationId = OperationId,
    OperationName = OperationName,
    OperationType = UFDType,
    OperationStartTime,
    OperationEndTime,
    OperationDuration = DurationMs,
    OperationDisplayName = UFDType,
    OperationResultCode = toint(iff(ResultType !in ('Succeeded', 'Success', 'ExpectedError'), 500, 200)),
    OperationResult = ResultType,
    OperationPayload = OperationPayloadPacked,
    Insights_HasIssues = ResultType !in ('Succeeded', 'Success', 'ExpectedError'),
    ParticipantId,
    UserAgent
| extend 
    Insights_Payload = bag_pack('ResultType', OperationResult, 'ResultSignature', OperationResultCode, 'userAgent', UserAgent, 'ParticipantId', ParticipantId),
    ShowLabel = true
| project-away UserAgent);
//
let nonCorrelatedOperations = materialize(allOperations
| where OperationName !in (rangeEventsWithCorrelation)
| extend OperationId = coalesce(hash_sha256(strcat(OperationId, tostring(CallClientTimeStamp))), tostring(new_guid()))
| summarize hint.strategy = shuffle arg_max(TimeGenerated, *) by OperationId
| extend OperationPayload = todynamic(OperationPayload)
| extend UFDType = coalesce(tostring(OperationPayload.DiagnosticChanged), tostring(OperationPayload.diagnosticChanged))
// Capitalize the first letter.
| extend UFDType = strcat(toupper(substring(UFDType, 0, 1)), substring(UFDType, 1))
| extend parent_entity_type = case(OperationName has_any ('MuteMicrophone', 'UnmuteMicrophone', 'SelectedMicrophoneChanged', 
                                'SelectedSpeakerChanged', 'IsMuted-changed', 'IsIncomingAudioMuted-changed', 'StopAudio'),
                                'Audio',
                                // ADP can have both audio and video requested, so assign it to App
                                OperationName has_any ('State-changed', 'CallMode-changed', 'Id-changed', 'Role-changed', 
                                'SelectedDevice-changed', 'PageHidden', 'AcceptIncomingCall', 'RejectIncomingCall', 'Hangup', 
                                'AskDevicePermission', 'EnterCall', 'CallAgentInit'),
                                'App',
                                OperationName has_any ('StartScreenShare', 'StopScreenShare'),
                                'ScreenSharing',
                                OperationName has_any ('OptimalVideoCount-changed'),
                                'Video',
                                OperationName has_any ('CreateView', 'DisposeView', 'StartVideo', 'StopVideo', 'SwitchSource'),
                                case(
                                    tostring(OperationPayload.streamType) == 'Video',
                                    'Video',
                                    tostring(OperationPayload.streamType) == 'ScreenSharing',
                                    'ScreenSharing',
                                    tostring(OperationPayload.streamType) == 'RawMedia',
                                    'RawMedia',
                                    'Video'
                                ),
                                OperationName == 'UserFacingDiagnostics',
                                case(
                                UFDType contains 'Speak',
                                'Audio',
                                UFDType contains 'microphone',
                                'Audio',
                                UFDType contains 'camera',
                                'Video',
                                UFDType contains 'capture',
                                'Video',
                                UFDType contains 'screenshare',
                                'ScreenSharing',
                                UFDType contains 'network',
                                'Network',
                                'App'
                                ),
                                'App')
| project
    ParentEntityId = strcat(ParticipantId, '-', parent_entity_type),
    ParentEntityType = parent_entity_type,
    OperationRoundtripId = OperationId,
    OperationId = OperationId,
    OperationName,
    OperationType=OperationName,
    OperationStartTime=CallClientTimeStamp,
    OperationEndTime=iff(OperationName in (pointEvents), CallClientTimeStamp, CallClientTimeStamp + max_of(DurationMs, 10) * 1ms),
    OperationDuration=DurationMs,
    OperationDisplayName = OperationName,
    OperationResultCode = ResultSignature,
    OperationResult = ResultType,
    OperationPayload,
    Insights_HasIssues = ResultType !in ('Succeeded', 'Success', 'ExpectedError'),
    Insights_Payload = bag_pack('ResultType', ResultType, 'ResultSignature', ResultSignature, 'userAgent', UserAgent, 'ParticipantId', ParticipantId),
    ParticipantId,
    ShowLabel = true);
let poorOperations = materialize((union nonCorrelatedOperations, correlatedOperations)
    | where Insights_HasIssues
    | extend 
        ParentEntityId = ParticipantId,
        ParentEntityType = 'Participant',
        OperationId = strcat('Participant-Issues-', OperationId),
        GroupName = "lifeCycle",
        ShowLabel = false);
union poorOperations, nonCorrelatedOperations, correlatedOperations
| project
    ParentEntityId,
    ParentEntityType,
    OperationId,
    OperationRoundtripId = OperationId,
    OperationName,
    OperationDisplayName,
    OperationResultCode,
    OperationResult,
    OperationType,
    OperationStartTime,
    OperationEndTime,
    OperationPayload,
    Insights_HasIssues,
    Insights_Payload
```


---
title: Supported metrics - Microsoft.CognitiveServices/accounts
description: Reference for Microsoft.CognitiveServices/accounts metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.CognitiveServices/accounts  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.CognitiveServices/accounts resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Action Feature Occurrences<p><p>Number of times each action feature appears. |`ActionFeatureIdOccurrences` |Count |Total |FeatureId, Mode, RunId |Yes|
|Action Features Per Event<p><p>Average number of action features per event. |`ActionFeaturesPerEvent` |Count |Average |Mode, RunId |Yes|
|Action Occurences<p><p>Number of times each action appears. |`ActionIdOccurrences` |Count |Total |ActionId, Mode, RunId |Yes|
|Action Namespaces Per Event<p><p>Average number of action namespaces per event. |`ActionNamespacesPerEvent` |Count |Average |Mode, RunId |Yes|
|Actions Per Event<p><p>Number of actions per event. |`ActionsPerEvent` |Count |Average |Mode, RunId |Yes|
|Audio Seconds Transcribed<p><p>Number of seconds transcribed |`AudioSecondsTranscribed` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Audio Seconds Translated<p><p>Number of seconds translated |`AudioSecondsTranslated` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Baseline Estimator Overall Reward<p><p>Baseline Estimator Overall Reward. |`BaselineEstimatorOverallReward` |Count |Average |Mode, RunId |Yes|
|Baseline Estimator Slot Reward<p><p>Baseline Estimator Reward by slot. |`BaselineEstimatorSlotReward` |Count |Average |SlotId, SlotIndex, Mode, RunId |Yes|
|Baseline Random Estimator Overall Reward<p><p>Baseline Random Estimator Overall Reward. |`BaselineRandomEstimatorOverallReward` |Count |Average |Mode, RunId |Yes|
|Baseline Random Estimator Slot Reward<p><p>Baseline Random Estimator Reward by slot. |`BaselineRandomEstimatorSlotReward` |Count |Average |SlotId, SlotIndex, Mode, RunId |Yes|
|Baseline Random Event count<p><p>Estimation for baseline random event count. |`BaselineRandomEventCount` |Count |Total |Mode, RunId |Yes|
|Baseline Random Reward<p><p>Estimation for baseline random reward. |`BaselineRandomReward` |Count |Total |Mode, RunId |Yes|
|Blocked Calls<p><p>Number of calls that exceeded rate or quota limit. |`BlockedCalls` |Count |Total |ApiName, OperationName, Region, RatelimitKey |Yes|
|Inference Count<p><p>Inference Count of Carnegie Frontdoor Service |`CarnegieInferenceCount` |Count |Total |Region, Modality, Category, Language, SeverityLevel, UseCustomList |Yes|
|Characters Trained (Deprecated)<p><p>Total number of characters trained. |`CharactersTrained` |Count |Total |ApiName, OperationName, Region |Yes|
|Characters Translated (Deprecated)<p><p>Total number of characters in incoming text request. |`CharactersTranslated` |Count |Total |ApiName, OperationName, Region |Yes|
|Client Errors<p><p>Number of calls with client side error (HTTP response code 4xx). |`ClientErrors` |Count |Total |ApiName, OperationName, Region, RatelimitKey |Yes|
|Computer Vision Transactions<p><p>Number of Computer Vision Transactions |`ComputerVisionTransactions` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Call Count for Image Moderation<p><p>Number of calls for image moderation. |`ContentSafetyImageAnalyzeRequestCount` |Count |Total |ApiVersion |Yes|
|Call Count for Text Moderation<p><p>Number of calls for text moderation. |`ContentSafetyTextAnalyzeRequestCount` |Count |Total |ApiVersion |Yes|
|Context Feature Occurrences<p><p>Number of times each context feature appears. |`ContextFeatureIdOccurrences` |Count |Total |FeatureId, Mode, RunId |Yes|
|Context Features Per Event<p><p>Number of context features per event. |`ContextFeaturesPerEvent` |Count |Average |Mode, RunId |Yes|
|Context Namespaces Per Event<p><p>Number of context namespaces per event. |`ContextNamespacesPerEvent` |Count |Average |Mode, RunId |Yes|
|Custom Vision Training Time<p><p>Custom Vision training time |`CustomVisionTrainingTime` |Seconds |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Custom Vision Transactions<p><p>Number of Custom Vision prediction transactions |`CustomVisionTransactions` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Data In<p><p>Size of incoming data in bytes. |`DataIn` |Bytes |Total |ApiName, OperationName, Region |Yes|
|Data Out<p><p>Size of outgoing data in bytes. |`DataOut` |Bytes |Total |ApiName, OperationName, Region |Yes|
|Document Characters Translated<p><p>Number of characters in document translation request. |`DocumentCharactersTranslated` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Document Custom Characters Translated<p><p>Number of characters in custom document translation request. |`DocumentCustomCharactersTranslated` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Face Images Trained<p><p>Number of images trained. 1,000 images trained per transaction. |`FaceImagesTrained` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Faces Stored<p><p>Number of faces stored, prorated daily. The number of faces stored is reported daily. |`FacesStored` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Face Transactions<p><p>Number of API calls made to Face service |`FaceTransactions` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Feature Cardinality by Action<p><p>Feature Cardinality based on Action. |`FeatureCardinality_Action` |Count |Average |FeatureId, Mode, RunId |Yes|
|Feature Cardinality by Context<p><p>Feature Cardinality based on Context. |`FeatureCardinality_Context` |Count |Average |FeatureId, Mode, RunId |Yes|
|Feature Cardinality by Slot<p><p>Feature Cardinality based on Slot. |`FeatureCardinality_Slot` |Count |Average |FeatureId, Mode, RunId |Yes|
|Processed FineTuned Training Hours<p><p>Number of Training Hours Processed on an OpenAI FineTuned Model |`FineTunedTrainingHours` |Count |Total |ApiName, ModelDeploymentName, FeatureName, UsageChannel, Region |Yes|
|Generated Completion Tokens<p><p>Number of Generated Tokens from an OpenAI Model |`GeneratedTokens` |Count |Total |ApiName, ModelDeploymentName, FeatureName, UsageChannel, Region |Yes|
|Images Stored<p><p>Number of Custom Vision images stored. |`ImagesStored` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Latency<p><p>Latency in milliseconds. |`Latency` |MilliSeconds |Average |ApiName, OperationName, Region, RatelimitKey |Yes|
|Learned Events<p><p>Number of Learned Events. |`LearnedEvents` |Count |Total |IsMatchBaseline, Mode, RunId |Yes|
|LUIS Speech Requests<p><p>Number of LUIS speech to intent understanding requests |`LUISSpeechRequests` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|LUIS Text Requests<p><p>Number of LUIS text requests |`LUISTextRequests` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Matched Rewards<p><p>Number of Matched Rewards. |`MatchedRewards` |Count |Total |Mode, RunId |Yes|
|Non Activated Events<p><p>Number of skipped events. |`NonActivatedEvents` |Count |Total |Mode, RunId |Yes|
|Slots<p><p>Number of slots per event. |`NumberOfSlots` |Count |Average |Mode, RunId |Yes|
|Number of Speaker Profiles<p><p>Number of speaker profiles enrolled. Prorated hourly. |`NumberofSpeakerProfiles` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Observed Rewards<p><p>Number of Observed Rewards. |`ObservedRewards` |Count |Total |Mode, RunId |Yes|
|Online Estimator Overall Reward<p><p>Online Estimator Overall Reward. |`OnlineEstimatorOverallReward` |Count |Average |Mode, RunId |Yes|
|Online Estimator Slot Reward<p><p>Online Estimator Reward by slot. |`OnlineEstimatorSlotReward` |Count |Average |SlotId, SlotIndex, Mode, RunId |Yes|
|Online Event Count<p><p>Estimation for online event count. |`OnlineEventCount` |Count |Total |Mode, RunId |Yes|
|Online Reward<p><p>Estimation for online reward. |`OnlineReward` |Count |Total |Mode, RunId |Yes|
|Processed Characters<p><p>Number of Characters processed by Immersive Reader. |`ProcessedCharacters` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Processed Health Text Records<p><p>Number of health text records processed |`ProcessedHealthTextRecords` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Processed Images<p><p>Number of images processed |`ProcessedImages` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Processed Pages<p><p>Number of pages processed |`ProcessedPages` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Processed Prompt Tokens<p><p>Number of Prompt Tokens Processed on an OpenAI Model |`ProcessedPromptTokens` |Count |Total |ApiName, ModelDeploymentName, FeatureName, UsageChannel, Region |Yes|
|Processed Text Records<p><p>Count of Text Records. |`ProcessedTextRecords` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|QA Text Records<p><p>Number of text records processed |`QuestionAnsweringTextRecords` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Ratelimit<p><p>The current ratelimit of the ratelimit key. |`Ratelimit` |Count |Total |Region, RatelimitKey |Yes|
|Average Reward Per Event<p><p>Average reward per event. |`Reward` |Count |Average |BaselineAction, ChosenActionId, MatchesBaseline, NonDefaultReward, Mode, RunId |Yes|
|Server Errors<p><p>Number of calls with service internal error (HTTP response code 5xx). |`ServerErrors` |Count |Total |ApiName, OperationName, Region, RatelimitKey |Yes|
|Slot Feature Occurrences<p><p>Number of times each slot feature appears. |`SlotFeatureIdOccurrences` |Count |Total |FeatureId, Mode, RunId |Yes|
|Slot Features Per Event<p><p>Average number of slot features per event. |`SlotFeaturesPerEvent` |Count |Average |Mode, RunId |Yes|
|Slot Occurrences<p><p>Number of times each slot appears. |`SlotIdOccurrences` |Count |Total |SlotId, SlotIndex, Mode, RunId |Yes|
|Slot Namespaces Per Event<p><p>Average number of slot namespaces per event. |`SlotNamespacesPerEvent` |Count |Average |Mode, RunId |Yes|
|Slot Reward<p><p>Reward per slot. |`SlotReward` |Count |Average |BaselineActionId, ChosenActionId, MatchesBaseline, NonDefaultReward, SlotId, SlotIndex, Mode, RunId |Yes|
|Speaker Recognition Transactions<p><p>Number of speaker recognition transactions |`SpeakerRecognitionTransactions` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Speech Model Hosting Hours<p><p>Number of speech model hosting hours |`SpeechModelHostingHours` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Speech Session Duration (Deprecated)<p><p>Total duration of speech session in seconds. |`SpeechSessionDuration` |Seconds |Total |ApiName, OperationName, Region |Yes|
|Successful Calls<p><p>Number of successful calls. |`SuccessfulCalls` |Count |Total |ApiName, OperationName, Region, RatelimitKey |Yes|
|AvailabilityRate<p><p>Availability percentage with the following calculation: (Total Calls - Server Errors)/Total Calls. Server Errors include any HTTP responses >=500. |`SuccessRate` |Percent |Average |ApiName, OperationName, Region, RatelimitKey |No|
|Synthesized Characters<p><p>Number of Characters. |`SynthesizedCharacters` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Text Characters Translated<p><p>Number of characters in incoming text translation request. |`TextCharactersTranslated` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Text Custom Characters Translated<p><p>Number of characters in incoming custom text translation request. |`TextCustomCharactersTranslated` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Text Trained Characters<p><p>Number of characters trained using text translation. |`TextTrainedCharacters` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Processed Inference Tokens<p><p>Number of Inference Tokens Processed on an OpenAI Model |`TokenTransaction` |Count |Total |ApiName, ModelDeploymentName, FeatureName, UsageChannel, Region |Yes|
|Total Calls<p><p>Total number of calls. |`TotalCalls` |Count |Total |ApiName, OperationName, Region, RatelimitKey |Yes|
|Total Errors<p><p>Total number of calls with error response (HTTP response code 4xx or 5xx). |`TotalErrors` |Count |Total |ApiName, OperationName, Region, RatelimitKey |Yes|
|Total Events<p><p>Number of events. |`TotalEvents` |Count |Total |Mode, RunId |Yes|
|Total Token Calls<p><p>Total number of token calls. |`TotalTokenCalls` |Count |Total |ApiName, OperationName, Region |Yes|
|Total Transactions (Deprecated)<p><p>Total number of transactions. |`TotalTransactions` |Count |Total |No Dimensions |Yes|
|User Baseline Event Count<p><p>Estimation for user defined baseline event count. |`UserBaselineEventCount` |Count |Total |Mode, RunId |Yes|
|User Baseline Reward<p><p>Estimation for user defined baseline reward. |`UserBaselineReward` |Count |Total |Mode, RunId |Yes|
|Voice Model Hosting Hours<p><p>Number of Hours. |`VoiceModelHostingHours` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|
|Voice Model Training Minutes<p><p>Number of Minutes. |`VoiceModelTrainingMinutes` |Count |Total |ApiName, FeatureName, UsageChannel, Region |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->
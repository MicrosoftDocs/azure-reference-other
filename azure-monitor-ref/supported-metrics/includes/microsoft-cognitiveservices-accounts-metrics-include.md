---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/02/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.CognitiveServices/accounts, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Action Feature Occurrences**<p><p>Number of times each action feature appears. |`ActionFeatureIdOccurrences` |Count |Total |`FeatureId`, `Mode`, `RunId`|PT1M |Yes|
|**Action Features Per Event**<p><p>Average number of action features per event. |`ActionFeaturesPerEvent` |Count |Average |`Mode`, `RunId`|PT1M |Yes|
|**Action Occurences**<p><p>Number of times each action appears. |`ActionIdOccurrences` |Count |Total |`ActionId`, `Mode`, `RunId`|PT1M |Yes|
|**Action Namespaces Per Event**<p><p>Average number of action namespaces per event. |`ActionNamespacesPerEvent` |Count |Average |`Mode`, `RunId`|PT1M |Yes|
|**Actions Per Event**<p><p>Number of actions per event. |`ActionsPerEvent` |Count |Average |`Mode`, `RunId`|PT1M |Yes|
|**Active Tokens**<p><p>Total tokens minus cached tokens over a period of time. Applies to PTU and PTU-managed deployments.  Use this metric to understand your TPS or TPM based utilization for PTUs and compare to your benchmarks for target TPS or TPM for your scenarios. To breakdown API requests, you can add a filter or apply splitting by the following dimensions: ModelDeploymentName, ModelName, and ModelVersion. |`ActiveTokens` |Count |Minimum, Maximum, Average, Total |`Region`, `ModelDeploymentName`, `ModelName`, `ModelVersion`|PT1M |Yes|
|**Audio Seconds Transcribed**<p><p>Number of seconds transcribed |`AudioSecondsTranscribed` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Audio Seconds Translated**<p><p>Number of seconds translated |`AudioSecondsTranslated` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Provisioned-managed Utilization**<p><p>Utilization % for a provisoned-managed deployment, calculated as (PTUs consumed / PTUs deployed) x 100. When utilization is greater than or equal to 100%, calls are throttled and error code 429 returned. To breakdown this metric, you can add a filter or apply splitting by the following dimensions: ModelDeploymentName, ModelName, ModelVersion and StreamType (Streaming vs non-streaming requests) |`AzureOpenAIProvisionedManagedUtilization` |Percent |Minimum, Maximum, Average |`Region`, `StreamType`, `ModelDeploymentName`, `ModelName`, `ModelVersion`|PT1M |No|
|**Azure OpenAI Requests**<p><p>Number of calls made to the Azure OpenAI API over a period of time. Applies to PTU, PTU-Managed and Pay-as-you-go deployments. To breakdown API requests, you can add a filter or apply splitting by the following dimensions: ModelDeploymentName, ModelName, ModelVersion, StatusCode (successful, clienterrors, server errors), StreamType (Streaming vs non-streaming requests) and operation. |`AzureOpenAIRequests` |Count |Total |`ApiName`, `OperationName`, `Region`, `StreamType`, `ModelDeploymentName`, `ModelName`, `ModelVersion`, `StatusCode`|PT1M |Yes|
|**Time to Response**<p><p>Recommended latency (responsiveness) measure for streaming requests. Applies to PTU and PTU-managed deployments. Calculated as time taken for the first response to appear after a user sends a prompt, as measured by the API gateway. This number increases as the prompt size increases and/or cache hit size reduces. To breakdown time to response metric, you can add a filter or apply splitting by the following dimensions: ModelDeploymentName, ModelName, and ModelVersion. <p><p>Note: this metric is an approximation as measured latency is heavily dependent on multiple factors, including concurrent calls and overall workload pattern. In addition, it does not account for any client-side latency that may exist between your client and the API endpoint. Please refer to your own logging for optimal latency tracking. |`AzureOpenAITimeToResponse` |MilliSeconds |Minimum, Maximum, Average |`ApiName`, `OperationName`, `Region`, `StreamType`, `ModelDeploymentName`, `ModelName`, `ModelVersion`, `StatusCode`|PT1M |Yes|
|**Baseline Estimator Overall Reward**<p><p>Baseline Estimator Overall Reward. |`BaselineEstimatorOverallReward` |Count |Average |`Mode`, `RunId`|PT1M |Yes|
|**Baseline Estimator Slot Reward**<p><p>Baseline Estimator Reward by slot. |`BaselineEstimatorSlotReward` |Count |Average |`SlotId`, `SlotIndex`, `Mode`, `RunId`|PT1M |Yes|
|**Baseline Random Estimator Overall Reward**<p><p>Baseline Random Estimator Overall Reward. |`BaselineRandomEstimatorOverallReward` |Count |Average |`Mode`, `RunId`|PT1M |Yes|
|**Baseline Random Estimator Slot Reward**<p><p>Baseline Random Estimator Reward by slot. |`BaselineRandomEstimatorSlotReward` |Count |Average |`SlotId`, `SlotIndex`, `Mode`, `RunId`|PT1M |Yes|
|**Baseline Random Event count**<p><p>Estimation for baseline random event count. |`BaselineRandomEventCount` |Count |Total |`Mode`, `RunId`|PT1M |Yes|
|**Baseline Random Reward**<p><p>Estimation for baseline random reward. |`BaselineRandomReward` |Count |Total |`Mode`, `RunId`|PT1M |Yes|
|**Blocked Calls**<p><p>Number of calls that exceeded rate or quota limit. Do not use for Azure OpenAI service. |`BlockedCalls` |Count |Total |`ApiName`, `OperationName`, `Region`, `RatelimitKey`|PT1M |Yes|
|**Inference Count**<p><p>Inference Count of Carnegie Frontdoor Service |`CarnegieInferenceCount` |Count |Total |`Region`, `Modality`, `Category`, `Language`, `SeverityLevel`, `UseCustomList`|PT1M |Yes|
|**Characters Trained (Deprecated)**<p><p>Total number of characters trained. |`CharactersTrained` |Count |Total |`ApiName`, `OperationName`, `Region`|PT1M |Yes|
|**Characters Translated (Deprecated)**<p><p>Total number of characters in incoming text request. |`CharactersTranslated` |Count |Total |`ApiName`, `OperationName`, `Region`|PT1M |Yes|
|**Client Errors**<p><p>Number of calls with client side error (HTTP response code 4xx). Do not use for Azure OpenAI service. |`ClientErrors` |Count |Total |`ApiName`, `OperationName`, `Region`, `RatelimitKey`|PT1M |Yes|
|**Computer Vision Transactions**<p><p>Number of Computer Vision Transactions |`ComputerVisionTransactions` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Call Count for Image Moderation**<p><p>Number of calls for image moderation. |`ContentSafetyImageAnalyzeRequestCount` |Count |Total |`ApiVersion`|PT1M |Yes|
|**Call Count for Text Moderation**<p><p>Number of calls for text moderation. |`ContentSafetyTextAnalyzeRequestCount` |Count |Total |`ApiVersion`|PT1M |Yes|
|**Context Feature Occurrences**<p><p>Number of times each context feature appears. |`ContextFeatureIdOccurrences` |Count |Total |`FeatureId`, `Mode`, `RunId`|PT1M |Yes|
|**Context Features Per Event**<p><p>Number of context features per event. |`ContextFeaturesPerEvent` |Count |Average |`Mode`, `RunId`|PT1M |Yes|
|**Context Namespaces Per Event**<p><p>Number of context namespaces per event. |`ContextNamespacesPerEvent` |Count |Average |`Mode`, `RunId`|PT1M |Yes|
|**Custom Vision Training Time**<p><p>Custom Vision training time |`CustomVisionTrainingTime` |Seconds |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Custom Vision Transactions**<p><p>Number of Custom Vision prediction transactions |`CustomVisionTransactions` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Data In**<p><p>Size of incoming data in bytes. Do not use for Azure OpenAI service. |`DataIn` |Bytes |Total |`ApiName`, `OperationName`, `Region`|PT1M |Yes|
|**Data Out**<p><p>Size of outgoing data in bytes. Do not use for Azure OpenAI service. |`DataOut` |Bytes |Total |`ApiName`, `OperationName`, `Region`|PT1M |Yes|
|**Document Characters Translated**<p><p>Number of characters in document translation request. |`DocumentCharactersTranslated` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Document Custom Characters Translated**<p><p>Number of characters in custom document translation request. |`DocumentCustomCharactersTranslated` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Face Images Trained**<p><p>Number of images trained. 1,000 images trained per transaction. |`FaceImagesTrained` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Faces Stored**<p><p>Number of faces stored, prorated daily. The number of faces stored is reported daily. |`FacesStored` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Face Transactions**<p><p>Number of API calls made to Face service |`FaceTransactions` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Feature Cardinality by Action**<p><p>Feature Cardinality based on Action. |`FeatureCardinality_Action` |Count |Average |`FeatureId`, `Mode`, `RunId`|PT1M |Yes|
|**Feature Cardinality by Context**<p><p>Feature Cardinality based on Context. |`FeatureCardinality_Context` |Count |Average |`FeatureId`, `Mode`, `RunId`|PT1M |Yes|
|**Feature Cardinality by Slot**<p><p>Feature Cardinality based on Slot. |`FeatureCardinality_Slot` |Count |Average |`FeatureId`, `Mode`, `RunId`|PT1M |Yes|
|**Processed FineTuned Training Hours**<p><p>Number of Training Hours Processed on an OpenAI FineTuned Model |`FineTunedTrainingHours` |Count |Total |`ApiName`, `ModelDeploymentName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Generated Completion Tokens**<p><p>Number of tokens generated (output) from an OpenAI model. Applies to PTU, PTU-Managed and Pay-as-you-go deployments. To breakdown this metric, you can add a filter or apply splitting by the following dimensions: ModelDeploymentName and ModelName. |`GeneratedTokens` |Count |Total |`ApiName`, `ModelDeploymentName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Images Stored**<p><p>Number of Custom Vision images stored. |`ImagesStored` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Latency**<p><p>Latency in milliseconds. Do not use for Azure OpenAI service. |`Latency` |MilliSeconds |Average |`ApiName`, `OperationName`, `Region`, `RatelimitKey`|PT1M |Yes|
|**Learned Events**<p><p>Number of Learned Events. |`LearnedEvents` |Count |Total |`IsMatchBaseline`, `Mode`, `RunId`|PT1M |Yes|
|**LUIS Speech Requests**<p><p>Number of LUIS speech to intent understanding requests |`LUISSpeechRequests` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**LUIS Text Requests**<p><p>Number of LUIS text requests |`LUISTextRequests` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Matched Rewards**<p><p>Number of Matched Rewards. |`MatchedRewards` |Count |Total |`Mode`, `RunId`|PT1M |Yes|
|**Non Activated Events**<p><p>Number of skipped events. |`NonActivatedEvents` |Count |Total |`Mode`, `RunId`|PT1M |Yes|
|**Slots**<p><p>Number of slots per event. |`NumberOfSlots` |Count |Average |`Mode`, `RunId`|PT1M |Yes|
|**Number of Speaker Profiles**<p><p>Number of speaker profiles enrolled. Prorated hourly. |`NumberofSpeakerProfiles` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Observed Rewards**<p><p>Number of Observed Rewards. |`ObservedRewards` |Count |Total |`Mode`, `RunId`|PT1M |Yes|
|**Online Estimator Overall Reward**<p><p>Online Estimator Overall Reward. |`OnlineEstimatorOverallReward` |Count |Average |`Mode`, `RunId`|PT1M |Yes|
|**Online Estimator Slot Reward**<p><p>Online Estimator Reward by slot. |`OnlineEstimatorSlotReward` |Count |Average |`SlotId`, `SlotIndex`, `Mode`, `RunId`|PT1M |Yes|
|**Online Event Count**<p><p>Estimation for online event count. |`OnlineEventCount` |Count |Total |`Mode`, `RunId`|PT1M |Yes|
|**Online Reward**<p><p>Estimation for online reward. |`OnlineReward` |Count |Total |`Mode`, `RunId`|PT1M |Yes|
|**Processed Characters**<p><p>Number of Characters processed by Immersive Reader. |`ProcessedCharacters` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Processed Health Text Records**<p><p>Number of health text records processed |`ProcessedHealthTextRecords` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Processed Images**<p><p>Number of images processed |`ProcessedImages` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Processed Pages**<p><p>Number of pages processed |`ProcessedPages` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Processed Prompt Tokens**<p><p>Number of prompt tokens processed (input) on an OpenAI model. Applies to PTU, PTU-Managed and Pay-as-you-go deployments. To breakdown this metric, you can add a filter or apply splitting by the following dimensions: ModelDeploymentName and ModelName. |`ProcessedPromptTokens` |Count |Total |`ApiName`, `ModelDeploymentName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Processed Text Records**<p><p>Count of Text Records. |`ProcessedTextRecords` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**QA Text Records**<p><p>Number of text records processed |`QuestionAnsweringTextRecords` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Ratelimit**<p><p>The current ratelimit of the ratelimit key. Do not use for Azure OpenAI service. |`Ratelimit` |Count |Total |`Region`, `RatelimitKey`|PT1M |Yes|
|**Average Reward Per Event**<p><p>Average reward per event. |`Reward` |Count |Average |`BaselineAction`, `ChosenActionId`, `MatchesBaseline`, `NonDefaultReward`, `Mode`, `RunId`|PT1M |Yes|
|**Server Errors**<p><p>Number of calls with service internal error (HTTP response code 5xx). Do not use for Azure OpenAI service. |`ServerErrors` |Count |Total |`ApiName`, `OperationName`, `Region`, `RatelimitKey`|PT1M |Yes|
|**Slot Feature Occurrences**<p><p>Number of times each slot feature appears. |`SlotFeatureIdOccurrences` |Count |Total |`FeatureId`, `Mode`, `RunId`|PT1M |Yes|
|**Slot Features Per Event**<p><p>Average number of slot features per event. |`SlotFeaturesPerEvent` |Count |Average |`Mode`, `RunId`|PT1M |Yes|
|**Slot Occurrences**<p><p>Number of times each slot appears. |`SlotIdOccurrences` |Count |Total |`SlotId`, `SlotIndex`, `Mode`, `RunId`|PT1M |Yes|
|**Slot Namespaces Per Event**<p><p>Average number of slot namespaces per event. |`SlotNamespacesPerEvent` |Count |Average |`Mode`, `RunId`|PT1M |Yes|
|**Slot Reward**<p><p>Reward per slot. |`SlotReward` |Count |Average |`BaselineActionId`, `ChosenActionId`, `MatchesBaseline`, `NonDefaultReward`, `SlotId`, `SlotIndex`, `Mode`, `RunId`|PT1M |Yes|
|**Speaker Recognition Transactions**<p><p>Number of speaker recognition transactions |`SpeakerRecognitionTransactions` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Speech Model Hosting Hours**<p><p>Number of speech model hosting hours |`SpeechModelHostingHours` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Speech Session Duration (Deprecated)**<p><p>Total duration of speech session in seconds. |`SpeechSessionDuration` |Seconds |Total |`ApiName`, `OperationName`, `Region`|PT1M |Yes|
|**Successful Calls**<p><p>Number of successful calls. Do not use for Azure OpenAI service. |`SuccessfulCalls` |Count |Total |`ApiName`, `OperationName`, `Region`, `RatelimitKey`|PT1M |Yes|
|**AvailabilityRate**<p><p>Availability percentage with the following calculation: (Total Calls - Server Errors)/Total Calls. Server Errors include any HTTP responses >=500. Do not use for Azure OpenAI service. |`SuccessRate` |Percent |Minimum, Maximum, Average |`ApiName`, `OperationName`, `Region`, `RatelimitKey`|PT1M |No|
|**Synthesized Characters**<p><p>Number of Characters. |`SynthesizedCharacters` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Text Characters Translated**<p><p>Number of characters in incoming text translation request. |`TextCharactersTranslated` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Text Custom Characters Translated**<p><p>Number of characters in incoming custom text translation request. |`TextCustomCharactersTranslated` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Text Trained Characters**<p><p>Number of characters trained using text translation. |`TextTrainedCharacters` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Processed Inference Tokens**<p><p>Number of inference tokens processed on an OpenAI model. Calculated as prompt tokens (input) plus generated tokens (output). Applies to PTU, PTU-Managed and Pay-as-you-go deployments. To breakdown this metric, you can add a filter or apply splitting by the following dimensions: ModelDeploymentName and ModelName. |`TokenTransaction` |Count |Total |`ApiName`, `ModelDeploymentName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Total Calls**<p><p>Total number of calls. Do not use for Azure OpenAI service. |`TotalCalls` |Count |Total |`ApiName`, `OperationName`, `Region`, `RatelimitKey`|PT1M |Yes|
|**Total Errors**<p><p>Total number of calls with error response (HTTP response code 4xx or 5xx). Do not use for Azure OpenAI service. |`TotalErrors` |Count |Total |`ApiName`, `OperationName`, `Region`, `RatelimitKey`|PT1M |Yes|
|**Total Events**<p><p>Number of events. |`TotalEvents` |Count |Total |`Mode`, `RunId`|PT1M |Yes|
|**Total Token Calls**<p><p>Total number of token calls. |`TotalTokenCalls` |Count |Total |`ApiName`, `OperationName`, `Region`|PT1M |Yes|
|**Total Transactions (Deprecated)**<p><p>Total number of transactions. |`TotalTransactions` |Count |Total |\<none\>|PT1M |Yes|
|**User Baseline Event Count**<p><p>Estimation for user defined baseline event count. |`UserBaselineEventCount` |Count |Total |`Mode`, `RunId`|PT1M |Yes|
|**User Baseline Reward**<p><p>Estimation for user defined baseline reward. |`UserBaselineReward` |Count |Total |`Mode`, `RunId`|PT1M |Yes|
|**Voice Model Hosting Hours**<p><p>Number of Hours. |`VoiceModelHostingHours` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
|**Voice Model Training Minutes**<p><p>Number of Minutes. |`VoiceModelTrainingMinutes` |Count |Total |`ApiName`, `FeatureName`, `UsageChannel`, `Region`|PT1M |Yes|
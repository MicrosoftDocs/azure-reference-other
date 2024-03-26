---
title: Azure Monitor log analytics queries by tables
description: Azure Monitor log analytics queries by tables
author: EdB-MSFT
ms.topic: reference
ms.service: azure-monitor
ms.date: 03/26/2024
ms.author: edbaynash
ms.reviewer: lualderm

---

# Azure Monitor log analytics sample queries.

[Azure Monitor resource logs](/azure/azure-monitor/essentials/platform-logs-overview) are logs emitted by Azure services that describe the operation of those services or resources. When exported to a [Log Analytics workspace](/azure/azure-monitor/logs/log-analytics-workspace-overview) the logs are stored in tables. This set of articles contains sample queries to retrieve data from the log analytics tables. The queries are also available in the Log Analytics workspace.


## Sample queries by table

## [AACAudit](AACAudit.md)

- [Most recent delete key-value operations](AACAudit.md#most-recent-delete-key-value-operations)
- [Most recent client error](AACAudit.md#most-recent-client-error)

## [AACHttpRequest](AACHttpRequest.md)

- [Throttled Requests](AACHttpRequest.md#throttled-requests)
- [Most common server errors](AACHttpRequest.md#most-common-server-errors)
- [Most Active Clients by IP Address](AACHttpRequest.md#most-active-clients-by-ip-address)

## [AADCustomSecurityAttributeAuditLogs](AADCustomSecurityAttributeAuditLogs.md)

- [User's custom security attribute audits](AADCustomSecurityAttributeAuditLogs.md#users-custom-security-attribute-audits)

## [AADDomainServicesAccountLogon](AADDomainServicesAccountLogon.md)

- [Show logs from AADDomainServicesAccountLogon table](AADDomainServicesAccountLogon.md#show-logs-from-aaddomainservicesaccountlogon-table)

## [AADDomainServicesAccountManagement](AADDomainServicesAccountManagement.md)

- [Show logs from AADDomainServicesAccountManagement table](AADDomainServicesAccountManagement.md#show-logs-from-aaddomainservicesaccountmanagement-table)

## [AADDomainServicesDirectoryServiceAccess](AADDomainServicesDirectoryServiceAccess.md)

- [Show logs from AADDomainServicesDirectoryServiceAccess table](AADDomainServicesDirectoryServiceAccess.md#show-logs-from-aaddomainservicesdirectoryserviceaccess-table)

## [AADDomainServicesLogonLogoff](AADDomainServicesLogonLogoff.md)

- [Show logs from AADDomainServicesLogonLogoff table](AADDomainServicesLogonLogoff.md#show-logs-from-aaddomainserviceslogonlogoff-table)

## [AADDomainServicesPolicyChange](AADDomainServicesPolicyChange.md)

- [Show logs from AADDomainServicesPolicyChange table](AADDomainServicesPolicyChange.md#show-logs-from-aaddomainservicespolicychange-table)

## [AADDomainServicesPrivilegeUse](AADDomainServicesPrivilegeUse.md)

- [Show logs from AADDomainServicesPrivilegeUse table](AADDomainServicesPrivilegeUse.md#show-logs-from-aaddomainservicesprivilegeuse-table)

## [AADManagedIdentitySignInLogs](AADManagedIdentitySignInLogs.md)

- [Most active managed identities](AADManagedIdentitySignInLogs.md#most-active-managed-identities)

## [AADNonInteractiveUserSignInLogs](AADNonInteractiveUserSignInLogs.md)

- [Users with multiple cities](AADNonInteractiveUserSignInLogs.md#users-with-multiple-cities)
- [Most active ip addresses](AADNonInteractiveUserSignInLogs.md#most-active-ip-addresses)

## [AADProvisioningLogs](AADProvisioningLogs.md)

- [Provisioning actions for the last week](AADProvisioningLogs.md#provisioning-actions-for-the-last-week)
- [Provisioning errors](AADProvisioningLogs.md#provisioning-errors)
- [Provisioned objects by day](AADProvisioningLogs.md#provisioned-objects-by-day)

## [AADRiskyUsers](AADRiskyUsers.md)

- [High risk users](AADRiskyUsers.md#high-risk-users)

## [AADServicePrincipalRiskEvents](AADServicePrincipalRiskEvents.md)

- [Active service principal risk detections](AADServicePrincipalRiskEvents.md#active-service-principal-risk-detections)

## [AADServicePrincipalSignInLogs](AADServicePrincipalSignInLogs.md)

- [Most active service principals](AADServicePrincipalSignInLogs.md#most-active-service-principals)
- [Inactive service principals](AADServicePrincipalSignInLogs.md#inactive-service-principals)

## [AADUserRiskEvents](AADUserRiskEvents.md)

- [Recent user risk events](AADUserRiskEvents.md#recent-user-risk-events)
- [Active user risk detections](AADUserRiskEvents.md#active-user-risk-detections)

## [ABSBotRequests](ABSBotRequests.md)

- [Clients To Direct Line Channel](ABSBotRequests.md#clients-to-direct-line-channel)
- [Bot To Channels](ABSBotRequests.md#bot-to-channels)
- [Channels To Bot](ABSBotRequests.md#channels-to-bot)
- [Requests From Facebook To Azure Bot Service](ABSBotRequests.md#requests-from-facebook-to-azure-bot-service)
- [Requests From Azure Bot Service To Facebook API](ABSBotRequests.md#requests-from-azure-bot-service-to-facebook-api)
- [Activities Sent from Clients to Direct Line](ABSBotRequests.md#activities-sent-from-clients-to-direct-line)
- [Direct Line Channel Logs](ABSBotRequests.md#direct-line-channel-logs)
- [Failed Requests](ABSBotRequests.md#failed-requests)
- [Direct Line Channel Response Codes Line Chart](ABSBotRequests.md#direct-line-channel-response-codes-line-chart)
- [Requests Duration Line Chart](ABSBotRequests.md#requests-duration-line-chart)
- [Response Codes Line Chart](ABSBotRequests.md#response-codes-line-chart)
- [Response Codes PieChart](ABSBotRequests.md#response-codes-piechart)
- [Request Operations PieChart](ABSBotRequests.md#request-operations-piechart)

## [ACICollaborationAudit](ACICollaborationAudit.md)

- [How many times a resource was granted grants per pipeline run?](ACICollaborationAudit.md#how-many-times-a-resource-was-granted-grants-per-pipeline-run)
- [What entitlements was granted to my resource?](ACICollaborationAudit.md#what-entitlements-was-granted-to-my-resource)
- [What resources was granted accessed by an entitlement?](ACICollaborationAudit.md#what-resources-was-granted-accessed-by-an-entitlement)
- [Which participants was granted accessed to my resource?](ACICollaborationAudit.md#which-participants-was-granted-accessed-to-my-resource)

## [ACRConnectedClientList](ACRConnectedClientList.md)

- [Unique Redis client IP addresses](ACRConnectedClientList.md#unique-redis-client-ip-addresses)
- [Redis client connections per hour](ACRConnectedClientList.md#redis-client-connections-per-hour)

## [ACSAuthIncomingOperations](ACSAuthIncomingOperations.md)

- [List distinct auth operations](ACSAuthIncomingOperations.md#list-distinct-auth-operations)
- [Calculate auth operation duration percentiles](ACSAuthIncomingOperations.md#calculate-auth-operation-duration-percentiles)
- [Top 5 IP addresses per auth operation](ACSAuthIncomingOperations.md#top-5-ip-addresses-per-auth-operation)
- [Auth operational errors](ACSAuthIncomingOperations.md#auth-operational-errors)
- [Auth operation result counts](ACSAuthIncomingOperations.md#auth-operation-result-counts)

## [ACSBillingUsage](ACSBillingUsage.md)

- [Get long calls](ACSBillingUsage.md#get-long-calls)
- [Usage breakdown](ACSBillingUsage.md#usage-breakdown)
- [Record count breakdown](ACSBillingUsage.md#record-count-breakdown)
- [Participant Phone Numbers](ACSBillingUsage.md#participant-phone-numbers)

## [ACSCallAutomationIncomingOperations](ACSCallAutomationIncomingOperations.md)

- [Call Automation operations](ACSCallAutomationIncomingOperations.md#call-automation-operations)
- [Calculate Call Automation operation duration percentiles](ACSCallAutomationIncomingOperations.md#calculate-call-automation-operation-duration-percentiles)
- [Top 5 IP addresses per Call Automation operation](ACSCallAutomationIncomingOperations.md#top-5-ip-addresses-per-call-automation-operation)
- [Call Automation operational errors](ACSCallAutomationIncomingOperations.md#call-automation-operational-errors)
- [Call Automation operation result counts](ACSCallAutomationIncomingOperations.md#call-automation-operation-result-counts)
- [Call Automation logs for call connection ID](ACSCallAutomationIncomingOperations.md#call-automation-logs-for-call-connection-id)
- [Call Automation API operations on a call](ACSCallAutomationIncomingOperations.md#call-automation-api-operations-on-a-call)
- [CallDiagnostics log for CallAutomation API call](ACSCallAutomationIncomingOperations.md#calldiagnostics-log-for-callautomation-api-call)
- [CallSummary log for CallAutomation API call](ACSCallAutomationIncomingOperations.md#callsummary-log-for-callautomation-api-call)

## [ACSCallAutomationMediaSummary](ACSCallAutomationMediaSummary.md)

- [Loop play success rate](ACSCallAutomationMediaSummary.md#loop-play-success-rate)
- [Play to participant success rate](ACSCallAutomationMediaSummary.md#play-to-participant-success-rate)
- [Recognize success rate](ACSCallAutomationMediaSummary.md#recognize-success-rate)
- [Success rate by sub operation name](ACSCallAutomationMediaSummary.md#success-rate-by-sub-operation-name)

## [ACSCallClientMediaStatsTimeSeries](ACSCallClientMediaStatsTimeSeries.md)

- [Metrics per each media type](ACSCallClientMediaStatsTimeSeries.md#metrics-per-each-media-type)
- [Metric histogram per media type and direction](ACSCallClientMediaStatsTimeSeries.md#metric-histogram-per-media-type-and-direction)

## [ACSCallClientOperations](ACSCallClientOperations.md)

- [Count client operations by type](ACSCallClientOperations.md#count-client-operations-by-type)
- [Outgoing call failure reasons](ACSCallClientOperations.md#outgoing-call-failure-reasons)
- [Search calls by keyword](ACSCallClientOperations.md#search-calls-by-keyword)
- [Search all user facing diagnostics in a call](ACSCallClientOperations.md#search-all-user-facing-diagnostics-in-a-call)
- [Search all participants in a call](ACSCallClientOperations.md#search-all-participants-in-a-call)
- [Search all client operations in a call](ACSCallClientOperations.md#search-all-client-operations-in-a-call)

## [ACSCallDiagnostics](ACSCallDiagnostics.md)

- [Streams per call](ACSCallDiagnostics.md#streams-per-call)
- [Streams per call histogram](ACSCallDiagnostics.md#streams-per-call-histogram)
- [Media type ratio](ACSCallDiagnostics.md#media-type-ratio)
- [Transport type ratio](ACSCallDiagnostics.md#transport-type-ratio)
- [Average telemetry values](ACSCallDiagnostics.md#average-telemetry-values)
- [Jitter average histogram](ACSCallDiagnostics.md#jitter-average-histogram)
- [Jitter max histogram](ACSCallDiagnostics.md#jitter-max-histogram)
- [Packet loss rate average histogram](ACSCallDiagnostics.md#packet-loss-rate-average-histogram)
- [Packet loss rate max histogram](ACSCallDiagnostics.md#packet-loss-rate-max-histogram)
- [Round trip time average histogram](ACSCallDiagnostics.md#round-trip-time-average-histogram)
- [Round trip time max histogram](ACSCallDiagnostics.md#round-trip-time-max-histogram)
- [Jitter quality ratio](ACSCallDiagnostics.md#jitter-quality-ratio)
- [Packet loss rate quality ratio](ACSCallDiagnostics.md#packet-loss-rate-quality-ratio)
- [Round trip time quality ratio](ACSCallDiagnostics.md#round-trip-time-quality-ratio)
- [CallDiagnostics log for CallAutomation API call](ACSCallDiagnostics.md#calldiagnostics-log-for-callautomation-api-call)
- [Search calls by keyword](ACSCallDiagnostics.md#search-calls-by-keyword)
- [Search all participants in a call](ACSCallDiagnostics.md#search-all-participants-in-a-call)

## [ACSCallRecordingIncomingOperations](ACSCallRecordingIncomingOperations.md)

- [Call Recording operations](ACSCallRecordingIncomingOperations.md#call-recording-operations)
- [Calculate Call Recording operation duration percentiles](ACSCallRecordingIncomingOperations.md#calculate-call-recording-operation-duration-percentiles)
- [Top 5 IP addresses per Call Recording operation](ACSCallRecordingIncomingOperations.md#top-5-ip-addresses-per-call-recording-operation)
- [Call Recording operational errors](ACSCallRecordingIncomingOperations.md#call-recording-operational-errors)
- [Call Recording operation result counts](ACSCallRecordingIncomingOperations.md#call-recording-operation-result-counts)
- [Call Recording logs by ID](ACSCallRecordingIncomingOperations.md#call-recording-logs-by-id)

## [ACSCallRecordingSummary](ACSCallRecordingSummary.md)

- [Call Recording duration histogram](ACSCallRecordingSummary.md#call-recording-duration-histogram)
- [Call Recording duration percentiles](ACSCallRecordingSummary.md#call-recording-duration-percentiles)
- [Call Recording's end reason ratio](ACSCallRecordingSummary.md#call-recordings-end-reason-ratio)
- [Daily Call Recordings](ACSCallRecordingSummary.md#daily-call-recordings)
- [Hourly Call Recordings](ACSCallRecordingSummary.md#hourly-call-recordings)
- [Call Recording's mode ratio](ACSCallRecordingSummary.md#call-recordings-mode-ratio)

## [ACSCallSummary](ACSCallSummary.md)

- [Participants per call](ACSCallSummary.md#participants-per-call)
- [Participant Phone Numbers](ACSCallSummary.md#participant-phone-numbers)
- [Participants per group call](ACSCallSummary.md#participants-per-group-call)
- [Call type ratio](ACSCallSummary.md#call-type-ratio)
- [Call duration histogram](ACSCallSummary.md#call-duration-histogram)
- [Call duration percentiles](ACSCallSummary.md#call-duration-percentiles)
- [Daily calls](ACSCallSummary.md#daily-calls)
- [Hourly calls](ACSCallSummary.md#hourly-calls)
- [Endpoints per call](ACSCallSummary.md#endpoints-per-call)
- [SDK version ratio](ACSCallSummary.md#sdk-version-ratio)
- [OS version ratio](ACSCallSummary.md#os-version-ratio)
- [CallSummary log for CallAutomation API call](ACSCallSummary.md#callsummary-log-for-callautomation-api-call)
- [Search calls by keyword](ACSCallSummary.md#search-calls-by-keyword)
- [Search all participants in a call](ACSCallSummary.md#search-all-participants-in-a-call)
- [Search all client operations in a call](ACSCallSummary.md#search-all-client-operations-in-a-call)

## [ACSCallSurvey](ACSCallSurvey.md)

- [Overall call rating](ACSCallSurvey.md#overall-call-rating)
- [Audio rating](ACSCallSurvey.md#audio-rating)
- [Video rating](ACSCallSurvey.md#video-rating)
- [Screenshare rating](ACSCallSurvey.md#screenshare-rating)
- [Overall call issues](ACSCallSurvey.md#overall-call-issues)
- [Audio issues](ACSCallSurvey.md#audio-issues)
- [Video issues](ACSCallSurvey.md#video-issues)
- [Screenshare issues](ACSCallSurvey.md#screenshare-issues)
- [Search calls by keyword](ACSCallSurvey.md#search-calls-by-keyword)
- [Search all participants in a call](ACSCallSurvey.md#search-all-participants-in-a-call)

## [ACSChatIncomingOperations](ACSChatIncomingOperations.md)

- [Chat operations](ACSChatIncomingOperations.md#chat-operations)
- [Calculate chat operation duration percentiles](ACSChatIncomingOperations.md#calculate-chat-operation-duration-percentiles)
- [Top 5 IP addresses per chat operation](ACSChatIncomingOperations.md#top-5-ip-addresses-per-chat-operation)
- [Chat operational errors](ACSChatIncomingOperations.md#chat-operational-errors)
- [Chat operation result counts](ACSChatIncomingOperations.md#chat-operation-result-counts)

## [ACSEmailSendMailOperational](ACSEmailSendMailOperational.md)

- [Email Send Request Summary](ACSEmailSendMailOperational.md#email-send-request-summary)

## [ACSEmailStatusUpdateOperational](ACSEmailStatusUpdateOperational.md)

- [Email failed deliveries by recipient ID](ACSEmailStatusUpdateOperational.md#email-failed-deliveries-by-recipient-id)
- [Email Failed Deliveries by Message Id](ACSEmailStatusUpdateOperational.md#email-failed-deliveries-by-message-id)

## [ACSJobRouterIncomingOperations](ACSJobRouterIncomingOperations.md)

- [Job Router operations](ACSJobRouterIncomingOperations.md#job-router-operations)
- [Calculate Job Router operation duration percentiles](ACSJobRouterIncomingOperations.md#calculate-job-router-operation-duration-percentiles)
- [Top 5 IP addresses per Job Router operation](ACSJobRouterIncomingOperations.md#top-5-ip-addresses-per-job-router-operation)
- [Job Router operational errors](ACSJobRouterIncomingOperations.md#job-router-operational-errors)
- [Job Router operation result counts](ACSJobRouterIncomingOperations.md#job-router-operation-result-counts)

## [ACSNetworkTraversalDiagnostics](ACSNetworkTraversalDiagnostics.md)

- [Network Traversal relay session data relayed per identity](ACSNetworkTraversalDiagnostics.md#network-traversal-relay-session-data-relayed-per-identity)
- [Network Traversal relay session duration](ACSNetworkTraversalDiagnostics.md#network-traversal-relay-session-duration)
- [Network Traversal relay session end reason](ACSNetworkTraversalDiagnostics.md#network-traversal-relay-session-end-reason)
- [Network Traversal relay sessions per IP address](ACSNetworkTraversalDiagnostics.md#network-traversal-relay-sessions-per-ip-address)
- [Network Traversal relay session start errors](ACSNetworkTraversalDiagnostics.md#network-traversal-relay-session-start-errors)

## [ACSNetworkTraversalIncomingOperations](ACSNetworkTraversalIncomingOperations.md)

- [Distinct Network Traversal operations](ACSNetworkTraversalIncomingOperations.md#distinct-network-traversal-operations)
- [Calculate Network Traversal operation duration percentiles](ACSNetworkTraversalIncomingOperations.md#calculate-network-traversal-operation-duration-percentiles)
- [Network Traversal operational errors](ACSNetworkTraversalIncomingOperations.md#network-traversal-operational-errors)
- [Network Traversal operation result counts](ACSNetworkTraversalIncomingOperations.md#network-traversal-operation-result-counts)

## [ACSRoomsIncomingOperations](ACSRoomsIncomingOperations.md)

- [Rooms operational errors](ACSRoomsIncomingOperations.md#rooms-operational-errors)
- [Rooms operation result counts](ACSRoomsIncomingOperations.md#rooms-operation-result-counts)
- [Rooms operation summary](ACSRoomsIncomingOperations.md#rooms-operation-summary)

## [ACSSMSIncomingOperations](ACSSMSIncomingOperations.md)

- [List distinct SMS operations](ACSSMSIncomingOperations.md#list-distinct-sms-operations)
- [Calculate SMS operation duration percentiles](ACSSMSIncomingOperations.md#calculate-sms-operation-duration-percentiles)
- [Top 5 IP addresses per SMS operation](ACSSMSIncomingOperations.md#top-5-ip-addresses-per-sms-operation)
- [SMS operational errors](ACSSMSIncomingOperations.md#sms-operational-errors)
- [SMS operation result counts](ACSSMSIncomingOperations.md#sms-operation-result-counts)

## [ADAssessmentRecommendation](ADAssessmentRecommendation.md)

- [AD Recommendations by Focus Area](ADAssessmentRecommendation.md#ad-recommendations-by-focus-area)
- [AD Recommendations by Computer](ADAssessmentRecommendation.md#ad-recommendations-by-computer)
- [AD Recommendations by Forest](ADAssessmentRecommendation.md#ad-recommendations-by-forest)
- [AD Recommendations by Domain](ADAssessmentRecommendation.md#ad-recommendations-by-domain)
- [AD Recommendations by DomainController](ADAssessmentRecommendation.md#ad-recommendations-by-domaincontroller)
- [AD Recommendations by AffectedObjectType](ADAssessmentRecommendation.md#ad-recommendations-by-affectedobjecttype)
- [How many times did each unique AD Recommendation trigger?](ADAssessmentRecommendation.md#how-many-times-did-each-unique-ad-recommendation-trigger)
- [High priority AD Assessment security recommendations](ADAssessmentRecommendation.md#high-priority-ad-assessment-security-recommendations)

## [ADFActivityRun](ADFActivityRun.md)

- [Activity Runs Availability](ADFActivityRun.md#activity-runs-availability)
- [Activity runs latest Status](ADFActivityRun.md#activity-runs-latest-status)

## [ADFPipelineRun](ADFPipelineRun.md)

- [PipelineRuns Availability](ADFPipelineRun.md#pipelineruns-availability)
- [Pipeline runs latest Status](ADFPipelineRun.md#pipeline-runs-latest-status)

## [ADFSSignInLogs](ADFSSignInLogs.md)

- [Top ADFS account lockouts](ADFSSignInLogs.md#top-adfs-account-lockouts)

## [ADFTriggerRun](ADFTriggerRun.md)

- [TriggerRuns Availability](ADFTriggerRun.md#triggerruns-availability)
- [Trigger runs latest Status](ADFTriggerRun.md#trigger-runs-latest-status)

## [ADTDataHistoryOperation](ADTDataHistoryOperation.md)

- [Data History operation failure logs](ADTDataHistoryOperation.md#data-history-operation-failure-logs)
- [Data History egress latency](ADTDataHistoryOperation.md#data-history-egress-latency)

## [ADTDigitalTwinsOperation](ADTDigitalTwinsOperation.md)

- [DigitalTwin Error Summary](ADTDigitalTwinsOperation.md#digitaltwin-error-summary)
- [DigitalTwin API Usage](ADTDigitalTwinsOperation.md#digitaltwin-api-usage)

## [ADTEventRoutesOperation](ADTEventRoutesOperation.md)

- [EventRoutes API Usage](ADTEventRoutesOperation.md#eventroutes-api-usage)

## [ADTModelsOperation](ADTModelsOperation.md)

- [Model Error Summary](ADTModelsOperation.md#model-error-summary)
- [Model API Usage](ADTModelsOperation.md#model-api-usage)

## [ADTQueryOperation](ADTQueryOperation.md)

- [Query Error Summary](ADTQueryOperation.md#query-error-summary)

## [ADXIngestionBatching](ADXIngestionBatching.md)

- [Ingestion batching size](ADXIngestionBatching.md#ingestion-batching-size)
- [Ingestion batching summary](ADXIngestionBatching.md#ingestion-batching-summary)
- [Ingestion batching duration timechart](ADXIngestionBatching.md#ingestion-batching-duration-timechart)

## [ADXTableUsageStatistics](ADXTableUsageStatistics.md)

- [Table usage by number of queries](ADXTableUsageStatistics.md#table-usage-by-number-of-queries)
- [Table usage by application](ADXTableUsageStatistics.md#table-usage-by-application)
- [Table data scanned - top time windows](ADXTableUsageStatistics.md#table-data-scanned---top-time-windows)
- [Table data scanned - top tables](ADXTableUsageStatistics.md#table-data-scanned---top-tables)

## [AEWComputePipelinesLogs](AEWComputePipelinesLogs.md)

- [AEWComputePipelinesLogs get daily tasks count](AEWComputePipelinesLogs.md#aewcomputepipelineslogs-get-daily-tasks-count)
- [AEWComputePipelinesLogs get failed tasks detail](AEWComputePipelinesLogs.md#aewcomputepipelineslogs-get-failed-tasks-detail)
- [AEWComputePipelinesLogs get long running jobs](AEWComputePipelinesLogs.md#aewcomputepipelineslogs-get-long-running-jobs)
- [AEWComputePipelinesLogs get task E2E latency time](AEWComputePipelinesLogs.md#aewcomputepipelineslogs-get-task-e2e-latency-time)

## [AFSAuditLogs](AFSAuditLogs.md)

- [Aggregate operations query](AFSAuditLogs.md#aggregate-operations-query)
- [Unauthorized requests query](AFSAuditLogs.md#unauthorized-requests-query)

## [AGCAccessLogs](AGCAccessLogs.md)

- [Client requests per hour](AGCAccessLogs.md#client-requests-per-hour)
- [5xx HTTP responses per hour](AGCAccessLogs.md#5xx-http-responses-per-hour)
- [4xx HTTP responses per hour](AGCAccessLogs.md#4xx-http-responses-per-hour)

## [AGSGrafanaLoginEvents](AGSGrafanaLoginEvents.md)

- [Show login error events](AGSGrafanaLoginEvents.md#show-login-error-events)

## [AHDSDicomAuditLogs](AHDSDicomAuditLogs.md)

- [DICOM privileged operations](AHDSDicomAuditLogs.md#dicom-privileged-operations)

## [AHDSDicomDiagnosticLogs](AHDSDicomDiagnosticLogs.md)

- [Log count per log starting with Dicom100 error code and CorrelationId](AHDSDicomDiagnosticLogs.md#log-count-per-log-starting-with-dicom100-error-code-and-correlationid)

## [AHDSMedTechDiagnosticLogs](AHDSMedTechDiagnosticLogs.md)

- [Most recent actionable MedTech logs](AHDSMedTechDiagnosticLogs.md#most-recent-actionable-medtech-logs)
- [Log count per MedTech log or exception type](AHDSMedTechDiagnosticLogs.md#log-count-per-medtech-log-or-exception-type)
- [MedTech healthcheck exceptions](AHDSMedTechDiagnosticLogs.md#medtech-healthcheck-exceptions)
- [MedTech normalization stage logs](AHDSMedTechDiagnosticLogs.md#medtech-normalization-stage-logs)
- [MedTech FHIR conversion stage logs](AHDSMedTechDiagnosticLogs.md#medtech-fhir-conversion-stage-logs)

## [AMSKeyDeliveryRequests](AMSKeyDeliveryRequests.md)

- [Key delivery successful request count by key type](AMSKeyDeliveryRequests.md#key-delivery-successful-request-count-by-key-type)
- [Key delivery failed requests](AMSKeyDeliveryRequests.md#key-delivery-failed-requests)
- [Key delivery requests latency at 95 and 99 percentiles](AMSKeyDeliveryRequests.md#key-delivery-requests-latency-at-95-and-99-percentiles)

## [AMSLiveEventOperations](AMSLiveEventOperations.md)

- [Live event ingest discontinuity operation count](AMSLiveEventOperations.md#live-event-ingest-discontinuity-operation-count)
- [Live event error operations](AMSLiveEventOperations.md#live-event-error-operations)

## [AMSMediaAccountHealth](AMSMediaAccountHealth.md)

- [Media account health events](AMSMediaAccountHealth.md#media-account-health-events)

## [AMSStreamingEndpointRequests](AMSStreamingEndpointRequests.md)

- [Streaming endpoint successful request count by client IP](AMSStreamingEndpointRequests.md#streaming-endpoint-successful-request-count-by-client-ip)
- [Streaming endpoint informational requests](AMSStreamingEndpointRequests.md#streaming-endpoint-informational-requests)

## [AOIDatabaseQuery](AOIDatabaseQuery.md)

- [Queries executed by a user on dataproduct](AOIDatabaseQuery.md#queries-executed-by-a-user-on-dataproduct)

## [AOIDigestion](AOIDigestion.md)

- [Row digestion errors](AOIDigestion.md#row-digestion-errors)
- [Failed file digestion by source](AOIDigestion.md#failed-file-digestion-by-source)

## [AOIStorage](AOIStorage.md)

- [Ingestion operation on storage](AOIStorage.md#ingestion-operation-on-storage)
- [Delete operation on storage](AOIStorage.md#delete-operation-on-storage)
- [Read operation on storage](AOIStorage.md#read-operation-on-storage)

## [ASCDeviceEvents](ASCDeviceEvents.md)

- [Azure Sphere device authentication and attestation failures](ASCDeviceEvents.md#azure-sphere-device-authentication-and-attestation-failures)
- [Azure Sphere device events timeline](ASCDeviceEvents.md#azure-sphere-device-events-timeline)
- [Azure Sphere device heartbeat events timechart](ASCDeviceEvents.md#azure-sphere-device-heartbeat-events-timechart)
- [Azure Sphere devices not updated to latest OS](ASCDeviceEvents.md#azure-sphere-devices-not-updated-to-latest-os)
- [Azure Sphere device telemetry events summary](ASCDeviceEvents.md#azure-sphere-device-telemetry-events-summary)

## [ASRJobs](ASRJobs.md)

- [Get all test failover jobs run](ASRJobs.md#get-all-test-failover-jobs-run)

## [ASRReplicatedItems](ASRReplicatedItems.md)

- [Get replication health status history](ASRReplicatedItems.md#get-replication-health-status-history)

## [ASimDnsActivityLogs](ASimDnsActivityLogs.md)

- [Count DNS failures for a source by source and type](ASimDnsActivityLogs.md#count-dns-failures-for-a-source-by-source-and-type)
- [Identify excessive query for a nonexistent domain by a source](ASimDnsActivityLogs.md#identify-excessive-query-for-a-nonexistent-domain-by-a-source)

## [AVNMConnectivityConfigurationChange](AVNMConnectivityConfigurationChange.md)

- [Recent connectivity configuration changes](AVNMConnectivityConfigurationChange.md#recent-connectivity-configuration-changes)
- [Recent failed connectivity configuration changes](AVNMConnectivityConfigurationChange.md#recent-failed-connectivity-configuration-changes)

## [AVNMIPAMPoolAllocationChange](AVNMIPAMPoolAllocationChange.md)

- [AVNM IPAM pool allocation changes](AVNMIPAMPoolAllocationChange.md#avnm-ipam-pool-allocation-changes)
- [Failed AVNM IPAM pool allocation changes](AVNMIPAMPoolAllocationChange.md#failed-avnm-ipam-pool-allocation-changes)

## [AVNMNetworkGroupMembershipChange](AVNMNetworkGroupMembershipChange.md)

- [Get recent Network Group Membership changes](AVNMNetworkGroupMembershipChange.md#get-recent-network-group-membership-changes)
- [Failed Network Group Membership Changes](AVNMNetworkGroupMembershipChange.md#failed-network-group-membership-changes)

## [AVNMRuleCollectionChange](AVNMRuleCollectionChange.md)

- [Get recent security admin rule collection changes](AVNMRuleCollectionChange.md#get-recent-security-admin-rule-collection-changes)
- [Get recent failed security admin rule collection changes](AVNMRuleCollectionChange.md#get-recent-failed-security-admin-rule-collection-changes)

## [AVSSyslog](AVSSyslog.md)

- [Get DNS failures](AVSSyslog.md#get-dns-failures)
- [Get distributed Firewall logs](AVSSyslog.md#get-distributed-firewall-logs)
- [Get audit events for VM created](AVSSyslog.md#get-audit-events-for-vm-created)
- [Get audit events for VM deleted](AVSSyslog.md#get-audit-events-for-vm-deleted)
- [Get audit events for VM powered on](AVSSyslog.md#get-audit-events-for-vm-powered-on)
- [Get audit events for VM disconnected](AVSSyslog.md#get-audit-events-for-vm-disconnected)
- [Get audit events for VM rebooted](AVSSyslog.md#get-audit-events-for-vm-rebooted)
- [Get audit events for VM migrated](AVSSyslog.md#get-audit-events-for-vm-migrated)
- [Get audit events for host added](AVSSyslog.md#get-audit-events-for-host-added)
- [Get audit events for host shutdown](AVSSyslog.md#get-audit-events-for-host-shutdown)
- [Get audit events for host enter maintenance mode](AVSSyslog.md#get-audit-events-for-host-enter-maintenance-mode)
- [Get audit events for host exit maintenance mode](AVSSyslog.md#get-audit-events-for-host-exit-maintenance-mode)
- [Get audit events for host connected](AVSSyslog.md#get-audit-events-for-host-connected)
- [Get audit events for host connection lost](AVSSyslog.md#get-audit-events-for-host-connection-lost)
- [Get audit events for cluster](AVSSyslog.md#get-audit-events-for-cluster)
- [Get audit events count for NSX](AVSSyslog.md#get-audit-events-count-for-nsx)
- [Get audit events count for vCenter](AVSSyslog.md#get-audit-events-count-for-vcenter)
- [Get audit events for role added](AVSSyslog.md#get-audit-events-for-role-added)
- [Get AVS events with severity of Info](AVSSyslog.md#get-avs-events-with-severity-of-info)

## [AWSCloudTrail](AWSCloudTrail.md)

- [New users per region](AWSCloudTrail.md#new-users-per-region)
- [All AWS CloudTrail events](AWSCloudTrail.md#all-aws-cloudtrail-events)
- [AWSCT for user](AWSCloudTrail.md#awsct-for-user)
- [AWS console sign in](AWSCloudTrail.md#aws-console-sign-in)

## [AWSGuardDuty](AWSGuardDuty.md)

- [High severity findings](AWSGuardDuty.md#high-severity-findings)

## [AWSVPCFlow](AWSVPCFlow.md)

- [Rejected IPv4 actions](AWSVPCFlow.md#rejected-ipv4-actions)

## [AZFWApplicationRule](AZFWApplicationRule.md)

- [Application rule logs](AZFWApplicationRule.md#application-rule-logs)
- [All firewall decisions](AZFWApplicationRule.md#all-firewall-decisions)

## [AZFWDnsQuery](AZFWDnsQuery.md)

- [DNS proxy logs](AZFWDnsQuery.md#dns-proxy-logs)

## [AZFWFatFlow](AZFWFatFlow.md)

- [Azure Firewall Top Flow Logs](AZFWFatFlow.md#azure-firewall-top-flow-logs)

## [AZFWFlowTrace](AZFWFlowTrace.md)

- [Azure Firewall flow trace logs](AZFWFlowTrace.md#azure-firewall-flow-trace-logs)

## [AZFWIdpsSignature](AZFWIdpsSignature.md)

- [IDPS event logs](AZFWIdpsSignature.md#idps-event-logs)
- [All firewall decisions](AZFWIdpsSignature.md#all-firewall-decisions)

## [AZFWInternalFqdnResolutionFailure](AZFWInternalFqdnResolutionFailure.md)

- [Internal FQDN resolution failures](AZFWInternalFqdnResolutionFailure.md#internal-fqdn-resolution-failures)

## [AZFWNatRule](AZFWNatRule.md)

- [DNAT rule logs](AZFWNatRule.md#dnat-rule-logs)
- [All firewall decisions](AZFWNatRule.md#all-firewall-decisions)

## [AZFWNetworkRule](AZFWNetworkRule.md)

- [Network rule logs](AZFWNetworkRule.md#network-rule-logs)
- [All firewall decisions](AZFWNetworkRule.md#all-firewall-decisions)

## [AZFWThreatIntel](AZFWThreatIntel.md)

- [Threat intelligence logs](AZFWThreatIntel.md#threat-intelligence-logs)
- [All firewall decisions](AZFWThreatIntel.md#all-firewall-decisions)

## [AZKVAuditLogs](AZKVAuditLogs.md)

- [Are there any failures?](AZKVAuditLogs.md#are-there-any-failures)
- [Are there any slow requests?](AZKVAuditLogs.md#are-there-any-slow-requests)
- [How active has this KeyVault been?](AZKVAuditLogs.md#how-active-has-this-keyvault-been)
- [How fast is this KeyVault serving requests?](AZKVAuditLogs.md#how-fast-is-this-keyvault-serving-requests)
- [What changes occurred last month?](AZKVAuditLogs.md#what-changes-occurred-last-month)
- [Who is calling this KeyVault?](AZKVAuditLogs.md#who-is-calling-this-keyvault)

## [AZMSHybridConnectionsEvents](AZMSHybridConnectionsEvents.md)

- [Publish HTTP send data for hybrid connection](AZMSHybridConnectionsEvents.md#publish-http-send-data-for-hybrid-connection)

## [AZMSOperationalLogs](AZMSOperationalLogs.md)

- [Publish success data for topics](AZMSOperationalLogs.md#publish-success-data-for-topics)
- [Publish failures for subscription](AZMSOperationalLogs.md#publish-failures-for-subscription)
- [Publish failures for namespace](AZMSOperationalLogs.md#publish-failures-for-namespace)
- [Publish success data for topics](AZMSOperationalLogs.md#publish-success-data-for-topics)
- [Publish failures for Topics](AZMSOperationalLogs.md#publish-failures-for-topics)
- [Publish failures for subscription](AZMSOperationalLogs.md#publish-failures-for-subscription)
- [Publish failures for namespace](AZMSOperationalLogs.md#publish-failures-for-namespace)

## [AZMSRunTimeAuditLogs](AZMSRunTimeAuditLogs.md)

- [Publish successful connection for AMQP protocol](AZMSRunTimeAuditLogs.md#publish-successful-connection-for-amqp-protocol)
- [Publish failed AAD logs](AZMSRunTimeAuditLogs.md#publish-failed-aad-logs)
- [Publish failed SAS logs](AZMSRunTimeAuditLogs.md#publish-failed-sas-logs)
- [Publish failure for send message](AZMSRunTimeAuditLogs.md#publish-failure-for-send-message)
- [Publish failure for Namespace](AZMSRunTimeAuditLogs.md#publish-failure-for-namespace)
- [[Classic] Errors in the last 7 days](AZMSRunTimeAuditLogs.md#classic-errors-in-the-last-7-days)
- [Publish successful connection for AMQP protocol](AZMSRunTimeAuditLogs.md#publish-successful-connection-for-amqp-protocol)
- [Publish failures for send message](AZMSRunTimeAuditLogs.md#publish-failures-for-send-message)
- [Publish failure for namespace](AZMSRunTimeAuditLogs.md#publish-failure-for-namespace)
- [Publish failed AAD logs](AZMSRunTimeAuditLogs.md#publish-failed-aad-logs)
- [Publish failed SAS logs](AZMSRunTimeAuditLogs.md#publish-failed-sas-logs)

## [AZMSVnetConnectionEvents](AZMSVnetConnectionEvents.md)

- [Publish deny connection by namespace](AZMSVnetConnectionEvents.md#publish-deny-connection-by-namespace)
- [Publish namespace vnet data](AZMSVnetConnectionEvents.md#publish-namespace-vnet-data)
- [Publish deny connection by namespace](AZMSVnetConnectionEvents.md#publish-deny-connection-by-namespace)
- [Publish virtual network events by namespace](AZMSVnetConnectionEvents.md#publish-virtual-network-events-by-namespace)
- [Publish deny connection by namespace](AZMSVnetConnectionEvents.md#publish-deny-connection-by-namespace)
- [Publish virtual network events by namespace](AZMSVnetConnectionEvents.md#publish-virtual-network-events-by-namespace)

## [AddonAzureBackupJobs](AddonAzureBackupJobs.md)

- [Distribution of Backup Jobs by Status](AddonAzureBackupJobs.md#distribution-of-backup-jobs-by-status)
- [Distribution of Restore Jobs by Status](AddonAzureBackupJobs.md#distribution-of-restore-jobs-by-status)
- [All Successful Jobs](AddonAzureBackupJobs.md#all-successful-jobs)
- [All Failed Jobs](AddonAzureBackupJobs.md#all-failed-jobs)

## [AddonAzureBackupStorage](AddonAzureBackupStorage.md)

- [Trend of total Cloud Storage consumed](AddonAzureBackupStorage.md#trend-of-total-cloud-storage-consumed)

## [AegDataPlaneRequests](AegDataPlaneRequests.md)

- [Unique unauthorized or forbidden client IP addresses](AegDataPlaneRequests.md#unique-unauthorized-or-forbidden-client-ip-addresses)

## [AegDeliveryFailureLogs](AegDeliveryFailureLogs.md)

- [Delivery failures by topic and error](AegDeliveryFailureLogs.md#delivery-failures-by-topic-and-error)
- [Delivery failures by topic and error](AegDeliveryFailureLogs.md#delivery-failures-by-topic-and-error)
- [Delivery failures by domain and error](AegDeliveryFailureLogs.md#delivery-failures-by-domain-and-error)
- [Topics Average Delivery Latency](AegDeliveryFailureLogs.md#topics-average-delivery-latency)
- [Domains Average Delivery Latency ](AegDeliveryFailureLogs.md#domains-average-delivery-latency)

## [AegPublishFailureLogs](AegPublishFailureLogs.md)

- [Publish failures by topic and error](AegPublishFailureLogs.md#publish-failures-by-topic-and-error)
- [Publish failures by topic and error](AegPublishFailureLogs.md#publish-failures-by-topic-and-error)
- [Publish failures by domain and error](AegPublishFailureLogs.md#publish-failures-by-domain-and-error)

## [AgriFoodApplicationAuditLogs](AgriFoodApplicationAuditLogs.md)

- [Failed authorization](AgriFoodApplicationAuditLogs.md#failed-authorization)

## [AgriFoodFarmManagementLogs](AgriFoodFarmManagementLogs.md)

- [Status of farm management operations for a farmer](AgriFoodFarmManagementLogs.md#status-of-farm-management-operations-for-a-farmer)
- [Status of all operations for a farmer](AgriFoodFarmManagementLogs.md#status-of-all-operations-for-a-farmer)
- [Usage trend for top 100 farmers based on the operations performed](AgriFoodFarmManagementLogs.md#usage-trend-for-top-100-farmers-based-on-the-operations-performed)

## [AgriFoodJobProcessedLogs](AgriFoodJobProcessedLogs.md)

- [Job execution statistics for a farmer](AgriFoodJobProcessedLogs.md#job-execution-statistics-for-a-farmer)

## [AlertEvidence](AlertEvidence.md)

- [Alerts involving a user](AlertEvidence.md#alerts-involving-a-user)

## [AlertInfo](AlertInfo.md)

- [Alerts by MITRE ATT&CK technique](AlertInfo.md#alerts-by-mitre-attck-technique)

## [AmlComputeClusterEvent](AmlComputeClusterEvent.md)

- [Get cluster events for clusters for specific VM size](AmlComputeClusterEvent.md#get-cluster-events-for-clusters-for-specific-vm-size)
- [Get number of running nodes](AmlComputeClusterEvent.md#get-number-of-running-nodes)
- [Graph of Running and Idle Node instances](AmlComputeClusterEvent.md#graph-of-running-and-idle-node-instances)

## [AmlComputeCpuGpuUtilization](AmlComputeCpuGpuUtilization.md)

- [Plot compute cluster utilization](AmlComputeCpuGpuUtilization.md#plot-compute-cluster-utilization)

## [AmlComputeJobEvent](AmlComputeJobEvent.md)

- [Get failed jobs](AmlComputeJobEvent.md#get-failed-jobs)
- [Get records for a job](AmlComputeJobEvent.md#get-records-for-a-job)
- [Display top 5 longest job runs](AmlComputeJobEvent.md#display-top-5-longest-job-runs)

## [AmlDataSetEvent](AmlDataSetEvent.md)

- [Count datasets reads](AmlDataSetEvent.md#count-datasets-reads)

## [AmlEnvironmentEvent](AmlEnvironmentEvent.md)

- [Request the history of accessing environment](AmlEnvironmentEvent.md#request-the-history-of-accessing-environment)

## [AmlModelsEvent](AmlModelsEvent.md)

- [Found users who accessed models](AmlModelsEvent.md#found-users-who-accessed-models)

## [AmlOnlineEndpointConsoleLog](AmlOnlineEndpointConsoleLog.md)

- [Online endpoint console logs](AmlOnlineEndpointConsoleLog.md#online-endpoint-console-logs)

## [AmlOnlineEndpointEventLog](AmlOnlineEndpointEventLog.md)

- [Online endpoint failure events](AmlOnlineEndpointEventLog.md#online-endpoint-failure-events)

## [AmlOnlineEndpointTrafficLog](AmlOnlineEndpointTrafficLog.md)

- [Online endpoint failed requests](AmlOnlineEndpointTrafficLog.md#online-endpoint-failed-requests)

## [AmlRegistryWriteEventsLog](AmlRegistryWriteEventsLog.md)

- [All WRITE events](AmlRegistryWriteEventsLog.md#all-write-events)

## [Anomalies](Anomalies.md)

- [Get Production Anomalies (last day)](Anomalies.md#get-production-anomalies-last-day)
- [Get Flighting Anomalies (last day)](Anomalies.md#get-flighting-anomalies-last-day)

## [ApiManagementGatewayLogs](ApiManagementGatewayLogs.md)

- [Number of requests](ApiManagementGatewayLogs.md#number-of-requests)
- [Logs of the last 100 calls](ApiManagementGatewayLogs.md#logs-of-the-last-100-calls)
- [Number of calls by APIs](ApiManagementGatewayLogs.md#number-of-calls-by-apis)
- [Bandwidth consumed](ApiManagementGatewayLogs.md#bandwidth-consumed)
- [Request sizes](ApiManagementGatewayLogs.md#request-sizes)
- [Response sizes](ApiManagementGatewayLogs.md#response-sizes)
- [Client TLS versions](ApiManagementGatewayLogs.md#client-tls-versions)
- [Error reasons breakdown](ApiManagementGatewayLogs.md#error-reasons-breakdown)
- [Last 100 failed requests](ApiManagementGatewayLogs.md#last-100-failed-requests)
- [Get failed requests due to issues related to the backend](ApiManagementGatewayLogs.md#get-failed-requests-due-to-issues-related-to-the-backend)
- [Get failed requests due to issues not related to the backend](ApiManagementGatewayLogs.md#get-failed-requests-due-to-issues-not-related-to-the-backend)
- [Overall latency](ApiManagementGatewayLogs.md#overall-latency)
- [Backend latency](ApiManagementGatewayLogs.md#backend-latency)
- [Client latency](ApiManagementGatewayLogs.md#client-latency)
- [Cache hit ratio](ApiManagementGatewayLogs.md#cache-hit-ratio)

## [AppDependencies](AppDependencies.md)

- [Failing dependencies](AppDependencies.md#failing-dependencies)

## [AppEnvSpringAppConsoleLogs](AppEnvSpringAppConsoleLogs.md)

- [Latest Container App first party Spring App errors](AppEnvSpringAppConsoleLogs.md#latest-container-app-first-party-spring-app-errors)

## [AppExceptions](AppExceptions.md)

- [Top 3 browser exceptions](AppExceptions.md#top-3-browser-exceptions)

## [AppPageViews](AppPageViews.md)

- [Page views trend](AppPageViews.md#page-views-trend)
- [Slowest pages](AppPageViews.md#slowest-pages)

## [AppPlatformLogsforSpring](AppPlatformLogsforSpring.md)

- [Show the application logs which contain the "error" or "exception" terms](AppPlatformLogsforSpring.md#show-the-application-logs-which-contain-the-error-or-exception-terms)
- [Show the error and exception number of each application](AppPlatformLogsforSpring.md#show-the-error-and-exception-number-of-each-application)

## [AppPlatformSystemLogs](AppPlatformSystemLogs.md)

- [Show the config server logs](AppPlatformSystemLogs.md#show-the-config-server-logs)
- [Show the service registry logs](AppPlatformSystemLogs.md#show-the-service-registry-logs)
- [Show the Spring Cloud Gateway logs](AppPlatformSystemLogs.md#show-the-spring-cloud-gateway-logs)
- [Show the API portal logs](AppPlatformSystemLogs.md#show-the-api-portal-logs)
- [Show the Application Configuration Service logs](AppPlatformSystemLogs.md#show-the-application-configuration-service-logs)
- [Show the Spring Cloud Gateway operator logs](AppPlatformSystemLogs.md#show-the-spring-cloud-gateway-operator-logs)

## [AppRequests](AppRequests.md)

- [Response time trend](AppRequests.md#response-time-trend)
- [Request count trend](AppRequests.md#request-count-trend)
- [Response time buckets](AppRequests.md#response-time-buckets)
- [Operations performance](AppRequests.md#operations-performance)
- [Top 10 countries by traffic](AppRequests.md#top-10-countries-by-traffic)
- [Failed requests – top 10](AppRequests.md#failed-requests--top-10)
- [Failed operations](AppRequests.md#failed-operations)
- [Exceptions causing request failures](AppRequests.md#exceptions-causing-request-failures)

## [AppServiceAppLogs](AppServiceAppLogs.md)

- [Count app logs by severity](AppServiceAppLogs.md#count-app-logs-by-severity)
- [App logs for each App Service](AppServiceAppLogs.md#app-logs-for-each-app-service)

## [AppServiceAuditLogs](AppServiceAuditLogs.md)

- [Audit Logs relating to unexpected users](AppServiceAuditLogs.md#audit-logs-relating-to-unexpected-users)

## [AppServiceAuthenticationLogs](AppServiceAuthenticationLogs.md)

- [Most recent errors from App Service Authentication](AppServiceAuthenticationLogs.md#most-recent-errors-from-app-service-authentication)
- [Most recent warnings from App Service Authentication](AppServiceAuthenticationLogs.md#most-recent-warnings-from-app-service-authentication)
- [Top 100 most frequent errors and warnings from App Service Authentication](AppServiceAuthenticationLogs.md#top-100-most-frequent-errors-and-warnings-from-app-service-authentication)

## [AppServiceConsoleLogs](AppServiceConsoleLogs.md)

- [Find console logs relating to application startup](AppServiceConsoleLogs.md#find-console-logs-relating-to-application-startup)

## [AppServiceFileAuditLogs](AppServiceFileAuditLogs.md)

- [File Audit Logs relating to a "Delete" operation](AppServiceFileAuditLogs.md#file-audit-logs-relating-to-a-delete-operation)

## [AppServiceHTTPLogs](AppServiceHTTPLogs.md)

- [App Service Health](AppServiceHTTPLogs.md#app-service-health)
- [Failure Categorization](AppServiceHTTPLogs.md#failure-categorization)
- [Response times of requests](AppServiceHTTPLogs.md#response-times-of-requests)
- [Top 5 Clients](AppServiceHTTPLogs.md#top-5-clients)
- [Top 5 Machines](AppServiceHTTPLogs.md#top-5-machines)

## [AutoscaleEvaluationsLog](AutoscaleEvaluationsLog.md)

- [Review Autoscale evaluations](AutoscaleEvaluationsLog.md#review-autoscale-evaluations)

## [AutoscaleScaleActionsLog](AutoscaleScaleActionsLog.md)

- [Display top Autoscale 50 logs](AutoscaleScaleActionsLog.md#display-top-autoscale-50-logs)
- [Autoscale operation status](AutoscaleScaleActionsLog.md#autoscale-operation-status)
- [Autoscale failed operations](AutoscaleScaleActionsLog.md#autoscale-failed-operations)

## [AzureActivity](AzureActivity.md)

- [[Classic] Find In AzureActivity](AzureActivity.md#classic-find-in-azureactivity)
- [Shut down Virtual Machines](AzureActivity.md#shut-down-virtual-machines)
- [Latest 50 logs](AzureActivity.md#latest-50-logs)
- [Operations' status](AzureActivity.md#operations-status)
- [Recent Azure Activity logs](AzureActivity.md#recent-azure-activity-logs)
- [Failed operations](AzureActivity.md#failed-operations)
- [Resources creation](AzureActivity.md#resources-creation)
- [Find In AzureActivity](AzureActivity.md#find-in-azureactivity)
- [Show logs from AzureActivity table](AzureActivity.md#show-logs-from-azureactivity-table)
- [Show logs from AzureActivity table](AzureActivity.md#show-logs-from-azureactivity-table)
- [Display top 50 Activity log events](AzureActivity.md#display-top-50-activity-log-events)
- [Display Activity log Administrative events](AzureActivity.md#display-activity-log-administrative-events)
- [VM creation](AzureActivity.md#vm-creation)
- [Display Activity log events generated from Policy](AzureActivity.md#display-activity-log-events-generated-from-policy)
- [List callers and their associated action in last 48 hours](AzureActivity.md#list-callers-and-their-associated-action-in-last-48-hours)
- [All Azure Activity](AzureActivity.md#all-azure-activity)
- [Azure Activity for user](AzureActivity.md#azure-activity-for-user)
- [Successful key enumaration](AzureActivity.md#successful-key-enumaration)
- [Network Access JIT initiation](AzureActivity.md#network-access-jit-initiation)
- [Azure Activity operation statistics](AzureActivity.md#azure-activity-operation-statistics)

## [AzureAttestationDiagnostics](AzureAttestationDiagnostics.md)

- [Are there any authorization failures?](AzureAttestationDiagnostics.md#are-there-any-authorization-failures)
- [Are there any slow requests?](AzureAttestationDiagnostics.md#are-there-any-slow-requests)
- [How active has this Attestation provider been?](AzureAttestationDiagnostics.md#how-active-has-this-attestation-provider-been)
- [Who is calling this attestation provider?](AzureAttestationDiagnostics.md#who-is-calling-this-attestation-provider)
- [Have there been any changes to attestation policy?](AzureAttestationDiagnostics.md#have-there-been-any-changes-to-attestation-policy)
- [Have there been any errors attempting to configure the attestation policy?](AzureAttestationDiagnostics.md#have-there-been-any-errors-attempting-to-configure-the-attestation-policy)

## [AzureBackupOperations](AzureBackupOperations.md)

- [Get all backup operations](AzureBackupOperations.md#get-all-backup-operations)

## [AzureDiagnostics](AzureDiagnostics.md)

- [Errors in automation jobs](AzureDiagnostics.md#errors-in-automation-jobs)
- [Find logs reporting errors in automation jobs from the last day](AzureDiagnostics.md#find-logs-reporting-errors-in-automation-jobs-from-the-last-day)
- [Azure Automation jobs that are failed, suspended, or stopped](AzureDiagnostics.md#azure-automation-jobs-that-are-failed-suspended-or-stopped)
- [Runbook completed successfully with errors](AzureDiagnostics.md#runbook-completed-successfully-with-errors)
- [View historical job status](AzureDiagnostics.md#view-historical-job-status)
- [Azure Automation jobs that are Completed](AzureDiagnostics.md#azure-automation-jobs-that-are-completed)
- [Successful tasks per job](AzureDiagnostics.md#successful-tasks-per-job)
- [Failed tasks per job](AzureDiagnostics.md#failed-tasks-per-job)
- [Task durations](AzureDiagnostics.md#task-durations)
- [Pool resizes](AzureDiagnostics.md#pool-resizes)
- [Pool resize failures](AzureDiagnostics.md#pool-resize-failures)
- [[Microsoft CDN (classic)] Requests per hour](AzureDiagnostics.md#microsoft-cdn-classic-requests-per-hour)
- [[Microsoft CDN (classic)] Traffic by URL](AzureDiagnostics.md#microsoft-cdn-classic-traffic-by-url)
- [[Microsoft CDN (classic)] 4XX error rate by URL](AzureDiagnostics.md#microsoft-cdn-classic-4xx-error-rate-by-url)
- [[Microsoft CDN (classic)] Request errors by user agent](AzureDiagnostics.md#microsoft-cdn-classic-request-errors-by-user-agent)
- [[Microsoft CDN (classic)] Top 10 URL request count](AzureDiagnostics.md#microsoft-cdn-classic-top-10-url-request-count)
- [[Microsoft CDN (classic)] Unique IP request count](AzureDiagnostics.md#microsoft-cdn-classic-unique-ip-request-count)
- [[Microsoft CDN (classic)] Top 10 client IPs and HTTP versions](AzureDiagnostics.md#microsoft-cdn-classic-top-10-client-ips-and-http-versions)
- [[Azure Front Door Standard/Premium] Top 20 blocked clients by IP and rule](AzureDiagnostics.md#azure-front-door-standardpremium-top-20-blocked-clients-by-ip-and-rule)
- [[Azure Front Door Standard/Premium] Requests to origin by route](AzureDiagnostics.md#azure-front-door-standardpremium-requests-to-origin-by-route)
- [[Azure Front Door Standard/Premium] Request errors by user agent](AzureDiagnostics.md#azure-front-door-standardpremium-request-errors-by-user-agent)
- [[Azure Front Door Standard/Premium] Top 10 client IPs and http versions](AzureDiagnostics.md#azure-front-door-standardpremium-top-10-client-ips-and-http-versions)
- [[Azure Front Door Standard/Premium] Request errors by host and path](AzureDiagnostics.md#azure-front-door-standardpremium-request-errors-by-host-and-path)
- [[Azure Front Door Standard/Premium] Firewall blocked request count per hour](AzureDiagnostics.md#azure-front-door-standardpremium-firewall-blocked-request-count-per-hour)
- [[Azure Front Door Standard/Premium] Firewall request count by host, path, rule, and action](AzureDiagnostics.md#azure-front-door-standardpremium-firewall-request-count-by-host-path-rule-and-action)
- [[Azure Front Door Standard/Premium] Requests per hour](AzureDiagnostics.md#azure-front-door-standardpremium-requests-per-hour)
- [[Azure Front Door Standard/Premium] Top 10 URL request count](AzureDiagnostics.md#azure-front-door-standardpremium-top-10-url-request-count)
- [ [Azure Front Door Standard/Premium] Top 10 URL request count ](AzureDiagnostics.md#azure-front-door-standardpremium-top-10-url-request-count)
- [[Azure Front Door Standard/Premium]  Unique IP request count](AzureDiagnostics.md#azure-front-door-standardpremium--unique-ip-request-count)
- [Find In AzureDiagnostics](AzureDiagnostics.md#find-in-azurediagnostics)
- [Execution time exceeding a threshold](AzureDiagnostics.md#execution-time-exceeding-a-threshold)
- [Show the Slowest queries ](AzureDiagnostics.md#show-the-slowest-queries)
- [Show Query's statistics](AzureDiagnostics.md#show-querys-statistics)
- [Review audit log events in GENERAL class ](AzureDiagnostics.md#review-audit-log-events-in-general-class)
- [Review audit log events in CONNECTION class ](AzureDiagnostics.md#review-audit-log-events-in-connection-class)
- [Execution time exceeding a threshold](AzureDiagnostics.md#execution-time-exceeding-a-threshold)
- [Show the Slowest queries ](AzureDiagnostics.md#show-the-slowest-queries)
- [Show Query's statistics](AzureDiagnostics.md#show-querys-statistics)
- [Review audit log events in GENERAL class ](AzureDiagnostics.md#review-audit-log-events-in-general-class)
- [Review audit log events in CONNECTION class ](AzureDiagnostics.md#review-audit-log-events-in-connection-class)
- [Autovacuum events](AzureDiagnostics.md#autovacuum-events)
- [Server restarts](AzureDiagnostics.md#server-restarts)
- [Find Errors](AzureDiagnostics.md#find-errors)
- [Unauthorized connections](AzureDiagnostics.md#unauthorized-connections)
- [Deadlocks](AzureDiagnostics.md#deadlocks)
- [Lock contention](AzureDiagnostics.md#lock-contention)
- [Audit logs](AzureDiagnostics.md#audit-logs)
- [Audit logs for table(s) and event type(s)](AzureDiagnostics.md#audit-logs-for-tables-and-event-types)
- [Queries with execution time exceeding a threshold](AzureDiagnostics.md#queries-with-execution-time-exceeding-a-threshold)
- [Slowest queries](AzureDiagnostics.md#slowest-queries)
- [Query statistics](AzureDiagnostics.md#query-statistics)
- [Execution count trends](AzureDiagnostics.md#execution-count-trends)
- [Top wait events](AzureDiagnostics.md#top-wait-events)
- [Wait event trends](AzureDiagnostics.md#wait-event-trends)
- [Connectvity errors](AzureDiagnostics.md#connectvity-errors)
- [Devices with most throttling errors](AzureDiagnostics.md#devices-with-most-throttling-errors)
- [Dead endpoints](AzureDiagnostics.md#dead-endpoints)
- [Error summary](AzureDiagnostics.md#error-summary)
- [Recently connected devices](AzureDiagnostics.md#recently-connected-devices)
- [SDK version of devices](AzureDiagnostics.md#sdk-version-of-devices)
- [Consumed RU/s in last 24 hours](AzureDiagnostics.md#consumed-rus-in-last-24-hours)
- [Collections with throttles (429) in past 24 hours](AzureDiagnostics.md#collections-with-throttles-429-in-past-24-hours)
- [Top operations by consumed Request Units (RUs) in last 24 hours](AzureDiagnostics.md#top-operations-by-consumed-request-units-rus-in-last-24-hours)
- [Top logical partition keys by storage](AzureDiagnostics.md#top-logical-partition-keys-by-storage)
- [[Classic] Duration of Capture failure](AzureDiagnostics.md#classic-duration-of-capture-failure)
- [[Classic] Join request for client](AzureDiagnostics.md#classic-join-request-for-client)
- [[Classic] Access to keyvault - key not found](AzureDiagnostics.md#classic-access-to-keyvault---key-not-found)
- [[Classic] Operation performed with keyvault](AzureDiagnostics.md#classic-operation-performed-with-keyvault)
- [Errors in the last 7 days](AzureDiagnostics.md#errors-in-the-last-7-days)
- [Duration of Capture failure](AzureDiagnostics.md#duration-of-capture-failure)
- [Join request for client](AzureDiagnostics.md#join-request-for-client)
- [Access to keyvault - key not found](AzureDiagnostics.md#access-to-keyvault---key-not-found)
- [Operation performed with keyvault](AzureDiagnostics.md#operation-performed-with-keyvault)
- [[Classic] How active has this KeyVault been?](AzureDiagnostics.md#classic-how-active-has-this-keyvault-been)
- [[Classic] Who is calling this KeyVault?](AzureDiagnostics.md#classic-who-is-calling-this-keyvault)
- [[Classic] Are there any slow requests?](AzureDiagnostics.md#classic-are-there-any-slow-requests)
- [[Classic] How fast is this KeyVault serving requests?](AzureDiagnostics.md#classic-how-fast-is-this-keyvault-serving-requests)
- [[Classic] Are there any failures?](AzureDiagnostics.md#classic-are-there-any-failures)
- [[Classic] What changes occurred last month?](AzureDiagnostics.md#classic-what-changes-occurred-last-month)
- [[Classic] List all input deserialization errors](AzureDiagnostics.md#classic-list-all-input-deserialization-errors)
- [[Classic] Find In AzureDiagnostics](AzureDiagnostics.md#classic-find-in-azurediagnostics)
- [Total billable executions](AzureDiagnostics.md#total-billable-executions)
- [Logic App execution distribution by workflows](AzureDiagnostics.md#logic-app-execution-distribution-by-workflows)
- [Logic App execution distribution by status](AzureDiagnostics.md#logic-app-execution-distribution-by-status)
- [Triggered failures count](AzureDiagnostics.md#triggered-failures-count)
- [Requests per hour](AzureDiagnostics.md#requests-per-hour)
- [Non-SSL requests per hour](AzureDiagnostics.md#non-ssl-requests-per-hour)
- [Failed requests per hour](AzureDiagnostics.md#failed-requests-per-hour)
- [Errors by user agent](AzureDiagnostics.md#errors-by-user-agent)
- [Errors by URI](AzureDiagnostics.md#errors-by-uri)
- [Top 10 Client IPs](AzureDiagnostics.md#top-10-client-ips)
- [Top HTTP versions](AzureDiagnostics.md#top-http-versions)
- [Network security events](AzureDiagnostics.md#network-security-events)
- [Requests per hour](AzureDiagnostics.md#requests-per-hour)
- [Forwarded backend requests by routing rule](AzureDiagnostics.md#forwarded-backend-requests-by-routing-rule)
- [Request errors by host and path](AzureDiagnostics.md#request-errors-by-host-and-path)
- [Request errors by user agent](AzureDiagnostics.md#request-errors-by-user-agent)
- [Top 10 client IPs and http versions](AzureDiagnostics.md#top-10-client-ips-and-http-versions)
- [Firewall blocked request count per hour](AzureDiagnostics.md#firewall-blocked-request-count-per-hour)
- [Top 20 blocked clients by IP and rule](AzureDiagnostics.md#top-20-blocked-clients-by-ip-and-rule)
- [Firewall request count by host, path, rule, and action](AzureDiagnostics.md#firewall-request-count-by-host-path-rule-and-action)
- [Application rule log data](AzureDiagnostics.md#application-rule-log-data)
- [Network rule log data](AzureDiagnostics.md#network-rule-log-data)
- [Threat Intelligence rule log data](AzureDiagnostics.md#threat-intelligence-rule-log-data)
- [Azure Firewall log data](AzureDiagnostics.md#azure-firewall-log-data)
- [Azure Firewall DNS proxy log data](AzureDiagnostics.md#azure-firewall-dns-proxy-log-data)
- [BGP route table](AzureDiagnostics.md#bgp-route-table)
- [BGP informational messages](AzureDiagnostics.md#bgp-informational-messages)
- [Endpoints with monitoring Status down](AzureDiagnostics.md#endpoints-with-monitoring-status-down)
- [Successful P2S connections](AzureDiagnostics.md#successful-p2s-connections)
- [Failed P2S connections](AzureDiagnostics.md#failed-p2s-connections)
- [Gateway configuration changes](AzureDiagnostics.md#gateway-configuration-changes)
- [S2S tunnel connet/disconnect events](AzureDiagnostics.md#s2s-tunnel-connetdisconnect-events)
- [BGP route updates](AzureDiagnostics.md#bgp-route-updates)
- [Show logs from AzureDiagnostics table](AzureDiagnostics.md#show-logs-from-azurediagnostics-table)
- [Failed backup jobs](AzureDiagnostics.md#failed-backup-jobs)
- [[Classic] List Management operations](AzureDiagnostics.md#classic-list-management-operations)
- [[Classic] Error Summary](AzureDiagnostics.md#classic-error-summary)
- [[Classic] Keyvault access attempt - key not found](AzureDiagnostics.md#classic-keyvault-access-attempt---key-not-found)
- [[Classic] AutoDeleted entities](AzureDiagnostics.md#classic-autodeleted-entities)
- [[Classic] Keyvault performed operational](AzureDiagnostics.md#classic-keyvault-performed-operational)
- [Management operations in the last 7 days](AzureDiagnostics.md#management-operations-in-the-last-7-days)
- [Errors summary](AzureDiagnostics.md#errors-summary)
- [Keyvault access attempt - key not found](AzureDiagnostics.md#keyvault-access-attempt---key-not-found)
- [AutoDeleted entities](AzureDiagnostics.md#autodeleted-entities)
- [Keyvault performed operational](AzureDiagnostics.md#keyvault-performed-operational)
- [Storage on managed instances above 90%](AzureDiagnostics.md#storage-on-managed-instances-above-90)
- [CPU utilization treshold above 95% on managed instances](AzureDiagnostics.md#cpu-utilization-treshold-above-95-on-managed-instances)
- [Display all active intelligent insights](AzureDiagnostics.md#display-all-active-intelligent-insights)
- [Wait stats](AzureDiagnostics.md#wait-stats)
- [List all input data errors](AzureDiagnostics.md#list-all-input-data-errors)
- [List all input deserialization errors](AzureDiagnostics.md#list-all-input-deserialization-errors)
- [List all InvalidInputTimeStamp errors](AzureDiagnostics.md#list-all-invalidinputtimestamp-errors)
- [List all InvalidInputTimeStampKey errors](AzureDiagnostics.md#list-all-invalidinputtimestampkey-errors)
- [Events that arrived late](AzureDiagnostics.md#events-that-arrived-late)
- [Events that arrived early](AzureDiagnostics.md#events-that-arrived-early)
- [Events that arrived out of order](AzureDiagnostics.md#events-that-arrived-out-of-order)
- [All output data errors](AzureDiagnostics.md#all-output-data-errors)
- [List all RequiredColumnMissing errors](AzureDiagnostics.md#list-all-requiredcolumnmissing-errors)
- [List all ColumnNameInvalid errors](AzureDiagnostics.md#list-all-columnnameinvalid-errors)
- [List all TypeConversionError errors](AzureDiagnostics.md#list-all-typeconversionerror-errors)
- [List all RecordExceededSizeLimit errors](AzureDiagnostics.md#list-all-recordexceededsizelimit-errors)
- [List all DuplicateKey errors](AzureDiagnostics.md#list-all-duplicatekey-errors)
- [All logs with level "Error"](AzureDiagnostics.md#all-logs-with-level-error)
- [Operations that have "Failed"](AzureDiagnostics.md#operations-that-have-failed)
- [Output Throttling logs (Cosmos DB, Power BI, Event Hubs)](AzureDiagnostics.md#output-throttling-logs-cosmos-db-power-bi-event-hubs)
- [Transient input and output errors](AzureDiagnostics.md#transient-input-and-output-errors)
- [Summary of all data errors in the last 7 days](AzureDiagnostics.md#summary-of-all-data-errors-in-the-last-7-days)
- [Summary of all errors in the last 7 days](AzureDiagnostics.md#summary-of-all-errors-in-the-last-7-days)
- [Summary of 'Failed' operations in the last 7 days](AzureDiagnostics.md#summary-of-failed-operations-in-the-last-7-days)

## [AzureLoadTestingOperation](AzureLoadTestingOperation.md)

- [Azure load test creation count](AzureLoadTestingOperation.md#azure-load-test-creation-count)
- [Azure load test run creation count](AzureLoadTestingOperation.md#azure-load-test-run-creation-count)

## [AzureMetrics](AzureMetrics.md)

- [Pie chart of HTTP response codes](AzureMetrics.md#pie-chart-of-http-response-codes)
- [Line chart of response times](AzureMetrics.md#line-chart-of-response-times)
- [[Classic] Find In AzureMetrics](AzureMetrics.md#classic-find-in-azuremetrics)
- [Latest metrics](AzureMetrics.md#latest-metrics)
- [Find In AzureMetrics](AzureMetrics.md#find-in-azuremetrics)
- [ExpressRoute Circuit BitsInPerSecond traffic graph](AzureMetrics.md#expressroute-circuit-bitsinpersecond-traffic-graph)
- [ExpressRoute Circuit BitsOutPerSecond traffic graph](AzureMetrics.md#expressroute-circuit-bitsoutpersecond-traffic-graph)
- [ExpressRoute Circuit ArpAvailablility graph](AzureMetrics.md#expressroute-circuit-arpavailablility-graph)
- [ExpressRoute Circuit BGP availability](AzureMetrics.md#expressroute-circuit-bgp-availability)
- [Avg CPU usage](AzureMetrics.md#avg-cpu-usage)
- [Performance troubleshooting](AzureMetrics.md#performance-troubleshooting)
- [Loading Data](AzureMetrics.md#loading-data)
- [P2S connection count](AzureMetrics.md#p2s-connection-count)
- [P2S bandwidth utilization](AzureMetrics.md#p2s-bandwidth-utilization)
- [Gateway throughput](AzureMetrics.md#gateway-throughput)
- [Show logs from AzureMetrics table](AzureMetrics.md#show-logs-from-azuremetrics-table)
- [Show logs from AzureMetrics table](AzureMetrics.md#show-logs-from-azuremetrics-table)
- [Cluster availability (KeepAlive)](AzureMetrics.md#cluster-availability-keepalive)

## [CCFApplicationLogs](CCFApplicationLogs.md)

- [CCF application errors](CCFApplicationLogs.md#ccf-application-errors)

## [CHSMManagementAuditLogs](CHSMManagementAuditLogs.md)

- [Aggregate operations query](CHSMManagementAuditLogs.md#aggregate-operations-query)
- [Failed operations count](CHSMManagementAuditLogs.md#failed-operations-count)
- [Operations per user](CHSMManagementAuditLogs.md#operations-per-user)

## [CIEventsAudit](CIEventsAudit.md)

- [CIEventsAudit - API response codes line chart](CIEventsAudit.md#cieventsaudit---api-response-codes-line-chart)
- [CIEventsAudit - result type ClientError](CIEventsAudit.md#cieventsaudit---result-type-clienterror)
- [CIEventsAudit - security level Error](CIEventsAudit.md#cieventsaudit---security-level-error)
- [CIEvents - all events for a specific correlation id](CIEventsAudit.md#cievents---all-events-for-a-specific-correlation-id)
- [CIEventsAudit - all events for a specific instance ID](CIEventsAudit.md#cieventsaudit---all-events-for-a-specific-instance-id)

## [CIEventsOperational](CIEventsOperational.md)

- [CIEventsOperational - event type ApiEvent](CIEventsOperational.md#cieventsoperational---event-type-apievent)
- [CIEventsOperational- event type WorkflowEvent](CIEventsOperational.md#cieventsoperational--event-type-workflowevent)
- [CIEvents - all events for a specific correlation id](CIEventsOperational.md#cievents---all-events-for-a-specific-correlation-id)
- [CIEventsOperational - all events for a specific instance ID](CIEventsOperational.md#cieventsoperational---all-events-for-a-specific-instance-id)

## [CassandraLogs](CassandraLogs.md)

- [Cassandra logs](CassandraLogs.md#cassandra-logs)
- [Cassandra errors or warnings](CassandraLogs.md#cassandra-errors-or-warnings)

## [ChaosStudioExperimentEventLogs](ChaosStudioExperimentEventLogs.md)

- [Failed experiment runs](ChaosStudioExperimentEventLogs.md#failed-experiment-runs)
- [Experiment events on last experiment run](ChaosStudioExperimentEventLogs.md#experiment-events-on-last-experiment-run)

## [CloudAppEvents](CloudAppEvents.md)

- [File name extension change](CloudAppEvents.md#file-name-extension-change)

## [CommonSecurityLog](CommonSecurityLog.md)

- [Palo Alto collector machine usage](CommonSecurityLog.md#palo-alto-collector-machine-usage)
- [Cisco ASA events type usage](CommonSecurityLog.md#cisco-asa-events-type-usage)
- [Device events volume statistics](CommonSecurityLog.md#device-events-volume-statistics)

## [ConfidentialWatchlist](ConfidentialWatchlist.md)

- [Get confidential Watchlist aliases](ConfidentialWatchlist.md#get-confidential-watchlist-aliases)
- [Lookup events using a confidential Watchlist](ConfidentialWatchlist.md#lookup-events-using-a-confidential-watchlist)

## [ConfigurationChange](ConfigurationChange.md)

- [Stopped Windows services ](ConfigurationChange.md#stopped-windows-services)
- [Software changes](ConfigurationChange.md#software-changes)
- [Service changes](ConfigurationChange.md#service-changes)
- [Software change type per computer](ConfigurationChange.md#software-change-type-per-computer)
- [Stopped services](ConfigurationChange.md#stopped-services)
- [Software change count per category](ConfigurationChange.md#software-change-count-per-category)
- [Removed software changes](ConfigurationChange.md#removed-software-changes)

## [ConfigurationData](ConfigurationData.md)

- [Recent stopped auto services](ConfigurationData.md#recent-stopped-auto-services)

## [ContainerAppConsoleLogs](ContainerAppConsoleLogs.md)

- [Latest Container App user errors](ContainerAppConsoleLogs.md#latest-container-app-user-errors)

## [ContainerImageInventory](ContainerImageInventory.md)

- [Image inventory](ContainerImageInventory.md#image-inventory)
- [Find In ContainerImageInventory](ContainerImageInventory.md#find-in-containerimageinventory)

## [ContainerInventory](ContainerInventory.md)

- [Container Lifecycle Information](ContainerInventory.md#container-lifecycle-information)

## [ContainerLog](ContainerLog.md)

- [Find a value in Container Logs Table](ContainerLog.md#find-a-value-in-container-logs-table)
- [Billable Log Data by log-type](ContainerLog.md#billable-log-data-by-log-type)
- [List container logs per namespace](ContainerLog.md#list-container-logs-per-namespace)
- [Find In ContainerLog](ContainerLog.md#find-in-containerlog)

## [ContainerLogV2](ContainerLogV2.md)

- [Find In ContainerLogV2](ContainerLogV2.md#find-in-containerlogv2)

## [ContainerNodeInventory](ContainerNodeInventory.md)

- [Find In ContainerNodeInventory](ContainerNodeInventory.md#find-in-containernodeinventory)

## [ContainerRegistryLoginEvents](ContainerRegistryLoginEvents.md)

- [Show login events reported over the last hour](ContainerRegistryLoginEvents.md#show-login-events-reported-over-the-last-hour)

## [ContainerRegistryRepositoryEvents](ContainerRegistryRepositoryEvents.md)

- [Show registry events reported over the last hour](ContainerRegistryRepositoryEvents.md#show-registry-events-reported-over-the-last-hour)

## [ContainerServiceLog](ContainerServiceLog.md)

- [Find In ContainerServiceLog](ContainerServiceLog.md#find-in-containerservicelog)

## [CoreAzureBackup](CoreAzureBackup.md)

- [Backup Items by Vault and Backup item type](CoreAzureBackup.md#backup-items-by-vault-and-backup-item-type)

## [DCRLogErrors](DCRLogErrors.md)

- [Ingestion and Transformation errors from data collection rules](DCRLogErrors.md#ingestion-and-transformation-errors-from-data-collection-rules)

## [DNSQueryLogs](DNSQueryLogs.md)

- [DNS queries by virtual network and return code](DNSQueryLogs.md#dns-queries-by-virtual-network-and-return-code)

## [DataTransferOperations](DataTransferOperations.md)

- [Discovered object](DataTransferOperations.md#discovered-object)
- [Terminal object state](DataTransferOperations.md#terminal-object-state)

## [DatabricksWorkspaceLogs](DatabricksWorkspaceLogs.md)

- [List all Databricks Diagnostic Settings categories](DatabricksWorkspaceLogs.md#list-all-databricks-diagnostic-settings-categories)

## [DataverseActivity](DataverseActivity.md)

- [Dataverse events filtered by operation type](DataverseActivity.md#dataverse-events-filtered-by-operation-type)

## [DevCenterDiagnosticLogs](DevCenterDiagnosticLogs.md)

- [Failed actions query](DevCenterDiagnosticLogs.md#failed-actions-query)

## [DevCenterResourceOperationLogs](DevCenterResourceOperationLogs.md)

- [Hibernate Unsupported Check](DevCenterResourceOperationLogs.md#hibernate-unsupported-check)

## [DeviceCalendar](DeviceCalendar.md)

- [Exchange Error](DeviceCalendar.md#exchange-error)

## [DeviceCleanup](DeviceCleanup.md)

- [Cleanup Failure](DeviceCleanup.md#cleanup-failure)

## [DeviceHardwareHealth](DeviceHardwareHealth.md)

- [Hardware Minor](DeviceHardwareHealth.md#hardware-minor)
- [Hardware Alert](DeviceHardwareHealth.md#hardware-alert)

## [DeviceHealth](DeviceHealth.md)

- [Software Alert](DeviceHealth.md#software-alert)

## [DeviceSkypeHeartbeat](DeviceSkypeHeartbeat.md)

- [Skype Error](DeviceSkypeHeartbeat.md#skype-error)

## [DeviceTvmSecureConfigurationAssessment](DeviceTvmSecureConfigurationAssessment.md)

- [Devices with antivirus configurations issue](DeviceTvmSecureConfigurationAssessment.md#devices-with-antivirus-configurations-issue)

## [DeviceTvmSoftwareInventory](DeviceTvmSoftwareInventory.md)

- [Unsupported software titles](DeviceTvmSoftwareInventory.md#unsupported-software-titles)

## [DeviceTvmSoftwareVulnerabilities](DeviceTvmSoftwareVulnerabilities.md)

- [Devices affected by a specific vulnerability](DeviceTvmSoftwareVulnerabilities.md#devices-affected-by-a-specific-vulnerability)

## [DnsEvents](DnsEvents.md)

- [Clients Resolving Malicious Domains](DnsEvents.md#clients-resolving-malicious-domains)

## [EGNFailedMqttConnections](EGNFailedMqttConnections.md)

- [Authentication error query](EGNFailedMqttConnections.md#authentication-error-query)

## [EGNMqttDisconnections](EGNMqttDisconnections.md)

- [Disconnections reason query](EGNMqttDisconnections.md#disconnections-reason-query)
- [Session disconnections query](EGNMqttDisconnections.md#session-disconnections-query)

## [EGNSuccessfulMqttConnections](EGNSuccessfulMqttConnections.md)

- [Session connections query](EGNSuccessfulMqttConnections.md#session-connections-query)

## [EmailAttachmentInfo](EmailAttachmentInfo.md)

- [Files from malicious sender](EmailAttachmentInfo.md#files-from-malicious-sender)
- [Emails to external domains with attachments](EmailAttachmentInfo.md#emails-to-external-domains-with-attachments)

## [EmailEvents](EmailEvents.md)

- [Phishing emails from the top 10 sender domains](EmailEvents.md#phishing-emails-from-the-top-10-sender-domains)
- [Emails with malware](EmailEvents.md#emails-with-malware)

## [EmailPostDeliveryEvents](EmailPostDeliveryEvents.md)

- [Post-delivery administrator actions](EmailPostDeliveryEvents.md#post-delivery-administrator-actions)
- [Unremediated post-delivery phishing email detections](EmailPostDeliveryEvents.md#unremediated-post-delivery-phishing-email-detections)
- [Full email processing details](EmailPostDeliveryEvents.md#full-email-processing-details)

## [EmailUrlInfo](EmailUrlInfo.md)

- [URLs in an email](EmailUrlInfo.md#urls-in-an-email)

## [Event](Event.md)

- [Memory usage percentage](Event.md#memory-usage-percentage)
- [Avg node CPU usage percentage](Event.md#avg-node-cpu-usage-percentage)
- [Virtual machines failed](Event.md#virtual-machines-failed)
- [Total virtual machines in a cluster.](Event.md#total-virtual-machines-in-a-cluster)
- [Available volume capacity in a cluster.](Event.md#available-volume-capacity-in-a-cluster)
- [Volume latency](Event.md#volume-latency)
- [Volume IOPS](Event.md#volume-iops)
- [Volume throughput](Event.md#volume-throughput)
- [Cluster node down](Event.md#cluster-node-down)
- [Memory usage percentage](Event.md#memory-usage-percentage)
- [Ingestion latency (end-to-end) timechart - Event table](Event.md#ingestion-latency-end-to-end-timechart---event-table)
- [Show the trend of a selected event](Event.md#show-the-trend-of-a-selected-event)
- [Error event on computer missing security co critical update](Event.md#error-event-on-computer-missing-security-co-critical-update)
- [All Events in the past hour](Event.md#all-events-in-the-past-hour)
- [Events started](Event.md#events-started)
- [Events by event source](Event.md#events-by-event-source)
- [Events by event ID](Event.md#events-by-event-id)
- [Warning events](Event.md#warning-events)
- [Count of warning events](Event.md#count-of-warning-events)
- [Events in OM between 2000 to 3000](Event.md#events-in-om-between-2000-to-3000)
- [Windows Fireawall policy settings](Event.md#windows-fireawall-policy-settings)
- [Windows Fireawall policy settings changed by machines](Event.md#windows-fireawall-policy-settings-changed-by-machines)

## [FailedIngestion](FailedIngestion.md)

- [Failed ingestions by errors](FailedIngestion.md#failed-ingestions-by-errors)
- [Failed ingestions timechart](FailedIngestion.md#failed-ingestions-timechart)
- [Failed Ingestions](FailedIngestion.md#failed-ingestions)

## [FunctionAppLogs](FunctionAppLogs.md)

- [Show application logs from Function Apps](FunctionAppLogs.md#show-application-logs-from-function-apps)
- [Show logs with warnings or exceptions](FunctionAppLogs.md#show-logs-with-warnings-or-exceptions)
- [Error and exception count](FunctionAppLogs.md#error-and-exception-count)
- [Function activity over time](FunctionAppLogs.md#function-activity-over-time)
- [Function results](FunctionAppLogs.md#function-results)
- [Function Error rate](FunctionAppLogs.md#function-error-rate)

## [GCPAuditLogs](GCPAuditLogs.md)

- [PubSub subscription logs with severity info](GCPAuditLogs.md#pubsub-subscription-logs-with-severity-info)

## [Heartbeat](Heartbeat.md)

- [Count heartbeats](Heartbeat.md#count-heartbeats)
- [Last heartbeat of each computer](Heartbeat.md#last-heartbeat-of-each-computer)
- [Ingestion latency (end-to-end) spikes - Heartbeat table](Heartbeat.md#ingestion-latency-end-to-end-spikes---heartbeat-table)
- [Agent latency spikes - Heartbeat table](Heartbeat.md#agent-latency-spikes---heartbeat-table)
- [Recently stopped heartbeats - Heartbeat table](Heartbeat.md#recently-stopped-heartbeats---heartbeat-table)
- [Computers availability today](Heartbeat.md#computers-availability-today)
- [Unavailable computers](Heartbeat.md#unavailable-computers)
- [Availability rate](Heartbeat.md#availability-rate)
- [Not reporting VMs](Heartbeat.md#not-reporting-vms)
- [Computers list](Heartbeat.md#computers-list)
- [Find In Heartbeat](Heartbeat.md#find-in-heartbeat)

## [IdentityDirectoryEvents](IdentityDirectoryEvents.md)

- [Group Membership changed](IdentityDirectoryEvents.md#group-membership-changed)
- [Password change event](IdentityDirectoryEvents.md#password-change-event)

## [IdentityLogonEvents](IdentityLogonEvents.md)

- [LDAP authentication processes with cleartext passwords](IdentityLogonEvents.md#ldap-authentication-processes-with-cleartext-passwords)

## [IdentityQueryEvents](IdentityQueryEvents.md)

- [SAMR queries to Active Directory](IdentityQueryEvents.md#samr-queries-to-active-directory)

## [InsightsMetrics](InsightsMetrics.md)

- [IoT Edge: Device offline or not sending messages upstream at expected rate](InsightsMetrics.md#iot-edge-device-offline-or-not-sending-messages-upstream-at-expected-rate)
- [IoT Edge: Edge Hub queue size over threshold](InsightsMetrics.md#iot-edge-edge-hub-queue-size-over-threshold)
- [Maximum node disk ](InsightsMetrics.md#maximum-node-disk)
- [Prometheus disk read per second per node](InsightsMetrics.md#prometheus-disk-read-per-second-per-node)
- [Find In InsightsMetrics](InsightsMetrics.md#find-in-insightsmetrics)
- [What data is being collected?](InsightsMetrics.md#what-data-is-being-collected)
- [Virtual Machine available memory](InsightsMetrics.md#virtual-machine-available-memory)
- [Chart CPU usage trends by computer](InsightsMetrics.md#chart-cpu-usage-trends-by-computer)
- [Virtual Machine free disk space ](InsightsMetrics.md#virtual-machine-free-disk-space)
- [Track VM Availability using Heartbeat ](InsightsMetrics.md#track-vm-availability-using-heartbeat)
- [Top 10 Virtual Machines by CPU utilization](InsightsMetrics.md#top-10-virtual-machines-by-cpu-utilization)
- [Bottom 10 Free disk space %](InsightsMetrics.md#bottom-10-free-disk-space-)

## [KubeEvents](KubeEvents.md)

- [Kubernetes events](KubeEvents.md#kubernetes-events)
- [Find In KubeEvents](KubeEvents.md#find-in-kubeevents)

## [KubeMonAgentEvents](KubeMonAgentEvents.md)

- [Find In KubeMonAgentEvents](KubeMonAgentEvents.md#find-in-kubemonagentevents)

## [KubeNodeInventory](KubeNodeInventory.md)

- [Avg node CPU usage percentage per minute ](KubeNodeInventory.md#avg-node-cpu-usage-percentage-per-minute)
- [Avg node memory usage percentage per minute](KubeNodeInventory.md#avg-node-memory-usage-percentage-per-minute)
- [Readiness status per node](KubeNodeInventory.md#readiness-status-per-node)
- [Find In KubeNodeInventory](KubeNodeInventory.md#find-in-kubenodeinventory)

## [KubePodInventory](KubePodInventory.md)

- [Pods in crash loop](KubePodInventory.md#pods-in-crash-loop)
- [Pods in pending state](KubePodInventory.md#pods-in-pending-state)
- [Find In KubePodInventory](KubePodInventory.md#find-in-kubepodinventory)

## [KubeServices](KubeServices.md)

- [Find In KubeServices](KubeServices.md#find-in-kubeservices)

## [LAQueryLogs](LAQueryLogs.md)

- [Most Requested ResourceIds](LAQueryLogs.md#most-requested-resourceids)
- [Unauthorized Users](LAQueryLogs.md#unauthorized-users)
- [Throttled Users](LAQueryLogs.md#throttled-users)
- [Request Count by ResponseCode](LAQueryLogs.md#request-count-by-responsecode)
- [Top 10 resource intensive queries](LAQueryLogs.md#top-10-resource-intensive-queries)
- [Top 10 longest time range queries](LAQueryLogs.md#top-10-longest-time-range-queries)

## [LASummaryLogs](LASummaryLogs.md)

- [Bin Rules Query Duration](LASummaryLogs.md#bin-rules-query-duration)

## [LogicAppWorkflowRuntime](LogicAppWorkflowRuntime.md)

- [Count of failed workflow operations from Logic App Workflow Runtime](LogicAppWorkflowRuntime.md#count-of-failed-workflow-operations-from-logic-app-workflow-runtime)

## [MNFDeviceUpdates](MNFDeviceUpdates.md)

- [Find all entries where value is active](MNFDeviceUpdates.md#find-all-entries-where-value-is-active)
- [Find all entries where value is up](MNFDeviceUpdates.md#find-all-entries-where-value-is-up)
- [Find all events of the type VxlanVlanToVniVlan](MNFDeviceUpdates.md#find-all-events-of-the-type-vxlanvlantovnivlan)
- [Find all entries where afisafiname is not of the type L2VPN_EVPN](MNFDeviceUpdates.md#find-all-entries-where-afisafiname-is-not-of-the-type-l2vpn_evpn)
- [Find all entries where network instance name is of the type workload-mgmt](MNFDeviceUpdates.md#find-all-entries-where-network-instance-name-is-of-the-type-workload-mgmt)

## [MNFSystemStateMessageUpdates](MNFSystemStateMessageUpdates.md)

- [Find all errors from Syslog](MNFSystemStateMessageUpdates.md#find-all-errors-from-syslog)

## [MicrosoftDataShareReceivedSnapshotLog](MicrosoftDataShareReceivedSnapshotLog.md)

- [List received snapshots by duration](MicrosoftDataShareReceivedSnapshotLog.md#list-received-snapshots-by-duration)
- [Count failed received snapshots](MicrosoftDataShareReceivedSnapshotLog.md#count-failed-received-snapshots)
- [Frequent errors in received snapshots](MicrosoftDataShareReceivedSnapshotLog.md#frequent-errors-in-received-snapshots)
- [Chart of daily received snapshots](MicrosoftDataShareReceivedSnapshotLog.md#chart-of-daily-received-snapshots)

## [MicrosoftDataShareSentSnapshotLog](MicrosoftDataShareSentSnapshotLog.md)

- [List sent snapshots by duration](MicrosoftDataShareSentSnapshotLog.md#list-sent-snapshots-by-duration)
- [Count failed sent snapshots](MicrosoftDataShareSentSnapshotLog.md#count-failed-sent-snapshots)
- [Frequent errors in sent snapshots](MicrosoftDataShareSentSnapshotLog.md#frequent-errors-in-sent-snapshots)
- [Chart of daily sent snapshots](MicrosoftDataShareSentSnapshotLog.md#chart-of-daily-sent-snapshots)

## [MicrosoftGraphActivityLogs](MicrosoftGraphActivityLogs.md)

- [Frequent users endpoint callers](MicrosoftGraphActivityLogs.md#frequent-users-endpoint-callers)
- [Failed groups endpoint requests](MicrosoftGraphActivityLogs.md#failed-groups-endpoint-requests)

## [MicrosoftPurviewInformationProtection](MicrosoftPurviewInformationProtection.md)

- [Microsoft Purview Information Protection events](MicrosoftPurviewInformationProtection.md#microsoft-purview-information-protection-events)

## [NGXOperationLogs](NGXOperationLogs.md)

- [Show NGINXaaS access logs](NGXOperationLogs.md#show-nginxaas-access-logs)
- [Show NGINXaaS error logs](NGXOperationLogs.md#show-nginxaas-error-logs)

## [NWConnectionMonitorPathResult](NWConnectionMonitorPathResult.md)

- [Path diagnostics](NWConnectionMonitorPathResult.md#path-diagnostics)

## [NWConnectionMonitorTestResult](NWConnectionMonitorTestResult.md)

- [Failed tests](NWConnectionMonitorTestResult.md#failed-tests)
- [Tests performance](NWConnectionMonitorTestResult.md#tests-performance)

## [NetworkSessions](NetworkSessions.md)

- [Get traffic to non standard ports](NetworkSessions.md#get-traffic-to-non-standard-ports)
- [High volume traffic to uncommon domains](NetworkSessions.md#high-volume-traffic-to-uncommon-domains)

## [OEPAirFlowTask](OEPAirFlowTask.md)

- [DAG type vs DAG runs summary statitics](OEPAirFlowTask.md#dag-type-vs-dag-runs-summary-statitics)
- [Correlation IDs of all DAG runs](OEPAirFlowTask.md#correlation-ids-of-all-dag-runs)
- [Logs of a DAG run](OEPAirFlowTask.md#logs-of-a-dag-run)
- [Error logs of a DAG run](OEPAirFlowTask.md#error-logs-of-a-dag-run)

## [OLPSupplyChainEntityOperations](OLPSupplyChainEntityOperations.md)

- [Count of successful warehouse delete requests](OLPSupplyChainEntityOperations.md#count-of-successful-warehouse-delete-requests)

## [OfficeActivity](OfficeActivity.md)

- [All Office Activity](OfficeActivity.md#all-office-activity)
- [Users accessing files](OfficeActivity.md#users-accessing-files)
- [File upload operation](OfficeActivity.md#file-upload-operation)
- [Office activity for user](OfficeActivity.md#office-activity-for-user)
- [Creation of Forward rule](OfficeActivity.md#creation-of-forward-rule)
- [Suspicious file name](OfficeActivity.md#suspicious-file-name)

## [Perf](Perf.md)

- [Non-RDMA activity](Perf.md#non-rdma-activity)
- [RDMA activity](Perf.md#rdma-activity)
- [What data is being collected?](Perf.md#what-data-is-being-collected)
- [Memory and CPU usage](Perf.md#memory-and-cpu-usage)
- [CPU usage trends over the last day](Perf.md#cpu-usage-trends-over-the-last-day)
- [Top 10 computers with the highest disk space](Perf.md#top-10-computers-with-the-highest-disk-space)
- [What data is being collected?](Perf.md#what-data-is-being-collected)
- [Virtual Machine available memory](Perf.md#virtual-machine-available-memory)
- [Chart CPU usage trends](Perf.md#chart-cpu-usage-trends)
- [Virtual Machine free disk space](Perf.md#virtual-machine-free-disk-space)
- [Top 10 Virtual Machines by CPU utilization](Perf.md#top-10-virtual-machines-by-cpu-utilization)
- [Bottom 10 Free disk space %](Perf.md#bottom-10-free-disk-space-)
- [Container CPU](Perf.md#container-cpu)
- [Container memory](Perf.md#container-memory)
- [Instances Avg CPU usage growth from last week](Perf.md#instances-avg-cpu-usage-growth-from-last-week)
- [Find In Perf](Perf.md#find-in-perf)

## [PowerAppsActivity](PowerAppsActivity.md)

- [Power Apps events filtered activity type](PowerAppsActivity.md#power-apps-events-filtered-activity-type)

## [PowerAutomateActivity](PowerAutomateActivity.md)

- [Power Automate events filtered by activity type](PowerAutomateActivity.md#power-automate-events-filtered-by-activity-type)

## [PowerBIActivity](PowerBIActivity.md)

- [PowerBI events filtered by organization ID](PowerBIActivity.md#powerbi-events-filtered-by-organization-id)

## [PowerPlatformAdminActivity](PowerPlatformAdminActivity.md)

- [Power Platform administration events](PowerPlatformAdminActivity.md#power-platform-administration-events)

## [PowerPlatformConnectorActivity](PowerPlatformConnectorActivity.md)

- [Power Platform Connector events filtered by by activity type](PowerPlatformConnectorActivity.md#power-platform-connector-events-filtered-by-by-activity-type)

## [PowerPlatformDlpActivity](PowerPlatformDlpActivity.md)

- [Power Platform DLP events filtered by by activity type](PowerPlatformDlpActivity.md#power-platform-dlp-events-filtered-by-by-activity-type)

## [ProjectActivity](ProjectActivity.md)

- [MS Project events filtered by organization ID](ProjectActivity.md#ms-project-events-filtered-by-organization-id)

## [ProtectionStatus](ProtectionStatus.md)

- [Signatures out of date](ProtectionStatus.md#signatures-out-of-date)
- [Protection Status updates](ProtectionStatus.md#protection-status-updates)
- [Malware detection](ProtectionStatus.md#malware-detection)

## [PurviewSecurityLogs](PurviewSecurityLogs.md)

- [Audit collection delete events](PurviewSecurityLogs.md#audit-collection-delete-events)

## [REDConnectionEvents](REDConnectionEvents.md)

- [Unique authenticated Redis client IP addresses](REDConnectionEvents.md#unique-authenticated-redis-client-ip-addresses)
- [Redis client authentication requests per hour](REDConnectionEvents.md#redis-client-authentication-requests-per-hour)
- [Redis client connections per hour](REDConnectionEvents.md#redis-client-connections-per-hour)
- [Redis client disconnections per hour](REDConnectionEvents.md#redis-client-disconnections-per-hour)
- [Unsuccessful authentication attempts on Redis cache](REDConnectionEvents.md#unsuccessful-authentication-attempts-on-redis-cache)

## [ResourceManagementPublicAccessLogs](ResourceManagementPublicAccessLogs.md)

- [Group number of requests based on the IP address](ResourceManagementPublicAccessLogs.md#group-number-of-requests-based-on-the-ip-address)
- [Number of opertions triggered](ResourceManagementPublicAccessLogs.md#number-of-opertions-triggered)
- [Calls based on the target URI](ResourceManagementPublicAccessLogs.md#calls-based-on-the-target-uri)
- [Calls based on operation name](ResourceManagementPublicAccessLogs.md#calls-based-on-operation-name)
- [Calls based on user](ResourceManagementPublicAccessLogs.md#calls-based-on-user)

## [SQLAssessmentRecommendation](SQLAssessmentRecommendation.md)

- [SQL Recommendations by Focus Area](SQLAssessmentRecommendation.md#sql-recommendations-by-focus-area)
- [SQL Recommendations by Computer](SQLAssessmentRecommendation.md#sql-recommendations-by-computer)
- [SQL Recommendations by Instance](SQLAssessmentRecommendation.md#sql-recommendations-by-instance)
- [SQL Recommendations by Database](SQLAssessmentRecommendation.md#sql-recommendations-by-database)
- [SQL Recommendations by AffectedObjectType](SQLAssessmentRecommendation.md#sql-recommendations-by-affectedobjecttype)
- [How many times did each unique SQL Recommendation trigger?](SQLAssessmentRecommendation.md#how-many-times-did-each-unique-sql-recommendation-trigger)
- [High priority SQL Assessment recommendations](SQLAssessmentRecommendation.md#high-priority-sql-assessment-recommendations)

## [SecurityAttackPathData](SecurityAttackPathData.md)

- [All attack paths by specific risk level](SecurityAttackPathData.md#all-attack-paths-by-specific-risk-level)

## [SecurityEvent](SecurityEvent.md)

- [Security Events most common event IDs](SecurityEvent.md#security-events-most-common-event-ids)
- [Members added to security groups](SecurityEvent.md#members-added-to-security-groups)
- [Uses of clear text password](SecurityEvent.md#uses-of-clear-text-password)
- [Windows failed logins](SecurityEvent.md#windows-failed-logins)
- [All Security Activities](SecurityEvent.md#all-security-activities)
- [Security Activities on the Device](SecurityEvent.md#security-activities-on-the-device)
- [Security Activities for Admin](SecurityEvent.md#security-activities-for-admin)
- [Logon Activity by Device](SecurityEvent.md#logon-activity-by-device)
- [Devices With More Than 10 Logons](SecurityEvent.md#devices-with-more-than-10-logons)
- [Accounts Terminated Antimalware](SecurityEvent.md#accounts-terminated-antimalware)
- [Devices with Antimalware Terminated](SecurityEvent.md#devices-with-antimalware-terminated)
- [Devices Where Hash Was Executed](SecurityEvent.md#devices-where-hash-was-executed)
- [Process Names Executed](SecurityEvent.md#process-names-executed)
- [Devices With Security Log Cleared](SecurityEvent.md#devices-with-security-log-cleared)
- [Logon Activity by Account](SecurityEvent.md#logon-activity-by-account)
- [Accounts With Less Than 5 Times Logons](SecurityEvent.md#accounts-with-less-than-5-times-logons)
- [Remoted Logged Accounts on Devices](SecurityEvent.md#remoted-logged-accounts-on-devices)
- [Computers With Guest Account Logons](SecurityEvent.md#computers-with-guest-account-logons)
- [Members Added to Security Enabled Groups](SecurityEvent.md#members-added-to-security-enabled-groups)
- [Domain Security Policy Changes](SecurityEvent.md#domain-security-policy-changes)
- [System Audit Policy Changes](SecurityEvent.md#system-audit-policy-changes)
- [Suspicious Executables](SecurityEvent.md#suspicious-executables)
- [Logons With Clear Text Password](SecurityEvent.md#logons-with-clear-text-password)
- [Computers With Cleaned Event Logs](SecurityEvent.md#computers-with-cleaned-event-logs)
- [Accounts Failed to Logon](SecurityEvent.md#accounts-failed-to-logon)
- [Locked Accounts](SecurityEvent.md#locked-accounts)
- [Change or Reset Passwords Attempts](SecurityEvent.md#change-or-reset-passwords-attempts)
- [Groups Created or Modified](SecurityEvent.md#groups-created-or-modified)
- [Remote Procedure Call Attempts](SecurityEvent.md#remote-procedure-call-attempts)
- [User Accounts Changed](SecurityEvent.md#user-accounts-changed)

## [SentinelAudit](SentinelAudit.md)

- [Failures updating Office365-Sharepoint related Sentinel resources](SentinelAudit.md#failures-updating-office365-sharepoint-related-sentinel-resources)

## [SignalRServiceDiagnosticLogs](SignalRServiceDiagnosticLogs.md)

- [Client connection IDs](SignalRServiceDiagnosticLogs.md#client-connection-ids)
- [Connection close reasons](SignalRServiceDiagnosticLogs.md#connection-close-reasons)
- [IP addresses](SignalRServiceDiagnosticLogs.md#ip-addresses)
- [Logs relating to specific connection ID](SignalRServiceDiagnosticLogs.md#logs-relating-to-specific-connection-id)
- [Logs relating to specific message tracing ID](SignalRServiceDiagnosticLogs.md#logs-relating-to-specific-message-tracing-id)
- [Logs relating to specific user ID](SignalRServiceDiagnosticLogs.md#logs-relating-to-specific-user-id)
- [Logs with warning or exceptions](SignalRServiceDiagnosticLogs.md#logs-with-warning-or-exceptions)
- [Server connection IDs](SignalRServiceDiagnosticLogs.md#server-connection-ids)
- [Time chart of operation names](SignalRServiceDiagnosticLogs.md#time-chart-of-operation-names)
- [Transport types](SignalRServiceDiagnosticLogs.md#transport-types)
- [User IDs](SignalRServiceDiagnosticLogs.md#user-ids)

## [SigninLogs](SigninLogs.md)

- [All SiginLogs events](SigninLogs.md#all-siginlogs-events)
- [Resources accessed by user](SigninLogs.md#resources-accessed-by-user)
- [User count per Resource](SigninLogs.md#user-count-per-resource)
- [User count per Application](SigninLogs.md#user-count-per-application)
- [Failed Signin reasons](SigninLogs.md#failed-signin-reasons)
- [Failed MFA challenge](SigninLogs.md#failed-mfa-challenge)
- [Failed App tried silent signin](SigninLogs.md#failed-app-tried-silent-signin)
- [Failed login Count](SigninLogs.md#failed-login-count)
- [Signin Locations](SigninLogs.md#signin-locations)
- [Logins To Resource](SigninLogs.md#logins-to-resource)

## [StorageBlobLogs](StorageBlobLogs.md)

- [Most common errors](StorageBlobLogs.md#most-common-errors)
- [Operations causing most errors](StorageBlobLogs.md#operations-causing-most-errors)
- [Operations with the highest latency](StorageBlobLogs.md#operations-with-the-highest-latency)
- [Operations causing server side throttling](StorageBlobLogs.md#operations-causing-server-side-throttling)
- [Show anonymous requests](StorageBlobLogs.md#show-anonymous-requests)
- [Frequent operations chart](StorageBlobLogs.md#frequent-operations-chart)

## [StorageCacheOperationEvents](StorageCacheOperationEvents.md)

- [Failed operation](StorageCacheOperationEvents.md#failed-operation)
- [Failed priming job](StorageCacheOperationEvents.md#failed-priming-job)
- [Completed long-running asynchronous operations](StorageCacheOperationEvents.md#completed-long-running-asynchronous-operations)

## [StorageCacheUpgradeEvents](StorageCacheUpgradeEvents.md)

- [Upgrade events](StorageCacheUpgradeEvents.md#upgrade-events)

## [StorageCacheWarningEvents](StorageCacheWarningEvents.md)

- [Active warning events](StorageCacheWarningEvents.md#active-warning-events)

## [StorageMalwareScanningResults](StorageMalwareScanningResults.md)

- [Malicious blobs per storage account](StorageMalwareScanningResults.md#malicious-blobs-per-storage-account)
- [Unsuccessful Scans](StorageMalwareScanningResults.md#unsuccessful-scans)

## [SucceededIngestion](SucceededIngestion.md)

- [Succeeded ingestions](SucceededIngestion.md#succeeded-ingestions)
- [Succeeded ingestions timechart](SucceededIngestion.md#succeeded-ingestions-timechart)

## [SynapseLinkEvent](SynapseLinkEvent.md)

- [Synapse Link table fail events](SynapseLinkEvent.md#synapse-link-table-fail-events)

## [Syslog](Syslog.md)

- [Find Linux kernel events](Syslog.md#find-linux-kernel-events)
- [All Syslog](Syslog.md#all-syslog)
- [All Syslog with errors](Syslog.md#all-syslog-with-errors)
- [All Syslog by facility](Syslog.md#all-syslog-by-facility)
- [All Syslog by process name](Syslog.md#all-syslog-by-process-name)
- [Users Added to Linux Group by Computer](Syslog.md#users-added-to-linux-group-by-computer)
- [New Linux Group Created by Computer](Syslog.md#new-linux-group-created-by-computer)
- [Failed Linux User Password Change](Syslog.md#failed-linux-user-password-change)
- [Computers With Failed Ssh Logons](Syslog.md#computers-with-failed-ssh-logons)
- [Computers With Failed Su Logons](Syslog.md#computers-with-failed-su-logons)
- [Computers With Failed Sudo Logons](Syslog.md#computers-with-failed-sudo-logons)

## [TSIIngress](TSIIngress.md)

- [Show event source connection errors](TSIIngress.md#show-event-source-connection-errors)
- [10 latest Ingress logs](TSIIngress.md#10-latest-ingress-logs)
- [Show deserialization errors](TSIIngress.md#show-deserialization-errors)

## [UCDOAggregatedStatus](UCDOAggregatedStatus.md)

- [Content distribution in Gigabytes](UCDOAggregatedStatus.md#content-distribution-in-gigabytes)

## [UCDOStatus](UCDOStatus.md)

- [Device configuration](UCDOStatus.md#device-configuration)

## [Update](Update.md)

- [Missing security or critical updates](Update.md#missing-security-or-critical-updates)
- [Updates available for Windows machines](Update.md#updates-available-for-windows-machines)
- [Updates available for Linux machines](Update.md#updates-available-for-linux-machines)
- [Missing updates summary](Update.md#missing-updates-summary)
- [Missing updates list](Update.md#missing-updates-list)
- [Computer with missing updates](Update.md#computer-with-missing-updates)
- [Missing required updates for server](Update.md#missing-required-updates-for-server)
- [Missing critical security updates](Update.md#missing-critical-security-updates)
- [Missing security or critical where update is manual](Update.md#missing-security-or-critical-where-update-is-manual)
- [Missing update rollups](Update.md#missing-update-rollups)
- [Distinct missing updates cross computers](Update.md#distinct-missing-updates-cross-computers)

## [UpdateRunProgress](UpdateRunProgress.md)

- [Patch installation failure for your machines](UpdateRunProgress.md#patch-installation-failure-for-your-machines)

## [UpdateSummary](UpdateSummary.md)

- [Summary of updates available across machines](UpdateSummary.md#summary-of-updates-available-across-machines)
- [Missing update specific product](UpdateSummary.md#missing-update-specific-product)
- [Automatic update configuration](UpdateSummary.md#automatic-update-configuration)
- [Automatic update configuration is disabled](UpdateSummary.md#automatic-update-configuration-is-disabled)

## [UrlClickEvents](UrlClickEvents.md)

- [Links where a user was allowed to proceed](UrlClickEvents.md#links-where-a-user-was-allowed-to-proceed)

## [Usage](Usage.md)

- [Usage by data types](Usage.md#usage-by-data-types)
- [Billable performance data](Usage.md#billable-performance-data)
- [Volume of solutions' data](Usage.md#volume-of-solutions-data)
- [Total workspace ingestion over the last 24 hours](Usage.md#total-workspace-ingestion-over-the-last-24-hours)
- [Container Insight solution billable data](Usage.md#container-insight-solution-billable-data)

## [VCoreMongoRequests](VCoreMongoRequests.md)

- [Mongo vCore requests P99 duration by operation](VCoreMongoRequests.md#mongo-vcore-requests-p99-duration-by-operation)
- [Mongo vCore requests binned by duration](VCoreMongoRequests.md#mongo-vcore-requests-binned-by-duration)
- [Failed Mongo vCore requests](VCoreMongoRequests.md#failed-mongo-vcore-requests)
- [Mongo vCore requests by user agent](VCoreMongoRequests.md#mongo-vcore-requests-by-user-agent)

## [VIAudit](VIAudit.md)

- [Video Indexer Audit by account id](VIAudit.md#video-indexer-audit-by-account-id)
- [Video Indexer Audit top 10 users by operations](VIAudit.md#video-indexer-audit-top-10-users-by-operations)
- [Video Indexer Audit parsed error message](VIAudit.md#video-indexer-audit-parsed-error-message)
- [Video Indexer Audit failed operations](VIAudit.md#video-indexer-audit-failed-operations)

## [VIIndexing](VIIndexing.md)

- [Failed Indexing operations](VIIndexing.md#failed-indexing-operations)
- [Top 10 users](VIIndexing.md#top-10-users)

## [W3CIISLog](W3CIISLog.md)

- [List IIS log entries](W3CIISLog.md#list-iis-log-entries)
- [Display breakdown respond codes](W3CIISLog.md#display-breakdown-respond-codes)
- [Maximum time taken for each page](W3CIISLog.md#maximum-time-taken-for-each-page)
- [Show 404 pages list](W3CIISLog.md#show-404-pages-list)
- [Average HTTP request time](W3CIISLog.md#average-http-request-time)
- [Servers with internal server error](W3CIISLog.md#servers-with-internal-server-error)
- [Count IIS log entries by HTTP request method](W3CIISLog.md#count-iis-log-entries-by-http-request-method)
- [Count IIS log entries by HTTP user agent](W3CIISLog.md#count-iis-log-entries-by-http-user-agent)
- [Count IIS log entries by client IP address](W3CIISLog.md#count-iis-log-entries-by-client-ip-address)
- [IIS log entries for client IP](W3CIISLog.md#iis-log-entries-for-client-ip)
- [Count of IIS log entries by URL](W3CIISLog.md#count-of-iis-log-entries-by-url)
- [Count of IIS log entries by host](W3CIISLog.md#count-of-iis-log-entries-by-host)
- [Total bytes traffic by client IP](W3CIISLog.md#total-bytes-traffic-by-client-ip)
- [Bytes received by each IIS computer](W3CIISLog.md#bytes-received-by-each-iis-computer)
- [Bytes responded to clients by each IIS server IP](W3CIISLog.md#bytes-responded-to-clients-by-each-iis-server-ip)
- [Average HTTP request time by client IP](W3CIISLog.md#average-http-request-time-by-client-ip)

## [WVDAgentHealthStatus](WVDAgentHealthStatus.md)

- [Active sessions on SessionHost](WVDAgentHealthStatus.md#active-sessions-on-sessionhost)
- [HealthChecks of SessionHost](WVDAgentHealthStatus.md#healthchecks-of-sessionhost)

## [WVDCheckpoints](WVDCheckpoints.md)

- [Published remote resources by count of users](WVDCheckpoints.md#published-remote-resources-by-count-of-users)

## [WVDConnectionNetworkData](WVDConnectionNetworkData.md)

- [Average round-trip time over time](WVDConnectionNetworkData.md#average-round-trip-time-over-time)
- [Average BW across all connections](WVDConnectionNetworkData.md#average-bw-across-all-connections)
- [Top 10 users with the highest round-trip time](WVDConnectionNetworkData.md#top-10-users-with-the-highest-round-trip-time)
- [Top 10 users with lowest bandwidth](WVDConnectionNetworkData.md#top-10-users-with-lowest-bandwidth)
- [Summary of Round-trip time and bandwidth](WVDConnectionNetworkData.md#summary-of-round-trip-time-and-bandwidth)

## [WVDConnections](WVDConnections.md)

- [Connection Errors](WVDConnections.md#connection-errors)
- [Session duration](WVDConnections.md#session-duration)
- [Top 10 users by average connection duration](WVDConnections.md#top-10-users-by-average-connection-duration)
- [Top 10 most active users](WVDConnections.md#top-10-most-active-users)
- [Average connection duration by hostpool](WVDConnections.md#average-connection-duration-by-hostpool)
- [Client-side operating system information by user count](WVDConnections.md#client-side-operating-system-information-by-user-count)
- [Azure Virtual Desktop client usage information](WVDConnections.md#azure-virtual-desktop-client-usage-information)
- [Average session logon time](WVDConnections.md#average-session-logon-time)

## [WVDErrors](WVDErrors.md)

- [Top 10 connection errors](WVDErrors.md#top-10-connection-errors)
- [Top 10 feed errors](WVDErrors.md#top-10-feed-errors)

## [WaaSDeploymentStatus](WaaSDeploymentStatus.md)

- [Update deployment failures](WaaSDeploymentStatus.md#update-deployment-failures)
- [Devices pending reboot to complete update](WaaSDeploymentStatus.md#devices-pending-reboot-to-complete-update)
- [Devices with a Safeguard Hold](WaaSDeploymentStatus.md#devices-with-a-safeguard-hold)
- [Target build distribution of devices with a safeguard hold](WaaSDeploymentStatus.md#target-build-distribution-of-devices-with-a-safeguard-hold)

## [WaaSUpdateStatus](WaaSUpdateStatus.md)

- [Distribution of device Servicing Branch](WaaSUpdateStatus.md#distribution-of-device-servicing-branch)
- [Distribution of device OS Edition](WaaSUpdateStatus.md#distribution-of-device-os-edition)
- [Feature Update Deferral Configurations](WaaSUpdateStatus.md#feature-update-deferral-configurations)
- [Feature Update Pause Configurations](WaaSUpdateStatus.md#feature-update-pause-configurations)
- [Quality Update Deferral Configurations](WaaSUpdateStatus.md#quality-update-deferral-configurations)
- [Quality Update Pause Configurations](WaaSUpdateStatus.md#quality-update-pause-configurations)

## [Watchlist](Watchlist.md)

- [Get Watchlist aliases](Watchlist.md#get-watchlist-aliases)
- [Lookup events using a Watchlist](Watchlist.md#lookup-events-using-a-watchlist)

## [WindowsEvent](WindowsEvent.md)

- [WindowsEvent Audit Policy Events](WindowsEvent.md#windowsevent-audit-policy-events)

## [WireData](WireData.md)

- [Agents that provide wire data](WireData.md#agents-that-provide-wire-data)
- [IP Addresses of the agents providing wire data](WireData.md#ip-addresses-of-the-agents-providing-wire-data)
- [All Outbound communications by Remote IP Address](WireData.md#all-outbound-communications-by-remote-ip-address)
- [Bytes sent by Application Protocol](WireData.md#bytes-sent-by-application-protocol)
- [Bytes received by Protocol Name](WireData.md#bytes-received-by-protocol-name)
- [Total bytes by IP version](WireData.md#total-bytes-by-ip-version)
- [Remote IP addresses that have communicated with agents on the subnet '10.0.0.0/8' (any direction)](WireData.md#remote-ip-addresses-that-have-communicated-with-agents-on-the-subnet-100008-any-direction)
- [Processes that initiated or received network traffic](WireData.md#processes-that-initiated-or-received-network-traffic)
- [Amount of Network Traffic by Process](WireData.md#amount-of-network-traffic-by-process)

## [WorkloadDiagnosticLogs](WorkloadDiagnosticLogs.md)

- [Workload Monitoring Insights data collection warnings or errors](WorkloadDiagnosticLogs.md#workload-monitoring-insights-data-collection-warnings-or-errors)

## Next steps

- [Analyze logs from Azure storage with Log Analytics](/azure/azure-monitor/essentials/resource-logs#send-to-log-analytics-workspace)
- [Learn more about resource logs](/azure/azure-monitor/essentials/platform-logs-overview)
- [Change resource log diagnostic settings using the Azure Monitor REST API](/rest/api/monitor/diagnosticsettings)

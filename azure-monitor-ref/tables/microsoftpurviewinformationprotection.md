---
title: Azure Monitor Logs reference - MicrosoftPurviewInformationProtection
description: Reference for MicrosoftPurviewInformationProtection table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# MicrosoftPurviewInformationProtection

 Microsoft Purview Information Protection audit logs.

## Categories

- Security
- Audit
## Solutions

- Microsoft Sentinel




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ActionSource | string | The source of the label action. |
| ActionSourceDetail | string | More details about the source of the label action. |
| AppAccessContext | dynamic | The application context for the user or service principal that performed the action. |
| Application | string | The application that where the activity happened. |
| ApplicationMode | string | The label application mode, how the label was applied. |
| ClientIP | string | The IP address of the device that was used when the activity was logged. The IP address is displayed in either an IPv4 or IPv6 address format. |
| Common | dynamic | Azure Information Protection - common event data. |
| ConditionMatch | dynamic | The condition match that triggered the auto labeling. |
| ContentType | string | Content type. |
| CorrelationId | string | Correlation ID. |
| CurrentProtectionType | dynamic | Current protection event information. |
| CurrentProtectionTypeName | string | The type of protection applied. |
| DataState | string | Azure Information Protection - data state. |
| DeviceName | string | The device on which the activity happened. |
| EmailInfo | dynamic | The information required when the internalTarget is an email. |
| ExchangeMetaData | dynamic | Exchange auto labeling metadata. |
| ExecutionRuleId | string | The ID of the rule that was executed. |
| ExecutionRuleName | string | The name of the rule that was executed. |
| ExecutionRuleVersion | string | The version of the rule that was executed. |
| Id | string | Unique identifier of an audit record. |
| IrmContentId | string | The unique ID used for identifying the encrypted document after the operation is complete. |
| IsViewableByExternalUsers | bool | Is viewable by external users. |
| ItemCreationTime | datetime | The date and time the item was created. |
| ItemLastModifiedTime | datetime | The date and time the item was last modified. |
| ItemName | string | The item name. |
| ItemSize | string | The item size. |
| JustificationText | string | The justification to be provided, when configured by the admin in the sensitivity label policy, only when the sensitivity label is downgraded or removed by the user. |
| LabelAction | string | The action applied by the label. |
| LabelAppliedDateTime | datetime | The date and time the label was applied. |
| LabelEventType | string | The label operation. |
| LabelName | string | The label name applied to the item. |
| LabelVersion | string | The label version applied by the auto labeling policy. |
| MachineName | string | The machine name. |
| MgtRuleId | string | Management rule ID. |
| ObjectId | string | For SharePoint and OneDrive for Business activity, the full path name of the file or folder accessed by the user. For Exchange admin audit logging, the name of the object that was modified by the cmdlet. |
| OldSensitivityLabelId | string | The identifier of the sensitivity label previously applied to the document before the operation to change/remove the label was triggered. |
| OldSensitivityLabelOwnerEmail | string | The email address of the owner of the old sensitivity label. |
| Operation | string | The name of the user or admin activity. |
| OrganizationId | string | The GUID for your organization's Office 365 tenant. This value will always be the same for your organization, regardless of the Office 365 service in which it occurs. |
| OverriddenActions | dynamic | Actions that were overridden by the rule actions. |
| OverRideReason | string | The reason the sensitivity label was overridden. |
| OverRideType | string | Override type. |
| Platform | string | The platform on which the activity happened. |
| PolicyId | string | Policy ID. |
| PolicyName | string | Policy name. |
| PolicyVersion | string | Policy version. |
| PreviousProtectionType | dynamic | Previous protection event information. |
| PreviousProtectionTypeName | string | Previous protection type. |
| ProtectionEventData | dynamic | Azure Information Protection - protection event data. |
| ProtectionEventTypeName | string | Protection event type name. |
| Receivers | dynamic | The email addresses of the receivers. |
| RecordType | int | The type of operation indicated by the record. |
| RecordTypeName | string | The record type name. |
| ResultStatus | string | Indicates whether the action (specified in the Operation property) was successful or not. Possible values are Succeeded, PartiallySucceeded, or Failed. For Exchange admin activity, the value is either True or False. |
| RuleActions | dynamic | Actions defined by the rules. |
| RuleMode | string | The current mode of the rule. |
| Scope | string | Was this event created by a hosted O365 service or an on-premises server. |
| ScopedLocationId | string | The address that triggered the policy match. |
| Sender | string | The email address of the sender. |
| SensitiveInfoDetectionIsIncluded | bool | Determines if sensitive info detection is included. |
| SensitiveInfoTypeData | dynamic | Azure Information Protection - sensitive information types. |
| SensitivityLabelId | string | The identifier for the sensitivity label recommended, as per the policy that was matched based on the contents of the document. |
| SensitivityLabelOwnerEmail | string | The email address of the owner of the sensitivity label. |
| SensitivityLabelPolicyId | string | The identifier for the sensitivity labeling policy that was matched based on the content of the document. |
| Severity | string | The severity of the auto label policy match. |
| SharePointMetaData | dynamic | SharePoint auto labeling metadata. |
| SourceSystem | string |  |
| TargetLocation | string | The location of the document with respect to the user' device. |
| TenantId | string |  |
| TimeGenerated | datetime | The date and time when the user performed the activity. |
| Type | string | The name of the table |
| UserId | string | The UPN (User Principal Name) of the user who performed the action (specified in the Operation property) that resulted in the record being logged. |
| UserKey | string | An alternative ID for the user identified in the UserId property. This property is populated with the passport unique ID (PUID) for events performed by users in SharePoint, OneDrive for Business, and Exchange. |
| UserType | string | The type of user that performed the operation. |
| Workload | string | The Office 365 service where the activity occurred. |
| WorkLoadItemId | string | The workload item id. |

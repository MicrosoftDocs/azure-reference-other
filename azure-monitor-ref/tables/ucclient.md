---
title: Azure Monitor Logs reference - UCClient
description: Reference for UCClient table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# UCClient

 Update Compliance - This event acts as an individual device's record, containing data like the current build installed, device's name, the OS Edition, active hours (quantitative), and so on.

## Solutions

- LogManagement
- Update Compliance




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AzureADDeviceId | string | A GUID corresponding to the AAD Tenant to which the device belongs. |
| AzureADTenantId | string | A GUID corresponding to this device's AAD Device ID. |
| City | string | The last-reported location of device (city), based on IP address. |
| Country | string | The last-reported location of device (country), based on IP address. Shown as country code. |
| DeviceFamily | string | The device family e.g. PC, Phone. |
| DeviceFormFactor | string | The device form factor e.g. Notebook, Desktop, Phone. |
| DeviceManufacturer | string | The device OEM Manufacturer e.g. Hewlett-Packard. |
| DeviceModel | string | The device's OEM model e.g. HP7420 Workstation. |
| DeviceName | string | The Device given name. |
| GlobalDeviceId | string | Microsoft internal Global Device Identifier. |
| IsVirtual | bool | Whether device is a Virtual Device. |
| LastCensusScanTime | datetime | The last time this device performed a successful Census Scan, if any. |
| LastWUScanTime | datetime | The last time this device performed a successful WU Scan, if any. |
| OSArchitecture | string | The architecture of the Operating System e.g. x86. |
| OSBuild | string | The currently-installed Windows 10 Build in the format 'Major'.'Revision'. 'Major' corresponds to which Feature Update the device is on, whereas 'Revision' corresponds to which quality update the device is on. Mappings between Feature release and Major, as well as Revision and KBs, are available aka.ms/win10releaseinfo. |
| OSBuildNumber | int | An integer value for the revision number of the currently-installed Windows 10 OSBuild on the device. |
| OSEdition | string | The Windows 10 Edition or SKU. |
| OSFeatureUpdateComplianceStatus | string | Whether or not the device is on the latest Feature Update being Offered by WUfB DS, else NotApplicable. |
| OSFeatureUpdateEOSTime | datetime | The end of service date of the Feature Update currently installed on the device. |
| OSFeatureUpdateReleaseTime | datetime | The release date of the Feature Update currently installed on the device. |
| OSFeatureUpdateStatus | string | Whether or not the device is on the latest available Feature Update. |
| OSQualityUpdateComplianceStatus | string | Whether or not the device is on the latest Quality Update being Offered by WUfB DS, else NotApplicable. |
| OSQualityUpdateReleaseTime | datetime | The release date of the Quality Update currently installed on the device. |
| OSQualityUpdateStatus | string | Whether or not the device is on the latest available Quality Update, for its Feature Update. |
| OSRevisionNumber | int | An integer value for the revision number of the currently-installed Windows 10 OSBuild on the device. |
| OSSecurityUpdateComplianceStatus | string | Whether or not the device is on the latest Security update (QU, Classification==Security) being offered by WUfB DS, else NotApplicable. |
| OSSecurityUpdateStatus | string | Whether or not the device is on the latest available Security Update, for its Feature Update. |
| OSServicingChannel | string | The elected Windows 10 Servicing Channel of the device. |
| OSVersion | string | The version of Windows 10 as is organized on aka.ms/win10releaseinfo. |
| PrimaryDiskFreeCapacityMb | int | Free disk capacity of the primary disk in Megabytes. |
| SCCMClientId | string | A GUID corresponding to the SCCM Client ID on the device. |
| SourceSystem | string |  |
| TenantId | string |  |
| TimeGenerated | datetime | The time the snapshot generated this specific record. |
| Type | string | The name of the table |
| UpdateConnectivityLevel | string | Whether or not this device is maintaining a sufficiently cumulative and continuous connection to Windows Update so the update can progress optimally.  |
| WUAutomaticUpdates | int | CSP: AllowAutoUpdate &'AuOptions'  Enables the IT admin to manage automatic update behavior to scan, download, and install updates. |
| WUDeadlineNoAutoRestart | int | CSP:ConfigureDeadlineNoAutoReboot. Devices will not automatically restart outside of active hours until the deadline is reached, 1 - Enabled 0 (default) - Disabled |
| WUDODownloadMode | string | The WU DO DownloadMode configuration, brought over from Update Compliance. |
| WUFeatureDeadlineDays | int | CSP: ConfigureDeadlineForFeatureUpdatesThe WU Feature Update deadline configuration in days. -1 indicates not configured, 0 indicates configured but set to 0. Values >0 indicate the deadline in days. |
| WUFeatureDeferralDays | int | CSP: DeferFeatureUpdates. The WU Feature Update Deferral configuration in days. -1 indicates not configured, 0 indicates configured but set to 0. Values >0 indicate the policy setting. |
| WUFeatureGracePeriodDays | int | The WU grace period for feature update in days. -1 indicates not configured, 0 indicates configured and set to 0. Values greater than 0 indicate the Grace Period in days. |
| WUFeaturePauseEndTime | datetime | CSP:PauseFEatureUpdatesEndTime The time WU Feature Update Pause will end, if activated, else null. |
| WUFeaturePauseStartTime | datetime | CSP: PauseFeatureUpdatesStartTime. The time WU Feature Update Pause was activated, if activated, else null.eature Updates will be paused for 35 days from the specified start date. |
| WUFeaturePauseState | string | Indicates pause status of device for FU, possible values are Paused, NotPaused, NotConfigured. |
| WUNotificationLevel | int | CSP: UpdateNotificationLevel. This policy allows you to define what Windows Update notifications users see.  0 (default) � Use the default Windows Update notifications. 1 � Turn off all notifications, excluding restart warnings. 2 � Turn off all notifications, including restart warnings |
| WUPauseUXDisabled | int | CSP: SetDisablePauseUXAccess. This policy allows the IT admin to disable the Pause Updates feature. When this policy is enabled, the user cannot access the Pause updates" feature. Supported values 0, 1. |
| WUQualityDeadlineDays | int | CSP: ConfigureDeadlineForQualityUpdates The WU Qualty Update deadline configuration in days. -1 indicates not configured, 0 indicates configured but set to 0. Values >0 indicate the deadline in days. |
| WUQualityDeferralDays | int | CSP: DeferQualityUpdatesThe WU Quality Update Deferral configuration in days. -1 indicates not configured, 0 indicates configured but set to 0. Values >0 indicate the policy setting. |
| WUQualityGracePeriodDays | int | The WU grace period for quality update in days. -1 indicates not configured, 0 indicates configured and set to 0. Values greater than 0 indicate the Grace Period in days. |
| WUQualityPauseEndTime | datetime | CSP:PauseQualityUpdatesEndTimeThe time WU Quality Update Pause will end, if activated, else null. |
| WUQualityPauseStartTime | datetime | CSP:PauseQualityUpdatesStartTime The time WU Quality Update Pause was activated; if activated; else null. |
| WUQualityPauseState | string | Indicates pause status of device for QU, possible values are Paused, NotPaused, NotConfigured. |
| WURestartNotification | int | CSP: AutoRestartRequiredNotificationDismissal. Allows the IT Admin to specify the method by which the auto-restart required notification is dismissed.The following list shows the supported values:  1 (default) = Auto Dismissal. 2 � User Dismissal. |
| WUServiceURLConfigured | string | CSP:UpdateServiceUrl. The following list shows the supported values: Not configured. The device checks for updates from Microsoft Update. Set to a URL, such as http://abcd-srv:8530. The device checks for updates from the WSUS server at the specified URL. Not configured. The device checks for updates from Microsoft Update. Set to a URL, such as http://abcd-srv:8530. The device checks for updates from the WSUS server at the specified URL. |
| WUUXDisabled | int | CSP:SetDisableUXWUAccess.This policy allows the IT admin to remove access to scan Windows Update. When this policy is enabled, the user cannot access the Windows Update scan, download, and install features. Default is 0. Supported values 0, 1. |

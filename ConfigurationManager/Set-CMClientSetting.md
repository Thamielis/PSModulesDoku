Set-CMClientSetting
-------------------




### Synopsis
Change client settings for Configuration Manager devices and users.



---


### Description

The Set-CMClientSetting cmdlet changes client settings for Configuration Manager devices and users. Configuration Manager provides default values for all client settings, but you can use this cmdlet to modify settings objects. Settings objects determine settings for individual clients. For more information, see About client settings (/mem/configmgr/core/clients/deploy/about-client-settings).



> [!IMPORTANT] > Starting in version 2010, this cmdlet is deprecated. Use one of the cmdlets specific to the client settings group, listed in the Related links (#related-links).



To modify a client setting, specify it by name.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [About client settings](About client settings)



* [Get-CMClientSetting](Get-CMClientSetting)



* [New-CMClientSetting](New-CMClientSetting)



* [Remove-CMClientSetting](Remove-CMClientSetting)



* [New-CMSchedule](New-CMSchedule)



* [Set-CMClientSettingBackgroundIntelligentTransfer](Set-CMClientSettingBackgroundIntelligentTransfer)



* [Set-CMClientSettingClientCache](Set-CMClientSettingClientCache)



* [Set-CMClientSettingClientPolicy](Set-CMClientSettingClientPolicy)



* [Set-CMClientSettingCloudService](Set-CMClientSettingCloudService)



* [Set-CMClientSettingComplianceSetting](Set-CMClientSettingComplianceSetting)



* [Set-CMClientSettingComputerAgent](Set-CMClientSettingComputerAgent)



* [Set-CMClientSettingComputerRestart](Set-CMClientSettingComputerRestart)



* [Set-CMClientSettingDeliveryOptimization](Set-CMClientSettingDeliveryOptimization)



* [Set-CMClientSettingEndpointProtection](Set-CMClientSettingEndpointProtection)



* [Set-CMClientSettingEnrollment](Set-CMClientSettingEnrollment)



* [Set-CMClientSettingGeneral](Set-CMClientSettingGeneral)



* [Set-CMClientSettingHardwareInventory](Set-CMClientSettingHardwareInventory)



* [Set-CMClientSettingMeteredInternetConnection](Set-CMClientSettingMeteredInternetConnection)



* [Set-CMClientSettingPowerManagement](Set-CMClientSettingPowerManagement)



* [Set-CMClientSettingRemoteTool](Set-CMClientSettingRemoteTool)



* [Set-CMClientSettingSoftwareCenter](Set-CMClientSettingSoftwareCenter)



* [Set-CMClientSettingSoftwareDeployment](Set-CMClientSettingSoftwareDeployment)



* [Set-CMClientSettingSoftwareInventory](Set-CMClientSettingSoftwareInventory)



* [Set-CMClientSettingSoftwareMetering](Set-CMClientSettingSoftwareMetering)



* [Set-CMClientSettingSoftwareUpdate](Set-CMClientSettingSoftwareUpdate)



* [Set-CMClientSettingStateMessaging](Set-CMClientSettingStateMessaging)



* [Set-CMClientSettingUserAndDeviceAffinity](Set-CMClientSettingUserAndDeviceAffinity)





---


### Examples
#### Example 1: Rename a client setting
```PowerShell
Set-CMClientSetting -Name "Client Settings Main" -Description "Client settings for TSQA office site." -NewName "Client Settings TSQA"
```

#### Example 2: Configure power management
```PowerShell
Set-CMClientSetting -Name "TSQA02" -AllowUserToOptOutFromPowerPlan $True -EnablePowerManagement $False
```

#### Example 3: Set state messaging reporting cycle value
```PowerShell
Set-CMClientSetting -Name "TSQA02" -StateMessagingReportingCycleMinutes 10
```

#### Example 4: Configure user affinity
```PowerShell
Set-CMClientSetting -Name "TSQA03" -AutoApproveAffinity $False -UserAffinityLogOnThresholdMinutes 2800 -UserAffinityUsageThresholdDays 20
```

#### Example 5: Allow user affinity
```PowerShell
Set-CMClientSetting -Name "TSQA04" -AllowUserAffinity $True
```

#### Example 6: Set bandwidth for client
```PowerShell
Set-CMClientSetting -Name "TSQA05" -EnableBITSMaxBandwidth $True EnableDownloadOffSchedule $True -MaxBandwidthValidFrom 8 -MaxBandwidthValidTo 15 -MaxTransferRateOnSchedule 1500
```

#### Example 7: Configure user policies on the internet
```PowerShell
Set-CMClientSetting -Name "TSQA06" -EnableUserPolicyOnInternet $True -EnableUserPolicyPolling $False -EnableUserPolicyOnInternet $True -PolicyPollingInterval 50
```

#### Example 8: Disable compliance evaluation
```PowerShell
Set-CMClientSetting -Name "TSQA07" -EnableComplianceEvaluation $False
```

#### Example 9: Set computer agent settings
```PowerShell
Set-CMClientSetting -Name "TSQA09" -AddPortalToTrustedSiteList $True -AllowPortalToHaveElevatedTrust $True -BrandingTitle "Contoso IT" -EnableThirdPartyOrchestration Yes -FinalReminderMinutesInterval 52 -InitialReminderHoursInterval 6 -InstallRestriction OnlyAdministrators -PortalUrl "https://NewInstall.Contoso.com" -PowerShellExecutionPolicy Bypass -SuspendBitLocker Always
```

#### Example 10: Configure restart settings
```PowerShell
Set-CMClientSetting -Name "TSQA11" -RebootLogoffNotificationCountdownDuration 12 -RebootLogoffNotificationFinalWindowMinutes 80
```

#### Example 11: Configure metered network usage
```PowerShell
Set-CMClientSetting -Name "TSQA21" -MeteredNetworkUsage Limit
```



---


### Parameters
#### **AccessLevel**

Specifies a level of allowed remote control access. Valid values are:


* FullControl


* NoAccess


* None


* ViewOnly



Valid Values:

* NoAccess
* ViewOnly
* FullControl






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[AccessLevelType]`|false   |named   |False        |



#### **AddPortalToTrustedSiteList**

Don't use this parameter. The application catalog is no longer supported.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowClientChange**

Indicates whether users can change policy or notification settings in Software Center.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowCloudDistributionPoint**

Indicates whether a device or user can access content from a cloud-based distribution point.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowPermittedViewer**








|Type       |Required|Position|PipelineInput|Aliases                             |
|-----------|--------|--------|-------------|------------------------------------|
|`[Boolean]`|false   |named   |False        |AllowPermittedViewersToRemoteDesktop|



#### **AllowPortalToHaveElevatedTrust**

Indicates whether to allow a portal to have elevated trust.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowRemoteControlOfUnattendedComputer**

Indicates whether to allow remote control of a computer with no user logged onto that computer.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowUserAffinity**

Indicates whether users can define their primary devices.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowUserToOptOutFromPowerPlan**

Indicates whether to allow users to exclude a device from power management settings.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ApplicationCatalogWebsitePointServerName**

Don't use this parameter. The application catalog is no longer supported.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **AudibleSignal**

Specifies what kind of sound a client computer plays while under remote control. This setting does not apply to remote assistance. Valid values are:


* None


* PlayNoSound


* PlaySoundAtBeginAndEnd


* PlaySoundRepeatedly



Valid Values:

* PlayNoSound
* PlaySoundAtBeginAndEnd
* PlaySoundRepeatedly






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[AudibleSignalType]`|false   |named   |False        |



#### **AutoApproveAffinity**

Indicates whether the client automatically configures user device affinity from usage data.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **BatchingTimeout**

Specifies a timeout value, as an integer. Specify a value of Hours or Days by using the TimeUnit parameter. When an update deadline passes, Configuration Manager deploys all updates pending within this period.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **Bits**








|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[Switch]`|true    |named   |False        |BitsSettings|



#### **BrandingTitle**

Specifies a Configuration Manager branding title. This branding information helps users identify Configuration Manager as a trusted source.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ClientPolicy**








|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[Switch]`|true    |named   |False        |ClientPolicySettings|



#### **CloudService**








|Type      |Required|Position|PipelineInput|Aliases                                |
|----------|--------|--------|-------------|---------------------------------------|
|`[Switch]`|true    |named   |False        |CloudServicesSettings<br/>CloudServices|



#### **Compliance**








|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[Switch]`|true    |named   |False        |ComplianceSettings|



#### **ComputerAgent**








|Type      |Required|Position|PipelineInput|Aliases              |
|----------|--------|--------|-------------|---------------------|
|`[Switch]`|true    |named   |False        |ComputerAgentSettings|



#### **ComputerRestart**








|Type      |Required|Position|PipelineInput|Aliases                |
|----------|--------|--------|-------------|-----------------------|
|`[Switch]`|true    |named   |False        |ComputerRestartSettings|



#### **DeploymentEvaluationSchedule**

Specifies a deployment evaluation schedule as a schedule object. To obtain a schedule object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **Description**

Specifies a description for client settings.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableFirstSignatureUpdate**

Indicates whether to disable the first signature update on client from a remote source.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DisplayNewProgramNotification**

Indicates whether Configuration Manager shows the user notifications for software availability or software installations. If this parameter has a value of $False, the user sees only restart notifications.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Enable**

Indicates whether to enable client settings.






|Type       |Required|Position|PipelineInput|Aliases                                                                                                                                                                                                                             |
|-----------|--------|--------|-------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|`[Boolean]`|false   |named   |False        |EnableEndpointProtection<br/>EnablePowerManagement<br/>EnableHardwareInventory<br/>EnableDeviceEnrollment<br/>EnableNetworkAccessProtection<br/>EnableSoftwareMetering<br/>EnableSoftwareUpdatesOnClient<br/>EnableSoftwareInventory|



#### **EnableBitsMaxBandwidth**

Specifies whether to enable maximum bandwidth for Background Intelligent Transfer Service (BITS) background transfers.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableComplianceEvaluation**

Indicates whether to enable compliance evaluation for this client.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableDownloadOffSchedule**

Specifies whether allow BITS downloads outside of a throttling window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableThirdPartyOrchestration**

Specifies whether Software Updates and Software Distribution agents wait for third-party software to install updates and applications.


Valid values are: Yes and No.



Valid Values:

* No
* Yes






|Type                                 |Required|Position|PipelineInput|
|-------------------------------------|--------|--------|-------------|
|`[EnableThirdPartyOrchestrationType]`|false   |named   |False        |



#### **EnableUserDataAndProfile**

Indicates whether to enable user data and profile settings.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableUserPolicy**








|Type       |Required|Position|PipelineInput|Aliases                |
|-----------|--------|--------|-------------|-----------------------|
|`[Boolean]`|false   |named   |False        |EnableUserPolicyPolling|



#### **EnableUserPolicyOnInternet**

Indicates whether users receive a user policy when logged on to a computer on the Internet. In order for users to receive user policy, you must enable user polling. You can use the EnableUserPolicyPolling parameter to enable user polling. An Internet-based management point must authenticate the user.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableUserPolicyOnTS**

Use this parameter to enable or disable the client setting, Enable user policy for multiple user sessions .






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableWakeupProxy**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EndpointProtection**








|Type      |Required|Position|PipelineInput|Aliases                   |
|----------|--------|--------|-------------|--------------------------|
|`[Switch]`|true    |named   |False        |EndpointProtectionSettings|



#### **EnforceMandatory**

Indicates whether to enforce all mandatory software update deployments that have deadlines within a specified period of time.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Enrollment**








|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[Switch]`|true    |named   |False        |EnrollmentSettings|



#### **EnrollmentProfileName**








|Type      |Required|Position|PipelineInput|Aliases                    |
|----------|--------|--------|-------------|---------------------------|
|`[String]`|false   |named   |False        |DeviceEnrollmentProfileName|



#### **FinalReminderMins**








|Type     |Required|Position|PipelineInput|Aliases                     |
|---------|--------|--------|-------------|----------------------------|
|`[Int32]`|false   |named   |False        |FinalReminderMinutesInterval|



#### **FirewallExceptionForWakeupProxy**





Valid Values:

* None
* Public
* Private
* Domain






|Type                                 |Required|Position|PipelineInput|Aliases                                |
|-------------------------------------|--------|--------|-------------|---------------------------------------|
|`[WakeUpProxyFirewallExceptionTypes]`|false   |named   |False        |WindowsFirewallExceptionsForWakeUpProxy|



#### **FirewallExceptionProfile**

Specifies a firewall exception profile. Valid values are:


* Disabled


* Domain


* Private


* Public



Valid Values:

* Disabled
* Public
* Private
* Domain






|Type                              |Required|Position|PipelineInput|
|----------------------------------|--------|--------|-------------|
|`[FirewallExceptionProfileType[]]`|false   |named   |False        |



#### **ForceRebootHr**








|Type     |Required|Position|PipelineInput|Aliases                               |
|---------|--------|--------|-------------|--------------------------------------|
|`[Int32]`|false   |named   |False        |ForceRebootPeriod<br/>ForceRebootHours|



#### **ForceScan**

Indicates whether to enable force scan.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **GrantRemoteControlPermissionToLocalAdministrator**

Indicates whether local administrators on the server initiating a remote control connection can establish remote control sessions to this client.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **HardwareInventory**








|Type      |Required|Position|PipelineInput|Aliases                  |
|----------|--------|--------|-------------|-------------------------|
|`[Switch]`|true    |named   |False        |HardwareInventorySettings|



#### **InitialReminderHours**








|Type     |Required|Position|PipelineInput|Aliases                     |
|---------|--------|--------|-------------|----------------------------|
|`[Int32]`|false   |named   |False        |InitialReminderHoursInterval|



#### **InstallEndpointProtectionClient**

Indicates whether to install and enable the Endpoint Protection client on this client if it is not already installed.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **InstallRestriction**

Specifies which users can initiate an install. Valid values are:


* AllUsers


* NoUsers


* OnlyAdministrators


* OnlyAdministratorsAndPrimaryUsers



Valid Values:

* AllUsers
* OnlyAdministrators
* OnlyAdministratorsAndPrimaryUsers
* NoUsers






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[InstallRestrictionType]`|false   |named   |False        |



#### **InterimReminderHours**








|Type     |Required|Position|PipelineInput|Aliases                     |
|---------|--------|--------|-------------|----------------------------|
|`[Int32]`|false   |named   |False        |InterimReminderHoursInterval|



#### **InventoryReportId**

Specifies an inventory report ID.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **LogOnThresholdMins**








|Type     |Required|Position|PipelineInput|Aliases                                                             |
|---------|--------|--------|-------------|--------------------------------------------------------------------|
|`[Int32]`|false   |named   |False        |UserAffinityLogOnThresholdMinutes<br/>UserAffinityLogOnThresholdMins|



#### **ManageRemoteDesktopSetting**

Indicates whether to allow Configuration Manager to manage Remote Desktop sessions for computers.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ManageSolicitedRemoteAssistance**

Indicates whether to allow Configuration Manager to manage solicited remote assistance sessions.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ManageUnsolicitedRemoteAssistance**

Indicates whether to allow Configuration Manager to manage unsolicited remote assistance sessions.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **MaxBandwidthBeginHr**








|Type     |Required|Position|PipelineInput|Aliases              |
|---------|--------|--------|-------------|---------------------|
|`[Int32]`|false   |named   |False        |MaxBandwidthValidFrom|



#### **MaxBandwidthEndHr**








|Type     |Required|Position|PipelineInput|Aliases            |
|---------|--------|--------|-------------|-------------------|
|`[Int32]`|false   |named   |False        |MaxBandwidthValidTo|



#### **MaxTransferRateOffSchedule**

Specifies an integer value for maximum transfer rate off schedule.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **MaxTransferRateOnSchedule**

Specifies an integer value for maximum transfer rate on schedule.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **MeteredNetwork**








|Type      |Required|Position|PipelineInput|Aliases               |
|----------|--------|--------|-------------|----------------------|
|`[Switch]`|true    |named   |False        |MeteredNetworkSettings|



#### **MeteredNetworkUsage**

Specifies a type of metered network usage to allow. Valid values are:


* Allow


* Block


* Limit


* None



Valid Values:

* None
* Allow
* Limit
* Block






|Type                       |Required|Position|PipelineInput|
|---------------------------|--------|--------|-------------|
|`[MeteredNetworkUsageType]`|false   |named   |False        |



#### **Name**

Specifies a name for a client setting.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **NetworkAccessProtection**








|Type      |Required|Position|PipelineInput|Aliases                        |
|----------|--------|--------|-------------|-------------------------------|
|`[Switch]`|true    |named   |False        |NetworkAccessProtectionSettings|



#### **NewName**

Specifies a new name for a client setting.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **NoRebootEnforcement**

Applies to version 2006 and later. Configure the client setting Configuration Manager can force a device to restart to prevent devices from automatically restarting when a deployment requires it. By default, Configuration Manager can still force devices to restart. For more information, see device restart notifications (/mem/configmgr/core/clients/deploy/device-restart-notifications).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PermittedViewer**

Specifies an array of names of users who can establish remote control sessions to a client computer.






|Type        |Required|Position|PipelineInput|Aliases         |
|------------|--------|--------|-------------|----------------|
|`[String[]]`|false   |named   |False        |PermittedViewers|



#### **PolicyPollingMins**








|Type     |Required|Position|PipelineInput|Aliases                                      |
|---------|--------|--------|-------------|---------------------------------------------|
|`[Int32]`|false   |named   |False        |PolicyPollingInterval<br/>PollingIntervalMins|



#### **PortalUrl**

Specifies a link, as a URL, for a portal for a client.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PowerManagement**








|Type      |Required|Position|PipelineInput|Aliases                |
|----------|--------|--------|-------------|-----------------------|
|`[Switch]`|true    |named   |False        |PowerManagementSettings|



#### **PowerShellExecutionPolicy**

Specifies how Configuration Manager runs Windows PowerShell scripts on remote computers. Valid values are


* AllSigned


* Bypass


* Restricted




The default value is Restricted.

When you select Restricted, the Configuration Manager client uses the current Windows PowerShell configuration on the client computer, which determines whether unsigned scripts run.




Valid Values:

* AllSigned
* Bypass
* Restricted






|Type                             |Required|Position|PipelineInput|
|---------------------------------|--------|--------|-------------|
|`[PowerShellExecutionPolicyType]`|false   |named   |False        |



#### **Priority**

Specifies a priority change for a client setting. Valid values are: Decrease and Increase.



Valid Values:

* Increase
* Decrease






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[PriorityChangeType]`|false   |named   |False        |



#### **PromptUserForPermission**

Indicates whether a client computer displays a message asking for user permission before it allows a remote control session.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RebootLogoffNotificationCountdownMins**








|Type     |Required|Position|PipelineInput|Aliases                                         |
|---------|--------|--------|-------------|------------------------------------------------|
|`[Int32]`|false   |named   |False        |RebootLogoffNotificationCountdownDurationMinutes|



#### **RebootLogoffNotificationFinalWindowMins**








|Type     |Required|Position|PipelineInput|Aliases                                   |
|---------|--------|--------|-------------|------------------------------------------|
|`[Int32]`|false   |named   |False        |RebootLogoffNotificationFinalWindowMinutes|



#### **RemoteAssistanceAccessLevel**

Specifies a level of access to assign to remote assistance sessions initiated in Configuration Manager. A user at the client computer always grants permission for a remote assistance session to occur. Valid values are:


* FullControl


* None


* RemoteViewing



Valid Values:

* None
* RemoteViewing
* FullControl






|Type                               |Required|Position|PipelineInput|
|-----------------------------------|--------|--------|-------------|
|`[RemoteAssistanceAccessLevelType]`|false   |named   |False        |



#### **RemoteControl**








|Type      |Required|Position|PipelineInput|Aliases                            |
|----------|--------|--------|-------------|-----------------------------------|
|`[Switch]`|true    |named   |False        |RemoteToolsSettings<br/>RemoteTools|



#### **RemoveThirdParty**

Indicates whether to remove third party.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ReplaceToastNotificationWithDialog**

Specify whether to replace toast notifications with a more intrusive dialog window when a deployment requires a restart. It's an optional parameter and false by default.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ReportingCycleMins**








|Type     |Required|Position|PipelineInput|Aliases                                                                 |
|---------|--------|--------|-------------|------------------------------------------------------------------------|
|`[Int32]`|false   |named   |False        |StateMessagingReportingCycleMinutes<br/>StateMessagingReportingCycleMins|



#### **RequireAuthentication**

Indicates whether to use network-level authentication to establish Remote Desktop connections to a client computer.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ScanSchedule**

Specifies a scan schedule as a schedule object. To obtain a schedule object, use the New-CMSchedule cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **Schedule**

Specifies a CMSchedule object. To create a CMSchedule object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






|Type             |Required|Position|PipelineInput|Aliases                                                                                                                    |
|-----------------|--------|--------|-------------|---------------------------------------------------------------------------------------------------------------------------|
|`[IResultObject]`|false   |named   |False        |InventorySchedule<br/>NapEvaluationSchedule<br/>EvaluationSchedule<br/>DataCollectionSchedule<br/>SoftwareInventorySchedule|



#### **SelectApplicationCatalogWebsitePoint**

Don't use this parameter. The application catalog is no longer supported.



Valid Values:

* Fqdn
* AutoDetect
* NetBios






|Type                                  |Required|Position|PipelineInput|
|--------------------------------------|--------|--------|-------------|
|`[ApplicationCatalogWebsitePointType]`|false   |named   |False        |



#### **ShowNotificationIconOnTaskbar**

Indicates whether to display an icon on the taskbar of a client computer to indicate an active remote control session.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ShowSessionConnectionBar**

Indicates whether to display a high-visibility session connection bar on a client computer to specify an active remote control session.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SoftwareDeployment**








|Type      |Required|Position|PipelineInput|Aliases                   |
|----------|--------|--------|-------------|--------------------------|
|`[Switch]`|true    |named   |False        |SoftwareDeploymentSettings|



#### **SoftwareInventory**








|Type      |Required|Position|PipelineInput|Aliases                  |
|----------|--------|--------|-------------|-------------------------|
|`[Switch]`|true    |named   |False        |SoftwareInventorySettings|



#### **SoftwareInventoryFileDisplayName**

Specifies the display name to use in place of an inventoried name specified by the SoftwareInventoryFileInventoriedName parameter. This parameter allows you to standardize inventory information for software names that differ in different file headers.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SoftwareInventoryFileInventoriedName**

Specifies an inventoried manufacturer or product name. During software inventory, Configuration Manager gets inventoried names from header information on client devices.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SoftwareInventoryFileName**

Specifies a name for the file you want to collect during inventory. You can use the wildcard (*) to represent any string of text and the question mark (?) to represent any single character.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SoftwareMetering**








|Type      |Required|Position|PipelineInput|Aliases                 |
|----------|--------|--------|-------------|------------------------|
|`[Switch]`|true    |named   |False        |SoftwareMeteringSettings|



#### **SoftwareUpdate**








|Type      |Required|Position|PipelineInput|Aliases                |
|----------|--------|--------|-------------|-----------------------|
|`[Switch]`|true    |named   |False        |SoftwareUpdatesSettings|



#### **StateMessage**








|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[Switch]`|true    |named   |False        |StateMessageSettings|



#### **SuppressReboot**

Indicates whether to bypass a required computer restart after installing the System Center 2016 Endpoint Protection client.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SuspendBitLocker**

Specifies whether to bypass a required BitLocker Drive Encryption PIN entry when a computer restarts after a software installation. This setting applies only when Configuration Manager initiates a restart. Valid values are:


* Always. Configuration Manager temporarily suspends the BitLocker requirement to enter a PIN. - Never. Configuration Manager does not suspend the BitLocker requirement to enter a PIN on the next computer startup after it has installed software that requires a restart.


If you select Never, the software installation cannot finish until the user enters the PIN to complete the standard startup process.



Valid Values:

* Never
* Always






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[SuspendBitLockerType]`|false   |named   |False        |



#### **TimeUnit**

Specifies the unit for the value specified in the BatchingTimeout parameter. Valid values are: Hours and Days.



Valid Values:

* Days
* Hours






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[BatchingTimeoutType]`|false   |named   |False        |



#### **UsageThresholdDays**








|Type     |Required|Position|PipelineInput|Aliases                       |
|---------|--------|--------|-------------|------------------------------|
|`[Int32]`|false   |named   |False        |UserAffinityUsageThresholdDays|



#### **UseNewSoftwareCenter**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UserDeviceAffinity**








|Type      |Required|Position|PipelineInput|Aliases                   |
|----------|--------|--------|-------------|--------------------------|
|`[Switch]`|true    |named   |False        |UserDeviceAffinitySettings|



#### **UseUtcForEvaluationTime**

Indicates whether to use Coordinated Universal Time (UTC), also known as Greenwich Mean Time, to configure a recurring interval. If you specify $False, Configuration Manager uses local time.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **WakeOnLanPort**








|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **WakeupProxyDirectAccessPrefix**








|Type      |Required|Position|PipelineInput|Aliases                                               |
|----------|--------|--------|-------------|------------------------------------------------------|
|`[String]`|false   |named   |False        |IPv6PrefixesForDirectAccessOrInterveningNetworkDevices|



#### **WakeupProxyPort**








|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **Confirm**
-Confirm is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-Confirm is used to -Confirm each operation.

If you pass ```-Confirm:$false``` you will not be prompted.


If the command sets a ```[ConfirmImpact("Medium")]``` which is lower than ```$confirmImpactPreference```, you will not be prompted unless -Confirm is passed.

#### **WhatIf**
-WhatIf is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-WhatIf is used to see what would happen, or return operations without executing them


---


### Inputs
None





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes
Starting in version 2010, this cmdlet is deprecated. Use one of the cmdlets specific to the client settings group, listed in the Related links (#related-links).



---


### Syntax
```PowerShell
Set-CMClientSetting [-AccessLevel {NoAccess | ViewOnly | FullControl}] [-AllowClientChange <Boolean>] [-AllowPermittedViewer <Boolean>] [-AllowRemoteControlOfUnattendedComputer <Boolean>] [-AudibleSignal {PlayNoSound | PlaySoundAtBeginAndEnd | PlaySoundRepeatedly}] [-DisableWildcardHandling] [-FirewallExceptionProfile {Disabled | Public | Private | Domain}] [-ForceWildcardHandling] [-GrantRemoteControlPermissionToLocalAdministrator <Boolean>] [-ManageRemoteDesktopSetting <Boolean>] [-ManageSolicitedRemoteAssistance <Boolean>] [-ManageUnsolicitedRemoteAssistance <Boolean>] -Name <String> [-PassThru] [-PermittedViewer <String[]>] [-PromptUserForPermission <Boolean>] [-RemoteAssistanceAccessLevel {None | RemoteViewing | FullControl}] -RemoteControl [-RequireAuthentication <Boolean>] [-ShowNotificationIconOnTaskbar <Boolean>] [-ShowSessionConnectionBar <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSetting [-AddPortalToTrustedSiteList <Boolean>] [-AllowPortalToHaveElevatedTrust <Boolean>] [-ApplicationCatalogWebsitePointServerName <String>] [-BrandingTitle <String>] -ComputerAgent [-DisableWildcardHandling] [-DisplayNewProgramNotification <Boolean>] [-EnableThirdPartyOrchestration {No | Yes}] [-FinalReminderMins <Int32>] [-ForceWildcardHandling] [-InitialReminderHours <Int32>] [-InstallRestriction {AllUsers | OnlyAdministrators | OnlyAdministratorsAndPrimaryUsers | NoUsers}] [-InterimReminderHours <Int32>] -Name <String> [-PassThru] [-PortalUrl <String>] [-PowerShellExecutionPolicy {AllSigned | Bypass | Restricted}] [-SelectApplicationCatalogWebsitePoint {Fqdn | AutoDetect | NetBios}] [-SuspendBitLocker {Never | Always}] [-UseNewSoftwareCenter <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSetting [-AllowCloudDistributionPoint <Boolean>] -CloudService [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSetting [-AllowUserAffinity <Boolean>] [-AutoApproveAffinity <Boolean>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-LogOnThresholdMins <Int32>] -Name <String> [-PassThru] [-UsageThresholdDays <Int32>] -UserDeviceAffinity [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSetting [-AllowUserToOptOutFromPowerPlan <Boolean>] [-DisableWildcardHandling] [-Enable <Boolean>] [-EnableWakeupProxy <Boolean>] [-FirewallExceptionForWakeupProxy {None | Public | Private | Domain}] [-ForceWildcardHandling] -Name <String> [-PassThru] -PowerManagement [-WakeOnLanPort <Int32>] [-WakeupProxyDirectAccessPrefix <String>] [-WakeupProxyPort <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSetting [-BatchingTimeout <Int32>] [-DeploymentEvaluationSchedule <IResultObject>] [-DisableWildcardHandling] [-Enable <Boolean>] [-EnforceMandatory <Boolean>] [-ForceWildcardHandling] -Name <String> [-PassThru] [-ScanSchedule <IResultObject>] -SoftwareUpdate [-TimeUnit {Days | Hours}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSetting -Bits [-DisableWildcardHandling] [-EnableBitsMaxBandwidth <Boolean>] [-EnableDownloadOffSchedule <Boolean>] [-ForceWildcardHandling] [-MaxBandwidthBeginHr <Int32>] [-MaxBandwidthEndHr <Int32>] [-MaxTransferRateOffSchedule <Int32>] [-MaxTransferRateOnSchedule <Int32>] -Name <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSetting -ClientPolicy [-DisableWildcardHandling] [-EnableUserPolicy <Boolean>] [-EnableUserPolicyOnInternet <Boolean>] [-EnableUserPolicyOnTS <Boolean>] [-ForceWildcardHandling] -Name <String> [-PassThru] [-PolicyPollingMins <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSetting -Compliance [-DisableWildcardHandling] [-EnableComplianceEvaluation <Boolean>] [-EnableUserDataAndProfile <Boolean>] [-ForceWildcardHandling] -Name <String> [-PassThru] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSetting -ComputerRestart [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-NoRebootEnforcement <Boolean>] [-PassThru] [-RebootLogoffNotificationCountdownMins <Int32>] [-RebootLogoffNotificationFinalWindowMins <Int32>] [-ReplaceToastNotificationWithDialog <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSetting [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-NewName <String>] [-PassThru] [-Priority {Increase | Decrease}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSetting [-DisableFirstSignatureUpdate <Boolean>] [-DisableWildcardHandling] [-Enable <Boolean>] -EndpointProtection [-ForceRebootHr <Int32>] [-ForceWildcardHandling] [-InstallEndpointProtectionClient <Boolean>] -Name <String> [-PassThru] [-RemoveThirdParty <Boolean>] [-SuppressReboot <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSetting [-DisableWildcardHandling] [-Enable <Boolean>] [-ForceWildcardHandling] -HardwareInventory [-InventoryReportId <String>] -Name <String> [-PassThru] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSetting [-DisableWildcardHandling] [-Enable <Boolean>] -Enrollment [-EnrollmentProfileName <String>] [-ForceWildcardHandling] -Name <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSetting [-DisableWildcardHandling] [-Enable <Boolean>] [-ForceScan <Boolean>] [-ForceWildcardHandling] -Name <String> -NetworkAccessProtection [-PassThru] [-Schedule <IResultObject>] [-UseUtcForEvaluationTime <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSetting [-DisableWildcardHandling] [-Enable <Boolean>] [-ForceWildcardHandling] -Name <String> [-PassThru] [-Schedule <IResultObject>] -SoftwareMetering [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSetting [-DisableWildcardHandling] [-Enable <Boolean>] [-ForceWildcardHandling] -Name <String> [-PassThru] [-Schedule <IResultObject>] -SoftwareInventory [-SoftwareInventoryFileDisplayName <String>] [-SoftwareInventoryFileInventoriedName <String>] [-SoftwareInventoryFileName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSetting [-DisableWildcardHandling] [-ForceWildcardHandling] -MeteredNetwork [-MeteredNetworkUsage {None | Allow | Limit | Block}] -Name <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSetting [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-PassThru] [-ReportingCycleMins <Int32>] -StateMessage [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSetting [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-PassThru] [-Schedule <IResultObject>] -SoftwareDeployment [-Confirm] [-WhatIf] [<CommonParameters>]
```

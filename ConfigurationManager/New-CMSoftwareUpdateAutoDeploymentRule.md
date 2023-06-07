New-CMSoftwareUpdateAutoDeploymentRule
--------------------------------------




### Synopsis
Create an automatic deployment rule (ADR) for software updates.



---


### Description

The New-CMSoftwareUpdateAutoDeploymentRule cmdlet creates a automatic deployment rule (ADR) for software updates. When a rule runs, Configuration Manager adds updates that qualify for the rule to a software update group. The Configuration Manager server downloads content files and copies them to distribution points, and then updates client computers. For more information, see Automatically deploy software updates (/mem/configmgr/sum/deploy-use/automatically-deploy-software-updates).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMSoftwareUpdateAutoDeploymentRule](Disable-CMSoftwareUpdateAutoDeploymentRule)



* [Enable-CMSoftwareUpdateAutoDeploymentRule](Enable-CMSoftwareUpdateAutoDeploymentRule)



* [Get-CMSoftwareUpdateAutoDeploymentRule](Get-CMSoftwareUpdateAutoDeploymentRule)



* [Invoke-CMSoftwareUpdateAutoDeploymentRule](Invoke-CMSoftwareUpdateAutoDeploymentRule)



* [Remove-CMSoftwareUpdateAutoDeploymentRule](Remove-CMSoftwareUpdateAutoDeploymentRule)



* [Set-CMSoftwareUpdateAutoDeploymentRule](Set-CMSoftwareUpdateAutoDeploymentRule)



* [New-CMSchedule](New-CMSchedule)





---


### Examples
#### Example 1: Create a basic ADR
```PowerShell
New-CMSoftwareUpdateAutoDeploymentRule -CollectionName "Desktops" -DeploymentPackageName "Updates123" -Name "DeploymentRule07" -ArticleId "117"
```

#### Example 2: Create an ADR that uses a schedule and other properties
```PowerShell
$Schedule = New-CMSchedule -DayOfWeek Wednesday

New-CMSoftwareUpdateAutoDeploymentRule -CollectionName "Laptops" -DeploymentPackageName "Updates235" -Name "DeploymentRule22" -AddToExistingSoftwareUpdateGroup $False -AlertTime 4 -AlertTimeUnit Weeks -AllowRestart $True -AllowSoftwareInstallationOutsideMaintenanceWindow $True -AllowUseMeteredNetwork $True -ArticleId "test" -AvailableImmediately $False -AvailableTime 5 -AvailableTimeUnit Months -CustomSeverity Critical -DateReleasedOrRevised Last1day -DeadlineImmediately $False -DeadlineTime $True -DeadlineTimeUnit Hours -DeployWithoutLicense $True -Description "Standard updates for our laptop systems." -DisableOperationManager $True -DownloadFromInternet $False -DownloadFromMicrosoftUpdate $True -EnabledAfterCreate $False -GenerateOperationManagerAlert $True -GenerateSuccessAlert $True -Location "\\k\aS_O15_Client_Dev_1" -NoInstallOnRemote $False -NoInstallOnUnprotected $True -RunType RunTheRuleOnSchedule -Schedule $Schedule -SendWakeUpPacket $True -SuccessPercent 99 -Superseded $True -SuppressRestartServer $True -SuppressRestartWorkstation $True -UpdateClassification "Critical Updates" -UseBranchCache $False -UserNotification DisplayAll -UseUtc $True -VerboseLevel AllMessages -WriteFilterHandling $True
```

#### Example 3: Create an ADR for multiple languages
```PowerShell
New-CMSoftwareUpdateAutoDeploymentRule -Name "Multi-language ADR" -CollectionId "XYZ0003F" -Language "English","Hungarian","Chinese (Simplified, PRC)" -Enable $false -EnabledAfterCreate $false -RunType DoNotRunThisRuleAutomatically -LanguageSelection "English","Hungarian","Chinese (Simplified, PRC)" -O365LanguageSelection "English (United States)","Hungarian (Hungary)","Chinese (Simplified, PRC)"
```



---


### Parameters
#### **AddToExistingSoftwareUpdateGroup**

Indicates whether the rule adds to an existing software update group.


* If this value is `$True`, each time the rule runs and finds new updates, it adds them to an existing update group.


* If this value is `$False`, it creates a new update group.




Specify the existing update group or assign a name for the new update group by using the -DeploymentPackageName parameter.







|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AlertTime**

Specifies an integer offset from an update deployment deadline. The rule uses this value to specify when the rule generates alerts. Specify a time unit by using the -AlertTimeUnit parameter.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **AlertTimeUnit**

Specifies a unit of time for the -AlertTime parameter.



Valid Values:

* Hours
* Days
* Weeks
* Months






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[TimeUnitType]`|false   |named   |False        |



#### **AllowRestart**

Indicates whether to allow a computer to restart if the update deployment takes place outside of a maintenance window. A maintenance window is a specified period of time used for computer maintenance and updates.


* If this value is `$True`, Configuration Manager restarts the computer, if necessary, to complete the update.


* If this value is `$False`, Configuration Manager doesn't restart the computer.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowSoftwareInstallationOutsideMaintenanceWindow**

Indicates whether the update deployment takes place even if scheduled outside of a maintenance window. A maintenance window is a specified period of time used for computer maintenance and updates.


* If this value is `$True`, Configuration Manager deploys the update even the scheduled time falls outside the service window.


* If this value is `$False`, Configuration Manager doesn't deploy the update outside the service window. It waits until it can deploy in a service window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowUseMeteredNetwork**

Indicates whether to allow clients to download content over a metered internet connection after the deadline, which may incur additional expense.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Architecture**

Use this parameter to set the Architecture property filter on the Software Updates page of the ADR properties.



Valid Values:

* Arm64
* Itanium
* X64
* X86






|Type                  |Required|Position|PipelineInput|Aliases      |
|----------------------|--------|--------|-------------|-------------|
|`[ArchitectureType[]]`|false   |named   |False        |Architectures|



#### **ArticleId**

Specifies an array of criteria, as strings, for software updates. The rule adds software updates that have article IDs that meet specified criteria to the software update group.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **AvailableImmediately**

Indicates whether this rule deploys updates as soon as the updates become available. If you select a value of `$False`, use the -AvailableTime and -AvailableTimeUnit parameters to specify how long after the rule runs to deploy the updates.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AvailableTime**

Specifies a period of time as an integer. Configuration Manager deploys the updates this long after the rule runs. Specify a time unit by using the -AvailableTimeUnit parameter.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **AvailableTimeUnit**

Specifies a unit of time for the -AvailableTime parameter.



Valid Values:

* Hours
* Days
* Weeks
* Months






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[TimeUnitType]`|false   |named   |False        |



#### **BulletinId**

Specifies an array of criteria, as strings, for software updates. The rule adds software updates that have bulletin IDs that meet specified criteria to the software update group.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **CMTag**

This property is reserved for future use.



Valid Values:

* None
* UUP






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[CMTagTypes[]]`|false   |named   |False        |



#### **Collection**

Specify a collection object as the target for the automatic deployment rule.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **CollectionId**

Specify a collection ID as the target for the automatic deployment rule.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **CollectionName**

Specify a collection name as the target for the automatic deployment rule.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ContentSize**

Use this parameter to set the Content Size (KB) property filter on the Software Updates page of the ADR properties.






|Type        |Required|Position|PipelineInput|Aliases     |
|------------|--------|--------|-------------|------------|
|`[String[]]`|false   |named   |False        |ContentSizes|



#### **CustomSeverity**

Specifies an array of custom severity types for software updates. The rule adds software updates that have custom severity levels that meet specified criteria to the software update group.



Valid Values:

* None
* Low
* Moderate
* Important
* Critical






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[SeverityType[]]`|false   |named   |False        |



#### **DateReleasedOrRevised**

Specifies a date released or revised for software updates. The rule adds software updates that have a date that meets specified criteria to the software update group.






|Type                         |Required|Position|PipelineInput|
|-----------------------------|--------|--------|-------------|
|`[DateReleasedOrRevisedType]`|false   |named   |False        |



#### **DeadlineImmediately**

Indicates whether to impose the deadline as soon as the rule runs. If you specify a value of `$False`, use the -DeadlineTime and -DeadlineTimeUnit parameters to specify how long after the rule runs to set the deadline. After the deadline, Configuration Manager installs required updates.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **DeadlineTime**

Specifies a period of time as an integer. The deadline for updates is this long after the rule runs. Specify a time unit by using the -DeadlineTimeUnit parameter.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **DeadlineTimeUnit**

Specifies a unit of time for the -DeadlineTime parameter.



Valid Values:

* Hours
* Days
* Weeks
* Months






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[TimeUnitType]`|false   |named   |False        |



#### **DeploymentPackage**

Use this parameter to specify an object for the deployment package to use with this automatic deployment rule. To not require a package, set the value to `$null`.






|Type             |Required|Position|PipelineInput |Aliases    |
|-----------------|--------|--------|--------------|-----------|
|`[IResultObject]`|false   |named   |True (ByValue)|InputObject|



#### **DeploymentPackageName**

Specify the name of the deployment package to use with this automatic deployment rule. To not require a package, set the value to `$null`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeploymentRing**





Valid Values:

* CB
* CB
* BusinessMainstream
* BusinessMainstream
* Ltsb






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[DeploymentRing]`|false   |named   |False        |



#### **DeployWithoutLicense**

Indicates whether the rule deploys updates without licenses.


* If you specify a value of `$True`, Configuration Manager deploys all updates for this rule and approves any license agreements.


* If this value is `$False`, Configuration Manager deploys only updates that don't include a license or for which the license agreement has been approved.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Description**

Specifies a description for the automatic deployment rule for software updates.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableOperationManager**

Indicates whether to disable System Center Operations Manager alerts during software updates.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DownloadFromInternet**

Indicates whether computers download software updates from the internet. If you specify a value of `$False`, specify an alternative location where computers can download updates by using the -Location parameter.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **DownloadFromMicrosoftUpdate**

Indicates whether computers download content from Microsoft Update if that content is unavailable on a preferred distribution point of remote distribution point.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Enable**

Specify whether the automatic deployment rule is enabled after you create it.






|Type       |Required|Position|PipelineInput|Aliases                     |
|-----------|--------|--------|-------------|----------------------------|
|`[Boolean]`|false   |named   |False        |Enabled<br/>EnableDeployment|



#### **EnabledAfterCreate**

Indicates whether to enable software deployment for the associated software update group after this rule runs. If this value is `$False`, deploy the software update group manually.






|Type       |Required|Position|PipelineInput|Aliases          |
|-----------|--------|--------|-------------|-----------------|
|`[Boolean]`|false   |named   |False        |EnableAfterCreate|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **GenerateFailureAlert**

If the rule fails, create a Configuration Manager alert.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **GenerateOperationManagerAlert**

Indicates whether to generate Operations Manager alerts during a software update.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **GenerateSuccessAlert**

Indicates whether to generate an alert for successful deployment.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **IsServicingPlan**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Language**

Specify a string array of language criteria for software updates. The rule adds software updates that have languages that meet specified criteria to the software update group.


Use the format of the language as displayed in the console. For example:


* `English`


* `Hungarian`


* `Chinese (Simplified, PRC)`




The format for the string array is: `"English","Hungarian","Chinese (Simplified, PRC)"`

> [!TIP] > If you run this cmdlet on a computer where Windows has a localized UI, the language names may be different. For example, the English version of Windows uses "Danish", but the Danish version of Windows uses "Dansk".







|Type        |Required|Position|PipelineInput|Aliases                                     |
|------------|--------|--------|-------------|--------------------------------------------|
|`[String[]]`|false   |named   |False        |Languages<br/>UpdateLocales<br/>UpdateLocale|



#### **LanguageSelection**

Specify a string array of languages. Clients download software updates available in the specified languages, and language-neutral updates.


Use the format of the language as displayed in the console. For example:


* `English`


* `Hungarian`


* `Chinese (Simplified, PRC)`




The format for the string array is: `"English","Hungarian","Chinese (Simplified, PRC)"`

> [!TIP] > If you run this cmdlet on a computer where Windows has a localized UI, the language names may be different. For example, the English version of Windows uses "Danish", but the Danish version of Windows uses "Dansk".







|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **Location**

Specifies a location in your network where computers can download software updates. In order to use this location, specify a value of `$False` for the -DownloadFromInternet parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **MicrosoftAsVendor**

Indicates whether the rule includes only updates that have Microsoft as the vendor.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Name**

Specifies a name for the automatic deployment rule for software updates.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **NoInstallOnRemote**

Indicates whether to disallow installation of updates on remote systems.


* If you specify a value of `$True`, if the client is within a slow or unreliable network boundary, or when the client uses a fallback source location for content, then Configuration Manager doesn't install software updates.


* If you specify a value of `$False`, installation proceeds.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **NoInstallOnUnprotected**

Indicates whether to disallow installation of updates on unprotected systems.


* If you specify a value of `$True`, if software updates aren't available on any preferred distribution points, Configuration Manager doesn't download and install software updates.


* If you specify a value of `$False`, installation proceeds.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **O365LanguageSelection**

Use this parameter to set the Office 365 Client Update language selection. Specify a string array of languages. Clients download software updates available in the specified languages, and language-neutral updates.


Use the format of the language as displayed in the console for the Windows Update language selection. This format is the same as the with the LanguageSelection parameter. For example:


* `English`


* `Hungarian`


* `Chinese (Simplified, PRC)`




The format for the string array is: `"English","Hungarian","Chinese (Simplified, PRC)"`


> [!TIP] > If you run this cmdlet on a computer where Windows has a localized UI, the language names may be different. For example, the English version of Windows uses "Danish", but the Danish version of Windows uses "Dansk".


You currently can't specify with this parameter all of the languages that are available in the Configuration Manager console. For example, you can't specify "Irish (Ireland)" or "Maltese (Malta)".<!-- CMADO-7059972 -->

Starting in version 2103, you need to specify a language with a country name. This change aligns this parameter with the options in the Configuration Manager console. For example, `-O365LanguageSelection "English (United States)"`







|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **Product**

Specifies an array of criteria, as strings, for software updates. The rule adds software updates for products that meet specified criteria to the software update group.


Starting in version 2107, when there are multiple products with the same name, it selects all of them.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **Required**

Specifies an array of criteria, as strings, for software updates. The rule adds software updates identified by required that meet specified criteria to the software update group.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **RequirePostRebootFullScan**

Use this parameter to set the following option on the User Experience page of the ADR deployment settings: If any update in this deployment requires a system restart, run updates deployment evaluation cycle after restart .






|Type       |Required|Position|PipelineInput|Aliases                  |
|-----------|--------|--------|-------------|-------------------------|
|`[Boolean]`|false   |named   |False        |RunEvaluationAfterRestart|



#### **RunType**

Specify the recurring schedule for when the site evaluates the ADR.


If you specify `RunTheRuleOnSchedule`, specify a schedule by using the -Schedule parameter.



Valid Values:

* DoNotRunThisRuleAutomatically
* RunTheRuleAfterAnySoftwareUpdatePointSynchronization
* RunTheRuleOnSchedule






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[RunType]`|false   |named   |False        |



#### **Schedule**

Specifies a schedule object for the deployment. To obtain a schedule object, use the New-CMSchedule (New-CMSchedule.md)cmdlet. Specify a schedule for this parameter if you specify a value of `RunTheRuleOnSchedule` for the -RunType parameter.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **SendWakeupPacket**

Indicates whether to send a wake up packet to computers before the deployment begins.


* If this value is `$True`, Configuration Manager wakes a computer from sleep.


* If this value is `$False`, it doesn't wake computers from sleep.




For computers to wake, you must first configure Wake On LAN.







|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Severity**

Specifies an array of severity levels for software updates. The rule adds software updates for specified severity types to the software update group.



Valid Values:

* None
* Low
* Moderate
* Important
* Critical






|Type              |Required|Position|PipelineInput|Aliases   |
|------------------|--------|--------|-------------|----------|
|`[SeverityType[]]`|false   |named   |False        |Severities|



#### **SoftDeadlineEnabled**

Use this parameter to set the following option on the Deployment Schedule page of the ADR deployment settings: Delay enforcement of this deployment according to user preferences, up to the grace period defined in client settings .






|Type       |Required|Position|PipelineInput|Aliases                           |
|-----------|--------|--------|-------------|----------------------------------|
|`[Boolean]`|false   |named   |False        |DelayEnforcementAndUpToGracePeriod|



#### **SuccessPercentage**

Specifies a percentage for client compliance as an integer from 0 to 99. If compliance falls below this percentage, Configuration Manager produces optional alerts.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **Superseded**

Indicates whether the rule adds updates superseded by other updates.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SuppressRestartServer**

Indicates whether to suppress a required update for a server. Some software updates require a system restart to complete the installation process.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SuppressRestartWorkstation**

Indicates whether to suppress a required update for a workstation. Some software updates require a system restart to complete the installation process.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Title**

Specifies an array of criteria, as strings, for software updates. The rule adds software updates that have titles that meet specified criteria to the software update group.






|Type        |Required|Position|PipelineInput|Aliases|
|------------|--------|--------|-------------|-------|
|`[String[]]`|false   |named   |False        |Titles |



#### **UpdateClassification**

Specifies an array of criteria, as strings, for software updates. The rule adds software updates that have update classifications that meet specified criteria to the software update group.






|Type        |Required|Position|PipelineInput|Aliases              |
|------------|--------|--------|-------------|---------------------|
|`[String[]]`|false   |named   |False        |UpdateClassifications|



#### **UpdateDeploymentWaitDay**








|Type     |Required|Position|PipelineInput|Aliases                 |
|---------|--------|--------|-------------|------------------------|
|`[Int32]`|false   |named   |False        |UpdateDeploymentWaitDays|



#### **UpdateDescription**

Specifies an array of criteria, as strings, for software updates. The rule adds software updates that have update descriptions that meet specified criteria to the software update group.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **UseBranchCache**

Indicates whether to use Windows BranchCache for this update deployment. If you specify a value of `$True`, clients share content on the same subnet.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UserNotification**

Specifies the type of user notification.


* `DisplayAll`: Display in Software Center and show all notifications.


* `DisplaySoftwareCenterOnly`: Display in Software Center, and only show notifications of computer restarts.


* `HideAll`: Hide in Software Center and all notifications.



Valid Values:

* DisplayAll
* DisplaySoftwareCenterOnly
* HideAll






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[UserNotificationType]`|false   |named   |False        |



#### **UseUtc**

Indicates whether to use Coordinated Universal Time (UTC).


* If this value is `$True`, Configuration Manager uses UTC for this deployment.


* If this value is `$False`, Configuration Manager uses local time.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Vendor**








|Type        |Required|Position|PipelineInput|Aliases|
|------------|--------|--------|-------------|-------|
|`[String[]]`|false   |named   |False        |Vendors|



#### **VerboseLevel**

Specifies the level of detail you want clients to report for deployments that this rule creates.



Valid Values:

* OnlyErrorMessages
* OnlySuccessAndErrorMessages
* AllMessages






|Type                |Required|Position|PipelineInput|
|--------------------|--------|--------|-------------|
|`[VerboseLevelType]`|false   |named   |False        |



#### **WriteFilterHandling**

Indicates whether to enable write filters for embedded devices.


* For a value of `$True`, the device commits changes during a maintenance window. This action requires a restart.


* For a value of `$False`, the device saves changes in an overlay and commits them later.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject#SMS_AutoDeployment






---


### Notes
For more information on this return object and its properties, see SMS_AutoDeployment server WMI class (/mem/configmgr/develop/reference/sum/sms_autodeployment-server-wmi-class).



---


### Syntax
```PowerShell
New-CMSoftwareUpdateAutoDeploymentRule [-AddToExistingSoftwareUpdateGroup <Boolean>] [-AlertTime <Int32>] [-AlertTimeUnit {Hours | Days | Weeks | Months}] [-AllowRestart <Boolean>] [-AllowSoftwareInstallationOutsideMaintenanceWindow <Boolean>] [-AllowUseMeteredNetwork <Boolean>] [-Architecture {Arm64 | Itanium | X64 | X86}] [-ArticleId <String[]>] [-AvailableImmediately <Boolean>] [-AvailableTime <Int32>] [-AvailableTimeUnit {Hours | Days | Weeks | Months}] [-BulletinId <String[]>] [-CMTag {None | UUP}] -Collection <IResultObject> [-ContentSize <String[]>] [-CustomSeverity {None | Low | Moderate | Important | Critical}] [-DateReleasedOrRevised {Any | Last1Hour | LastHour | Last2Hours | Last3Hours | Last4Hours | Last8Hours | Last12Hours | Last16Hours | Last20Hours | Last1Day | LastDay | Last2Days | Last3Days | Last4Days | Last5Days | Last6Days | Last7Days | Last14Days | Last21Days | Last28Days | LastMonth | Last1Month | Last2Months | Last3Months | Last4Months | Last5Months | Last6Months | Last7Months | Last8Months | Last9Months | Last10Months | Last11Months | Last1Year | LastYear | Last12Months}] [-DeadlineImmediately <Boolean>] [-DeadlineTime <Int32>] [-DeadlineTimeUnit {Hours | Days | Weeks | Months}] [-DeploymentPackage <IResultObject>] [-DeploymentPackageName <String>] [-DeploymentRing {CB | Release | BusinessMainstream | Cbb | Ltsb}] [-DeployWithoutLicense <Boolean>] [-Description <String>] [-DisableOperationManager <Boolean>] [-DisableWildcardHandling] [-DownloadFromInternet <Boolean>] [-DownloadFromMicrosoftUpdate <Boolean>] [-Enable <Boolean>] [-EnabledAfterCreate <Boolean>] [-ForceWildcardHandling] [-GenerateFailureAlert <Boolean>] [-GenerateOperationManagerAlert <Boolean>] [-GenerateSuccessAlert <Boolean>] [-IsServicingPlan] [-Language <String[]>] [-LanguageSelection <String[]>] [-Location <String>] [-MicrosoftAsVendor <Boolean>] -Name <String> [-NoInstallOnRemote <Boolean>] [-NoInstallOnUnprotected <Boolean>] [-O365LanguageSelection <String[]>] [-Product <String[]>] [-Required <String[]>] [-RequirePostRebootFullScan <Boolean>] [-RunType {DoNotRunThisRuleAutomatically | RunTheRuleAfterAnySoftwareUpdatePointSynchronization | RunTheRuleOnSchedule}] [-Schedule <IResultObject>] [-SendWakeupPacket <Boolean>] [-Severity {None | Low | Moderate | Important | Critical}] [-SoftDeadlineEnabled <Boolean>] [-SuccessPercentage <Int32>] [-Superseded <Boolean>] [-SuppressRestartServer <Boolean>] [-SuppressRestartWorkstation <Boolean>] [-Title <String[]>] [-UpdateClassification <String[]>] [-UpdateDeploymentWaitDay <Int32>] [-UpdateDescription <String[]>] [-UseBranchCache <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-UseUtc <Boolean>] [-Vendor <String[]>] [-VerboseLevel {OnlyErrorMessages | OnlySuccessAndErrorMessages | AllMessages}] [-WriteFilterHandling <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSoftwareUpdateAutoDeploymentRule [-AddToExistingSoftwareUpdateGroup <Boolean>] [-AlertTime <Int32>] [-AlertTimeUnit {Hours | Days | Weeks | Months}] [-AllowRestart <Boolean>] [-AllowSoftwareInstallationOutsideMaintenanceWindow <Boolean>] [-AllowUseMeteredNetwork <Boolean>] [-Architecture {Arm64 | Itanium | X64 | X86}] [-ArticleId <String[]>] [-AvailableImmediately <Boolean>] [-AvailableTime <Int32>] [-AvailableTimeUnit {Hours | Days | Weeks | Months}] [-BulletinId <String[]>] [-CMTag {None | UUP}] -CollectionId <String> [-ContentSize <String[]>] [-CustomSeverity {None | Low | Moderate | Important | Critical}] [-DateReleasedOrRevised {Any | Last1Hour | LastHour | Last2Hours | Last3Hours | Last4Hours | Last8Hours | Last12Hours | Last16Hours | Last20Hours | Last1Day | LastDay | Last2Days | Last3Days | Last4Days | Last5Days | Last6Days | Last7Days | Last14Days | Last21Days | Last28Days | LastMonth | Last1Month | Last2Months | Last3Months | Last4Months | Last5Months | Last6Months | Last7Months | Last8Months | Last9Months | Last10Months | Last11Months | Last1Year | LastYear | Last12Months}] [-DeadlineImmediately <Boolean>] [-DeadlineTime <Int32>] [-DeadlineTimeUnit {Hours | Days | Weeks | Months}] [-DeploymentPackage <IResultObject>] [-DeploymentPackageName <String>] [-DeploymentRing {CB | Release | BusinessMainstream | Cbb | Ltsb}] [-DeployWithoutLicense <Boolean>] [-Description <String>] [-DisableOperationManager <Boolean>] [-DisableWildcardHandling] [-DownloadFromInternet <Boolean>] [-DownloadFromMicrosoftUpdate <Boolean>] [-Enable <Boolean>] [-EnabledAfterCreate <Boolean>] [-ForceWildcardHandling] [-GenerateFailureAlert <Boolean>] [-GenerateOperationManagerAlert <Boolean>] [-GenerateSuccessAlert <Boolean>] [-IsServicingPlan] [-Language <String[]>] [-LanguageSelection <String[]>] [-Location <String>] [-MicrosoftAsVendor <Boolean>] -Name <String> [-NoInstallOnRemote <Boolean>] [-NoInstallOnUnprotected <Boolean>] [-O365LanguageSelection <String[]>] [-Product <String[]>] [-Required <String[]>] [-RequirePostRebootFullScan <Boolean>] [-RunType {DoNotRunThisRuleAutomatically | RunTheRuleAfterAnySoftwareUpdatePointSynchronization | RunTheRuleOnSchedule}] [-Schedule <IResultObject>] [-SendWakeupPacket <Boolean>] [-Severity {None | Low | Moderate | Important | Critical}] [-SoftDeadlineEnabled <Boolean>] [-SuccessPercentage <Int32>] [-Superseded <Boolean>] [-SuppressRestartServer <Boolean>] [-SuppressRestartWorkstation <Boolean>] [-Title <String[]>] [-UpdateClassification <String[]>] [-UpdateDeploymentWaitDay <Int32>] [-UpdateDescription <String[]>] [-UseBranchCache <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-UseUtc <Boolean>] [-Vendor <String[]>] [-VerboseLevel {OnlyErrorMessages | OnlySuccessAndErrorMessages | AllMessages}] [-WriteFilterHandling <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSoftwareUpdateAutoDeploymentRule [-AddToExistingSoftwareUpdateGroup <Boolean>] [-AlertTime <Int32>] [-AlertTimeUnit {Hours | Days | Weeks | Months}] [-AllowRestart <Boolean>] [-AllowSoftwareInstallationOutsideMaintenanceWindow <Boolean>] [-AllowUseMeteredNetwork <Boolean>] [-Architecture {Arm64 | Itanium | X64 | X86}] [-ArticleId <String[]>] [-AvailableImmediately <Boolean>] [-AvailableTime <Int32>] [-AvailableTimeUnit {Hours | Days | Weeks | Months}] [-BulletinId <String[]>] [-CMTag {None | UUP}] -CollectionName <String> [-ContentSize <String[]>] [-CustomSeverity {None | Low | Moderate | Important | Critical}] [-DateReleasedOrRevised {Any | Last1Hour | LastHour | Last2Hours | Last3Hours | Last4Hours | Last8Hours | Last12Hours | Last16Hours | Last20Hours | Last1Day | LastDay | Last2Days | Last3Days | Last4Days | Last5Days | Last6Days | Last7Days | Last14Days | Last21Days | Last28Days | LastMonth | Last1Month | Last2Months | Last3Months | Last4Months | Last5Months | Last6Months | Last7Months | Last8Months | Last9Months | Last10Months | Last11Months | Last1Year | LastYear | Last12Months}] [-DeadlineImmediately <Boolean>] [-DeadlineTime <Int32>] [-DeadlineTimeUnit {Hours | Days | Weeks | Months}] [-DeploymentPackage <IResultObject>] [-DeploymentPackageName <String>] [-DeploymentRing {CB | Release | BusinessMainstream | Cbb | Ltsb}] [-DeployWithoutLicense <Boolean>] [-Description <String>] [-DisableOperationManager <Boolean>] [-DisableWildcardHandling] [-DownloadFromInternet <Boolean>] [-DownloadFromMicrosoftUpdate <Boolean>] [-Enable <Boolean>] [-EnabledAfterCreate <Boolean>] [-ForceWildcardHandling] [-GenerateFailureAlert <Boolean>] [-GenerateOperationManagerAlert <Boolean>] [-GenerateSuccessAlert <Boolean>] [-IsServicingPlan] [-Language <String[]>] [-LanguageSelection <String[]>] [-Location <String>] [-MicrosoftAsVendor <Boolean>] -Name <String> [-NoInstallOnRemote <Boolean>] [-NoInstallOnUnprotected <Boolean>] [-O365LanguageSelection <String[]>] [-Product <String[]>] [-Required <String[]>] [-RequirePostRebootFullScan <Boolean>] [-RunType {DoNotRunThisRuleAutomatically | RunTheRuleAfterAnySoftwareUpdatePointSynchronization | RunTheRuleOnSchedule}] [-Schedule <IResultObject>] [-SendWakeupPacket <Boolean>] [-Severity {None | Low | Moderate | Important | Critical}] [-SoftDeadlineEnabled <Boolean>] [-SuccessPercentage <Int32>] [-Superseded <Boolean>] [-SuppressRestartServer <Boolean>] [-SuppressRestartWorkstation <Boolean>] [-Title <String[]>] [-UpdateClassification <String[]>] [-UpdateDeploymentWaitDay <Int32>] [-UpdateDescription <String[]>] [-UseBranchCache <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-UseUtc <Boolean>] [-Vendor <String[]>] [-VerboseLevel {OnlyErrorMessages | OnlySuccessAndErrorMessages | AllMessages}] [-WriteFilterHandling <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

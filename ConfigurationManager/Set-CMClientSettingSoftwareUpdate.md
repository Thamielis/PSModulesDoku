Set-CMClientSettingSoftwareUpdate
---------------------------------




### Synopsis
Configure client settings for software updates.



---


### Description

Use this cmdlet to configure settings in the Software updates group of client settings. For more information, see About client settings: Software updates (/mem/configmgr/core/clients/deploy/about-client-settings#software-updates).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMClientSetting](Get-CMClientSetting)



* [Remove-CMClientSetting](Remove-CMClientSetting)



* [New-CMSchedule](New-CMSchedule)



* [About client settings: Software updates](About client settings: Software updates)





---


### Examples
#### Example 1: Enable third-party updates in the default client settings
```PowerShell
Set-CMClientSettingSoftwareUpdate -DefaultSetting -Enable $true -EnableThirdPartyUpdates $true
```

#### Example 2: Enable third-party updates in a custom device setting
```PowerShell
$clientDeviceSettingName = "Dev device settings"
Set-CMClientSettingSoftwareUpdate -Name $clientDeviceSettingName -Enable $true -EnableThirdPartyUpdates $true
```

#### Example 3: Configure multiple settings
```PowerShell
Set-CMClientSettingSoftwareUpdate -InputObject $testsetting -Enable $true -ScanSchedule $Sch1 -DeploymentEvaluationSchedule $Sch2 -BatchingTimeout 3 -TimeUnit Days -EnforceMandatory $true -Office365ManagementType $false -EnableThirdPartyUpdates $true -EnableDeltaDownload $true -EnableInstallation $true -ThreadPriority Normal -EnableDynamicUpdate $true
```



---


### Parameters
#### **BatchingTimeout**

Specify the period of time for which all pending deployments with a deadline in this time will also be installed. Use this parameter with the EnforceMandatory parameter. You can enter a value from 1 to 23 hours, and from 1 to 365 days. By default, this setting is configured for seven days. Use the TimeUnit parameter to specify hours or days.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **DefaultSetting**

Add this parameter to configure software update settings in the default client settings.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **DeltaDownloadPort**

Use this parameter to configure the network port that clients use to receive requests for delta content. Use the EnableDeltaDownload parameter to enable the behavior. The default value is `8005`.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **DeploymentEvaluationSchedule**

Specify how often the software updates client agent reevaluates software updates for installation status on Configuration Manager client computers. To create a new schedule token, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Enable**

Set this parameter to `$true` to enable software updates on clients.






|Type       |Required|Position|PipelineInput|Aliases                      |
|-----------|--------|--------|-------------|-----------------------------|
|`[Boolean]`|false   |named   |False        |EnableSoftwareUpdatesOnClient|



#### **EnableDeltaDownload**

Set this parameter to `$true` to allow clients to download delta content when available. To configure the network port, use the DeltaDownloadPort parameter.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableDynamicUpdate**

Applies to version 2010 and later. Set this parameter to `$true` to enable dynamic update for Windows 10 feature updates. Dynamic update installs language packs, features on demand, drivers, and cumulative updates during Windows setup. It directs the client to download these updates from the internet.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableInstallation**

Applies to version 2010 and later. Set this parameter to `$true` to enable installation of software updates in the "All deployments" maintenance window when the "Software Update" maintenance window is available.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableThirdPartyUpdates**

Set this parameter to `$true` to enable third-party software updates.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableWsusCertPinning**

Applies to version 2107 and later. Set this parameter to `$true` to enforce TLS certificate pinning for Windows Update client for detecting updates.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnforceMandatory**

When any software update deployment deadline is reached, install all other software update deployments with deadline coming within a specified period of time. Use the BatchingTimeout parameter to specify the period of time.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

This cmdlet adds the software update settings to the client settings object that you specify with this parameter. To get this object, use the Get-CMClientSetting (Get-CMClientSetting.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

This cmdlet adds the software update settings to the client settings object that this parameter names.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Office365ManagementType**

Set this parameter to `$true` to enable management of the Microsoft 365 Apps client agent and installation settings.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **PassThru**

Returns an object representing the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ScanSchedule**

Specify how often the software updates client agent starts a compliance assessment scan. This scan determines the state for software updates on the client. To create a new schedule token, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **ThreadPriority**

Applies to version 2010 and later. Specify a thread priority for Windows 10 feature updates.


* `Normal`: Windows Setup uses more system resources and updates faster. It uses more processor time, so the total installation time is shorter, but the user's outage is longer. This value is the default.


* `Low`: You can continue to work on the device while it downloads and updates in the background. The total installation time is longer, but the user's outage is shorter. You may need to increase the update max run time to avoid a time-out when you use this option.






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[ThreadPriorityType]`|false   |named   |False        |



#### **TimeUnit**

Use with the BatchingTimeout parameter to specify the period of time for which all pending deployments with a deadline in this time will also be installed.



Valid Values:

* Days
* Hours






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[BatchingTimeoutType]`|false   |named   |False        |



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
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMClientSettingSoftwareUpdate [-BatchingTimeout <Int32>] -DefaultSetting [-DeltaDownloadPort <Int32>] [-DeploymentEvaluationSchedule <IResultObject>] [-DisableWildcardHandling] [-Enable <Boolean>] [-EnableDeltaDownload <Boolean>] [-EnableDynamicUpdate <Boolean>] [-EnableInstallation <Boolean>] [-EnableThirdPartyUpdates <Boolean>] [-EnableWsusCertPinning <Boolean>] [-EnforceMandatory <Boolean>] [-ForceWildcardHandling] [-Office365ManagementType <Boolean>] [-PassThru] [-ScanSchedule <IResultObject>] [-ThreadPriority {Normal | Low}] [-TimeUnit {Days | Hours}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingSoftwareUpdate [-BatchingTimeout <Int32>] [-DeltaDownloadPort <Int32>] [-DeploymentEvaluationSchedule <IResultObject>] [-DisableWildcardHandling] [-Enable <Boolean>] [-EnableDeltaDownload <Boolean>] [-EnableDynamicUpdate <Boolean>] [-EnableInstallation <Boolean>] [-EnableThirdPartyUpdates <Boolean>] [-EnableWsusCertPinning <Boolean>] [-EnforceMandatory <Boolean>] [-ForceWildcardHandling] -InputObject <IResultObject> [-Office365ManagementType <Boolean>] [-PassThru] [-ScanSchedule <IResultObject>] [-ThreadPriority {Normal | Low}] [-TimeUnit {Days | Hours}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingSoftwareUpdate [-BatchingTimeout <Int32>] [-DeltaDownloadPort <Int32>] [-DeploymentEvaluationSchedule <IResultObject>] [-DisableWildcardHandling] [-Enable <Boolean>] [-EnableDeltaDownload <Boolean>] [-EnableDynamicUpdate <Boolean>] [-EnableInstallation <Boolean>] [-EnableThirdPartyUpdates <Boolean>] [-EnableWsusCertPinning <Boolean>] [-EnforceMandatory <Boolean>] [-ForceWildcardHandling] -Name <String> [-Office365ManagementType <Boolean>] [-PassThru] [-ScanSchedule <IResultObject>] [-ThreadPriority {Normal | Low}] [-TimeUnit {Days | Hours}] [-Confirm] [-WhatIf] [<CommonParameters>]
```

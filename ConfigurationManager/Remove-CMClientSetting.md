Remove-CMClientSetting
----------------------




### Synopsis
Removes client settings.



---


### Description

The Remove-CMClientSetting cmdlet removes a customized collection of client settings. For more information, see About Client Settings in Configuration Manager (/mem/configmgr/core/clients/deploy/about-client-settings).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [About Client Settings in Configuration Manager](About Client Settings in Configuration Manager)



* [Get-CMClientSetting](Get-CMClientSetting)



* [New-CMClientSetting](New-CMClientSetting)



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
#### Example 1: Remove a collection of client settings that is specified by its ID
```PowerShell
PS XYZ:\> Remove-CMClientSetting -Id "16777255"
```
This command removes a collection of client settings that is specified by the ID 16777255. You must confirm the action before it is performed.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Forces the command to run without asking for user confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies an array of identifiers for one or more collections of client settings.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |named   |False        |SettingsId|



#### **InputObject**

Specifies an input object for this cmdlet. You can get an input object by using Get-CMClientSetting.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies a name for customized client settings.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
Remove-CMClientSetting [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMClientSetting [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMClientSetting [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```

New-CMClientSetting
-------------------




### Synopsis
Creates customized client settings.



---


### Description

The New-CMClientSetting cmdlet creates a collection of customized settings for Configuration Manager client computers. After you create the customized settings and deploy them to client computer collections, the customized settings override the default client settings for that collection.



For more information about client settings, see About Client Settings in Configuration Manager (/mem/configmgr/core/clients/deploy/about-client-settings).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [About Client Settings in Configuration Manager](About Client Settings in Configuration Manager)



* [Get-CMClientSetting](Get-CMClientSetting)



* [Remove-CMClientSetting](Remove-CMClientSetting)



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
#### Example 1: Create a customized collection of client settings
```PowerShell
PS XYZ:\> New-CMClientSetting -Name "Win08ClientSettings" -Description "Windows 8 Client Computers Settings" -Type 1
AgentConfigurations: {}
AssignmentCount:     0
CreatedBy:           Contoso\DChew
DateCreated:         8/04/2012 4:40:03 PM
DateModified:        8/04/2012 4:40:03 PM
Description:         Windows 8 Client Computers Settings
Enabled:             False
FeatureType:         1
Flags:               0
LastModifiedBy:      Contoso\DChew
Name:                Win08ClientSettings
Priority:            0
SecuredScopeNames:   {Default}
Settings ID:         16777220
Type:                1
UniqueID:            {0CCA6700-AE5E-4949-8FBC-AA6719775CC3}
```
This command creates customized device settings for the group of client computers that run Windows� 8. After the new collection of settings is created, the command displays an unpopulated list of setting properties. To refresh and view a populated list of properties, use Get-CMClientSetting . The output for this example shows a populated list.


---


### Parameters
#### **Description**

Specifies a description of the content of the new settings.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Name**

Specifies a name for customized client settings.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Type**

Specifies the type of customized settings. Valid values are: 1 (device) or 2 (user).



Valid Values:

* Default
* Device
* User






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Types]`|true    |named   |False        |



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
* IResultObject#SMS_ClientSettings






---


### Notes




---


### Syntax
```PowerShell
New-CMClientSetting [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> -Type {Default | Device | User} [-Confirm] [-WhatIf] [<CommonParameters>]
```

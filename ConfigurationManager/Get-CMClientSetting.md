Get-CMClientSetting
-------------------




### Synopsis
Gets client settings.



---


### Description

The Get-CMClientSetting cmdlet gets a customized collection of client settings.



For more information about client settings, see About Client Settings in Configuration Manager (/mem/configmgr/core/clients/deploy/about-client-settings).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [About Client Settings in Configuration Manager](About Client Settings in Configuration Manager)



* [New-CMClientSetting](New-CMClientSetting)



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
#### Example 1: Get a collection of customized client settings that is specified by its name
```PowerShell
PS XYZ:\> Get-CMClientSetting -Name "Windows 8 Client Computers Settings"
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
This command gets client settings that have the specified name.


---


### Parameters
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



#### **Id**

Specifies an array of identifiers for one or more collections of client settings.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |named   |False        |SettingsId|



#### **Name**

Specifies a name for customized client settings.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Raw**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Setting**

Specifies an array of setting types for one or more collections of client settings.


Valid values are:


* BackgroundIntelligentTransfer


* ClientPolicy


* Cloud


* ComplianceSettings


* ComputerAgent


* ComputerRestart


* EndpointProtection


* HardwareInventory


* MeteredNetwork


* MobileDevice


* NetworkAccessProtection


* PowerManagement


* RemoteTools


* SoftwareDeployment


* SoftwareInventory


* SoftwareMetering


* SoftwareUpdates


* StateMessaging


* UserAndDeviceAffinity



Valid Values:

* BackgroundIntelligentTransfer
* Cloud
* ClientCache
* ClientPolicy
* ComplianceSettings
* ComputerAgent
* ComputerRestart
* DeliveryOptimization
* EndpointProtection
* HardwareInventory
* MeteredNetwork
* MobileDevice
* NetworkAccessProtection
* PowerManagement
* RemoteTools
* SoftwareCenter
* SoftwareDeployment
* SoftwareInventory
* SoftwareMetering
* SoftwareUpdates
* StateMessaging
* UserAndDeviceAffinity
* WindowsAnalytics






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[SettingType]`|false   |named   |False        |



#### **SettingType**





Valid Values:

* Default
* Device
* User






|Type     |Required|Position|PipelineInput|Aliases|
|---------|--------|--------|-------------|-------|
|`[Types]`|false   |named   |False        |Type   |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_ClientSettings


* IResultObject#SMS_ClientSettings


* IResultObject#SMS_ClientSettingsDefault


* Dictionary<string, object>






---


### Notes




---


### Syntax
```PowerShell
Get-CMClientSetting [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-Raw] [-Setting {BackgroundIntelligentTransfer | Cloud | ClientCache | ClientPolicy | ComplianceSettings | ComputerAgent | ComputerRestart | DeliveryOptimization | EndpointProtection | HardwareInventory | MeteredNetwork | MobileDevice | NetworkAccessProtection | PowerManagement | RemoteTools | SoftwareCenter | SoftwareDeployment | SoftwareInventory | SoftwareMetering | SoftwareUpdates | StateMessaging | UserAndDeviceAffinity | WindowsAnalytics}] [-SettingType {Default | Device | User}] [<CommonParameters>]
```
```PowerShell
Get-CMClientSetting [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [-Raw] [-Setting {BackgroundIntelligentTransfer | Cloud | ClientCache | ClientPolicy | ComplianceSettings | ComputerAgent | ComputerRestart | DeliveryOptimization | EndpointProtection | HardwareInventory | MeteredNetwork | MobileDevice | NetworkAccessProtection | PowerManagement | RemoteTools | SoftwareCenter | SoftwareDeployment | SoftwareInventory | SoftwareMetering | SoftwareUpdates | StateMessaging | UserAndDeviceAffinity | WindowsAnalytics}] [-SettingType {Default | Device | User}] [<CommonParameters>]
```

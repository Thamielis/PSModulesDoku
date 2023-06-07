Get-CMResultantSettings
-----------------------




### Synopsis
Gets a resultant settings.



---


### Description

> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1
```PowerShell
PS XYZ:\>
```



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








|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |named   |False        |ResourceId|



#### **InputObject**








|Type             |Required|Position|PipelineInput |Aliases        |
|-----------------|--------|--------|--------------|---------------|
|`[IResultObject]`|true    |named   |True (ByValue)|Device<br/>User|



#### **Name**








|Type      |Required|Position|PipelineInput|Aliases                |
|----------|--------|--------|-------------|-----------------------|
|`[String]`|true    |named   |False        |DeviceName<br/>UserName|



#### **Setting**





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



#### **SettingsType**





Valid Values:

* Device
* User






|Type                     |Required|Position|PipelineInput|
|-------------------------|--------|--------|-------------|
|`[ResultantSettingsType]`|true    |named   |False        |





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
Get-CMResultantSettings [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-Setting {BackgroundIntelligentTransfer | Cloud | ClientCache | ClientPolicy | ComplianceSettings | ComputerAgent | ComputerRestart | DeliveryOptimization | EndpointProtection | HardwareInventory | MeteredNetwork | MobileDevice | NetworkAccessProtection | PowerManagement | RemoteTools | SoftwareCenter | SoftwareDeployment | SoftwareInventory | SoftwareMetering | SoftwareUpdates | StateMessaging | UserAndDeviceAffinity | WindowsAnalytics}] -SettingsType {Device | User} [<CommonParameters>]
```
```PowerShell
Get-CMResultantSettings [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Setting {BackgroundIntelligentTransfer | Cloud | ClientCache | ClientPolicy | ComplianceSettings | ComputerAgent | ComputerRestart | DeliveryOptimization | EndpointProtection | HardwareInventory | MeteredNetwork | MobileDevice | NetworkAccessProtection | PowerManagement | RemoteTools | SoftwareCenter | SoftwareDeployment | SoftwareInventory | SoftwareMetering | SoftwareUpdates | StateMessaging | UserAndDeviceAffinity | WindowsAnalytics}] -SettingsType {Device | User} [<CommonParameters>]
```
```PowerShell
Get-CMResultantSettings [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Setting {BackgroundIntelligentTransfer | Cloud | ClientCache | ClientPolicy | ComplianceSettings | ComputerAgent | ComputerRestart | DeliveryOptimization | EndpointProtection | HardwareInventory | MeteredNetwork | MobileDevice | NetworkAccessProtection | PowerManagement | RemoteTools | SoftwareCenter | SoftwareDeployment | SoftwareInventory | SoftwareMetering | SoftwareUpdates | StateMessaging | UserAndDeviceAffinity | WindowsAnalytics}] -SettingsType {Device | User} [<CommonParameters>]
```

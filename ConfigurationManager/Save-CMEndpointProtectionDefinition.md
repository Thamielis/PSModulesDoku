Save-CMEndpointProtectionDefinition
-----------------------------------




### Synopsis
Saves an Endpoint Protection definition.



---


### Description

The Save-CMEndpointProtectionDefinition cmdlet saves a System Center 2016 Endpoint Protection definition in Configuration Manager. Endpoint Protection definitions contain anti-malware policies and settings for Windows Firewall that you can apply to specific groups of computers.



For more information about Endpoint Protection, see Endpoint Protection in Configuration Manager (/mem/configmgr/protect/deploy-use/endpoint-protection).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Endpoint Protection in Configuration Manager](Endpoint Protection in Configuration Manager)



* [Add-CMEndpointProtectionPoint](Add-CMEndpointProtectionPoint)



* [Get-CMEndpointProtectionPoint](Get-CMEndpointProtectionPoint)



* [Remove-CMEndpointProtectionPoint](Remove-CMEndpointProtectionPoint)



* [Get-CMDevice](Get-CMDevice)



* [Get-CMDeviceCollection](Get-CMDeviceCollection)





---


### Examples
#### Example 1: Save an Endpoint Protection epshort definition by using a device collection nameepshortEndpoint Protection
```PowerShell
PS XYZ:\> Save-CMEndpointProtectionDefinition -DeviceCollectionName "NA-Client-Devices"
```
This command saves the Endpoint Protection definition to the devices in the device collection named NA-Client-Devices.


---


### Parameters
#### **Device**

Specifies a device object in Configuration Manager. To obtain a device object, use the Get-CMDevice (Get-CMDevice.md)cmdlet. This object identifies the device to which you save the Endpoint Protection definition.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|false   |named   |True (ByValue)|



#### **DeviceCollection**

Specifies a device collection object in Configuration Manager. To obtain a device collection object, use the Get-CMDeviceCollection (Get-CMDeviceCollection.md)cmdlet. This object identifies the device collection to which you save the Endpoint Protection definition.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **DeviceCollectionId**

Specifies an ID for a Configuration Manager device collection to which you add the Endpoint Protection definition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DeviceCollectionName**

Specifies a name for a Configuration Manager device collection to which you add the Endpoint Protection definition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DeviceId**

Specifies the ID of a Configuration Manager device to which you add the Endpoint Protection definition.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|false   |named   |False        |ResourceID|



#### **DeviceName**

Specifies the name of a Configuration Manager device to which you save the Endpoint Protection definition.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |Name   |



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
Save-CMEndpointProtectionDefinition [-Device <IResultObject>] -DeviceCollection <IResultObject> [-DeviceId <String>] [-DeviceName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Save-CMEndpointProtectionDefinition [-Device <IResultObject>] -DeviceCollectionId <String> [-DeviceId <String>] [-DeviceName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Save-CMEndpointProtectionDefinition [-Device <IResultObject>] -DeviceCollectionName <String> [-DeviceId <String>] [-DeviceName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```

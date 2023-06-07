Clear-CMPxeDeployment
---------------------




### Synopsis
Clears the status of the most recent PXE deployment in Configuration Manager.



---


### Description

The Clear-CMPxeDeployment cmdlet clears the status of the most recent Pre-Boot EXecution Environment (PXE) deployment in Configuration Manager.



You can redeploy a required PXE deployment for a collection of devices. Clear the status of the last PXE deployment assigned to that Configuration Manager collection. Configuration Manager redeploys the most recent required deployments.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDevice](Get-CMDevice)



* [Get-CMDeviceCollection](Get-CMDeviceCollection)





---


### Examples
#### Example 1: Clear a PXE deployment for a device collection
```PowerShell
PS XYZ:\>Clear-CMPxeDeployment -DeviceCollectionId "SMS00072"
```
This command clears a PXE deployment identified with a device collection ID.


---


### Parameters
#### **Device**

Specifies a device object. To obtain a device object, use the Get-CMDevice (Get-CMDevice.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **DeviceCollection**

Specifies a device collection object. To obtain a device collection object, use the Get-CMDeviceCollection (Get-CMDeviceCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection|



#### **DeviceCollectionId**

Specifies an array of IDs of device collections.






|Type        |Required|Position|PipelineInput|Aliases                                               |
|------------|--------|--------|-------------|------------------------------------------------------|
|`[String[]]`|true    |named   |False        |CollectionId<br/>DeviceCollectionIds<br/>CollectionIds|



#### **DeviceCollectionName**

Specifies an array of names of device collections.






|Type        |Required|Position|PipelineInput|Aliases                                                     |
|------------|--------|--------|-------------|------------------------------------------------------------|
|`[String[]]`|true    |named   |False        |CollectionName<br/>DeviceCollectionNames<br/>CollectionNames|



#### **DeviceName**

Specifies an array of names of devices.






|Type        |Required|Position|PipelineInput|Aliases    |
|------------|--------|--------|-------------|-----------|
|`[String[]]`|true    |named   |False        |DeviceNames|



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



#### **ResourceId**

Specifies an array of IDs for resources. The cmdlet clears the status of the PXE deployment for these resources.






|Type       |Required|Position|PipelineInput|Aliases    |
|-----------|--------|--------|-------------|-----------|
|`[Int32[]]`|true    |named   |False        |ResourceIds|



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
Clear-CMPxeDeployment -Device <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Clear-CMPxeDeployment -DeviceCollection <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Clear-CMPxeDeployment -DeviceCollectionId <String[]> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Clear-CMPxeDeployment -DeviceCollectionName <String[]> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Clear-CMPxeDeployment -DeviceName <String[]> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Clear-CMPxeDeployment [-DisableWildcardHandling] [-ForceWildcardHandling] -ResourceId <Int32[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```

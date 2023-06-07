Remove-CMDevice
---------------




### Synopsis
Removes a client device from Configuration Manager.



---


### Description

The Remove-CMDevice cmdlet removes one or more Configuration Manager client devices. Do not remove a client if you want to uninstall the client or remove it from a collection.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Approve-CMDevice](Approve-CMDevice)



* [Block-CMDevice](Block-CMDevice)



* [Get-CMDevice](Get-CMDevice)



* [Unblock-CMDevice](Unblock-CMDevice)





---


### Examples
#### Example 1: Remove a device by name
```PowerShell
PS XYZ:\> Remove-CMDevice -DeviceName "WIN10-86-33"
```
This command removes the device named WIN10-86-33.
#### Example 2: Get a device and remove it
```PowerShell
PS XYZ:\> Get-CMDevice -Name "TestVLAN-VNEXT" | Remove-CMDevice
```
This command gets the device object named TestVLAN-VNEXT and uses the pipeline operator to pass the object to Remove-CMDevice , which removes the device object.


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



#### **InputObject**

Specifies a device object. To obtain a device object, use the Get-CMDevice (Get-CMDevice.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **Name**

Specifies the name of a device.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |0       |False        |DeviceName|



#### **ResourceId**

Specifies the resource ID of a device.






|Type     |Required|Position|PipelineInput|Aliases        |
|---------|--------|--------|-------------|---------------|
|`[Int32]`|true    |0       |False        |Id<br/>DeviceId|



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
Remove-CMDevice [-InputObject] <IResultObject> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDevice [-Name] <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDevice [-ResourceId] <Int32> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```

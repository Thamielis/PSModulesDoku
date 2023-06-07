Block-CMDevice
--------------




### Synopsis
Blocks a device.



---


### Description

The Block-CMDevice cmdlet blocks one or more client devices. You must block a device from the client's assigned site. You cannot block the device from sites higher in the hierarchy. Blocked devices are ignored by the Configuration Manager hierarchy. To unblock a device, use the Unblock-CMDevice (Unblock-CMDevice.md)cmdlet.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Approve-CMDevice](Approve-CMDevice)



* [Get-CMDevice](Get-CMDevice)



* [Remove-CMDevice](Remove-CMDevice)



* [Unblock-CMDevice](Unblock-CMDevice)





---


### Examples
#### Example 1: Block a device
```PowerShell
PS XYZ:\>Block-CMDevice -DeviceName "CMCEN-DIST02"
```
This command blocks the device named Test-DIST02.
#### Example 2: Get a device and block it
```PowerShell
PS XYZ:\> Get-CMDevice -Name "WIN10-86-33" | Block-CMDevice
```
This command gets the device object named WIN10-86-33 and uses the pipeline operator to pass the object to the Block-CMDevice cmdlet, which blocks the device object.


---


### Parameters
#### **DeviceId**

Specifies the ID of a device.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |named   |False        |ResourceId|



#### **DeviceName**

Specifies the name of a device.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



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



#### **InputObject**

Specifies a device object. To obtain a device object, use the Get-CMDevice (Get-CMDevice.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



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
Block-CMDevice -DeviceId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Block-CMDevice -DeviceName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Block-CMDevice [-InputObject] <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```

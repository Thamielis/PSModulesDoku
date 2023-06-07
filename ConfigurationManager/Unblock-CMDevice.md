Unblock-CMDevice
----------------




### Synopsis
Unblocks a client device.



---


### Description

The Unblock-CMDevice cmdlet unblocks one or more Configuration Manager client devices. You must unblock a device from the client's assigned site. You cannot unblock the device from sites higher in the hierarchy.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Approve-CMDevice](Approve-CMDevice)



* [Block-CMDevice](Block-CMDevice)



* [Get-CMDevice](Get-CMDevice)



* [Remove-CMDevice](Remove-CMDevice)





---


### Examples
#### Example 1: Unblock a device
```PowerShell
PS XYZ:\>Unbock-CMDevice -DeviceName "Test-DIST02"
```
This command unblocks the device named Test-DIST02.
#### Example 2: Get a device and unblock it
```PowerShell
PS XYZ:\> Get-CMDevice -Name "WIN10-86-33" | Unblock-CMDevice
```
This command gets the device object named WIN10-86-33 and uses the pipeline operator to pass the object to Unblock-CMDevice , which unblocks the device object.


---


### Parameters
#### **DeviceId**

Specifies the ID of a device.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |named   |False        |ResourceId|



#### **DeviceName**

Specifies the name of the device.






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
Unblock-CMDevice -DeviceId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Unblock-CMDevice -DeviceName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Unblock-CMDevice [-InputObject] <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```

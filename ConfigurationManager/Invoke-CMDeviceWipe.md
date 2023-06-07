Invoke-CMDeviceWipe
-------------------




### Synopsis
Performs a wipe of a modern device.



---


### Description

The Invoke-CMDeviceWipe cmdlet performs a complete wipe of all applications and data on a modern device. This cmdlet returns one or more devices to the factory configuration.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMDeviceOwnership](Set-CMDeviceOwnership)



* [Get-CMDevice](Get-CMDevice)





---


### Examples
#### Example 1: Return Restore a device to its factory configurationRestore
```PowerShell
PS XYZ:\>Invoke-CMDeviceWipe -DeviceName "WindowsPhone_17"
```
This command restores the named device to its factory configuration.


---


### Parameters
#### **Cancel**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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








|Type     |Required|Position|PipelineInput|Aliases                |
|---------|--------|--------|-------------|-----------------------|
|`[Int32]`|true    |named   |False        |ResourceId<br/>DeviceId|



#### **InputObject**

Specifies a CMDevice object. To obtain a CMDevice object, use the Get-CMDevice (Get-CMDevice.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases|
|-----------------|--------|--------|--------------|-------|
|`[IResultObject]`|true    |named   |True (ByValue)|Device |



#### **Name**








|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |named   |False        |DeviceName|



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
Invoke-CMDeviceWipe [-Cancel] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <Int32> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMDeviceWipe [-Cancel] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMDeviceWipe [-Cancel] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```

Remove-CMUserAffinityFromDevice
-------------------------------




### Synopsis
Removes a primary user from one or more devices in the Configuration Manager hierarchy.



---


### Description

The Remove-CMUserAffinityFromDevice cmdlet removes a primary user from the devices.



User device affinity is a method of associating a user with one or more specified devices in Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMUserAffinityToDevice](Add-CMUserAffinityToDevice)





---


### Examples
#### Example 1: Remove a primary user from a device
```PowerShell
PS XYZ:\> Remove-CMUserAffinityFromDevice -DeviceId "209846738" -UserId "206359374"
```
This command removes the association between the user that has the ID 206359374 and the device that has the ID 209846738.


---


### Parameters
#### **DeviceId**

Specifies an array of IDs of the devices.






|Type       |Required|Position|PipelineInput|Aliases   |
|-----------|--------|--------|-------------|----------|
|`[Int32[]]`|true    |named   |False        |ResourceId|



#### **DeviceName**

Specifies an array of names of the devices.






|Type        |Required|Position|PipelineInput|Aliases     |
|------------|--------|--------|-------------|------------|
|`[String[]]`|true    |named   |False        |ResourceName|



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



#### **UserId**

Specifies the ID of a user.






|Type       |Required|Position|PipelineInput|Aliases|
|-----------|--------|--------|-------------|-------|
|`[Int32[]]`|false   |named   |False        |UserIds|



#### **UserName**

Specifies the name of the primary user that you want to disassociate from the specified devices.






|Type        |Required|Position|PipelineInput|Aliases  |
|------------|--------|--------|-------------|---------|
|`[String[]]`|false   |named   |False        |UserNames|



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
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Remove-CMUserAffinityFromDevice -DeviceId <Int32[]> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-UserId <Int32[]>] [-UserName <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserAffinityFromDevice -DeviceName <String[]> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-UserId <Int32[]>] [-UserName <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

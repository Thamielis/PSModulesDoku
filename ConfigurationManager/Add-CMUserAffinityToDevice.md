Add-CMUserAffinityToDevice
--------------------------




### Synopsis
Adds a primary user to one or more devices in the Configuration Manager hierarchy.



---


### Description

The Add-CMUserAffinityToDevice cmdlet associates the devices with a primary user in Configuration Manager. You can specify the devices to associate with the primary user by their names or IDs. You can specify the primary user by their name or ID.



User device affinity is a method of associating a user with one or more specified devices. This allows you to deploy applications to a user without the requirement to know the name of all the user's devices. Instead of deploying the application to all the devices of a user, you deploy the application to the user and the application automatically installs on all devices that are associated with that user.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Remove-CMUserAffinityFromDevice](Remove-CMUserAffinityFromDevice)





---


### Examples
#### Example 1: Add a primary user to a device
```PowerShell
PS XYZ:\>Add-CMUserAffinityToDevice -DeviceName "CMCEN-DIST-02" -UserId "2063597981"
```
This command adds the primary user that has the ID 2063597981 to the device named CMCEN-DIST-02.


---


### Parameters
#### **DeviceId**

Specifies an array of IDs of the devices that you want to associate with the primary user.






|Type       |Required|Position|PipelineInput|Aliases   |
|-----------|--------|--------|-------------|----------|
|`[Int32[]]`|true    |named   |False        |ResourceId|



#### **DeviceName**

Specifies an array of names of the devices that you want to associate with the primary user.






|Type        |Required|Position|PipelineInput|Aliases     |
|------------|--------|--------|-------------|------------|
|`[String[]]`|true    |named   |False        |ResourceName|



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



#### **UserId**

Specifies the ID of a user.






|Type       |Required|Position|PipelineInput|Aliases|
|-----------|--------|--------|-------------|-------|
|`[Int32[]]`|false   |named   |False        |UserIds|



#### **UserName**

Specifies the name of the primary user.






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
Add-CMUserAffinityToDevice -DeviceId <Int32[]> [-DisableWildcardHandling] [-ForceWildcardHandling] [-UserId <Int32[]>] [-UserName <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMUserAffinityToDevice -DeviceName <String[]> [-DisableWildcardHandling] [-ForceWildcardHandling] [-UserId <Int32[]>] [-UserName <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

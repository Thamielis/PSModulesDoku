Sync-CMSoftwareUpdate
---------------------




### Synopsis
Synchronizes software updates.



---


### Description

The Sync-CMSoftwareUpdate cmdlet retrieves metadata for software updates. Software updates synchronization in Configuration Manager uses Microsoft Update to retrieve software updates metadata. You can use this cmdlet to retrieve metadata for all software updates or only recent changes to software updates.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareUpdate](Get-CMSoftwareUpdate)



* [Save-CMSoftwareUpdate](Save-CMSoftwareUpdate)



* [Set-CMSoftwareUpdate](Set-CMSoftwareUpdate)





---


### Examples
#### Example 1: Perform a full synchronization for all software updates
```PowerShell
PS XYZ:\> Sync-CMSoftwareUpdate -FullSync $True
```
This command performs a complete metadata synchronization for all software updates.


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



#### **FullSync**

Indicates whether to perform a complete synchronization of all updates or a delta synchronization.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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
Sync-CMSoftwareUpdate [-DisableWildcardHandling] [-ForceWildcardHandling] [-FullSync <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

Set-CMAssignedSite
------------------




### Synopsis
Assigns a client computer to a primary site.



---


### Description

The Set-CMAssignedSite cmdlet assigns a client computer to a primary site. When you install a client agent, the installation determines the primary site for the client. This cmdlet assigns a client to a different primary site.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDevice](Get-CMDevice)





---


### Examples
#### Example 1: Reassign a client to a site
```PowerShell
PS XYZ:\> Set-CMAssignedSite -DeviceId "2097152000" -SiteCode "CM7"
```
This command reassigns the client that has the device ID 2097152000 to the site that has the site code CM7.


---


### Parameters
#### **DeviceId**

Specifies an array of device IDs.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |named   |False        |ResourceId|



#### **DeviceName**

Specifies an array of device names.






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

Specifies a CMDevice object. To obtain a CMDevice object, use the Get-CMDevice (Get-CMDevice.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **SiteCode**

Specifies the site code of the new primary site to assign the client to.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
Set-CMAssignedSite -DeviceId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAssignedSite -DeviceName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAssignedSite [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

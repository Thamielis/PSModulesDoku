Remove-CMSoftwareUpdateGroup
----------------------------




### Synopsis
Removes Configuration Manager software update groups.



---


### Description

The Remove-CMSoftwareUpdateGroup cmdlet removes software update groups from Configuration Manager. You can specify each software update group that you are removing by using the group IDs or names. If you remove a software update group, you can use the Get-CMSoftwareUpdateGroup (Get-CMSoftwareUpdateGroup.md)cmdlet to return a software update group object and use that object to specify the group that you want to remove.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareUpdateGroup](Get-CMSoftwareUpdateGroup)



* [New-CMSoftwareUpdateGroup](New-CMSoftwareUpdateGroup)



* [Set-CMSoftwareUpdateGroup](Set-CMSoftwareUpdateGroup)





---


### Examples
#### Example 1: Remove a software update group by using an ID
```PowerShell
PS XYZ:\> Remove-CMSoftwareUpdateGroup -Id "ST10000B"
```
This command removes the software update group that has the ID ST10000B.
#### Example 2: Remove a software update group by using a name
```PowerShell
PS XYZ:\> Remove-CMSoftwareUpdateGroup -Name "SUGroupD01"
```
This command removes the software update group named SUGroupD01.
#### Example 3: Remove a software update group by using an object variable
```PowerShell
PS XYZ:\> $SubObj=Get-CMSoftwareUpdateGroup -Id "ST10000B"
PS XYZ:\> Remove-CMSoftwareUpdateGroup -SoftwareUpdateGroup $SubObj
```
The first command gets the software update group that has the ID ST10000B, and then stores it in the variable $SubObj.


The second command removes the software update group by using the $SubObj variable.


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



#### **Id**

Specifies an array of software update group IDs.






|Type        |Required|Position|PipelineInput|Aliases|
|------------|--------|--------|-------------|-------|
|`[String[]]`|true    |named   |False        |CIId   |



#### **InputObject**

Specifies the software update group object to remove. To obtain a software update group object, use Get-CMSoftwareUpdateGroup .






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies an array of software update group names.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |named   |False        |LocalizedDisplayName|



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
Remove-CMSoftwareUpdateGroup [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdateGroup [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdateGroup [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```

Set-CMSoftwareUpdateGroup
-------------------------




### Synopsis
Changes configuration settings for software update groups in Configuration Manager.



---


### Description

The Set-CMSoftwareUpdateGroup cmdlet changes the name or description of one or more Configuration Manager software update groups, or it adds or removes software update groups for one or more security scopes.



A software update group is a collection of one or more software updates. You can add software updates to a software update group and then deploy the group to clients. After you deploy a software update group, you can add new software updates to the group and Configuration Manager automatically deploys them.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareUpdateGroup](Get-CMSoftwareUpdateGroup)



* [New-CMSoftwareUpdateGroup](New-CMSoftwareUpdateGroup)



* [Remove-CMSoftwareUpdateGroup](Remove-CMSoftwareUpdateGroup)





---


### Examples
#### Example 1: Add a software update group to a security scope
```PowerShell
PS XYZ:\> Set-CMSoftwareUpdateGroup -SecurityScopeAction AddMembership -SecurityScopeName "ScopeNameD02" -Name "SUGroup01"
```
This command adds a software update group named SUGroup01 as a member of the security scope named ScopeNameD02.
#### Example 2: Remove a software update group from a security scope
```PowerShell
PS XYZ:\> Set-CMSoftwareUpdateGroup -SecurityScopeAction RemoveMembership -SecurityScopeName "ScopeNameD17" -Name "SUGroup01"
```
This command removes the software update group named SUGroup01 from membership in the security scope named ScopeNameD17.


---


### Parameters
#### **AddSoftwareUpdate**








|Type               |Required|Position|PipelineInput|Aliases           |
|-------------------|--------|--------|-------------|------------------|
|`[IResultObject[]]`|false   |named   |False        |AddSoftwareUpdates|



#### **ClearExpiredSoftwareUpdate**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ClearSoftwareUpdate**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ClearSupersededSoftwareUpdate**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Description**

Specifies a description for a software update group.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |LocalizedDescription|



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



#### **Id**

Specifies an array of IDs of software update groups.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |named   |False        |CIId<br/>CI_ID|



#### **InputObject**

Specifies a software group object. To obtain a software group object, use the Get-CMSoftwareUpdateGroup (Get-CMSoftwareUpdateGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies an array of names of software update groups.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |named   |False        |LocalizedDisplayName|



#### **NewName**

Specifies a name for a software update group. This name replaces the current name of the group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveSoftwareUpdate**








|Type               |Required|Position|PipelineInput|Aliases              |
|-------------------|--------|--------|-------------|---------------------|
|`[IResultObject[]]`|false   |named   |False        |RemoveSoftwareUpdates|



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
Set-CMSoftwareUpdateGroup [-AddSoftwareUpdate <IResultObject[]>] [-ClearExpiredSoftwareUpdate] [-ClearSoftwareUpdate] [-ClearSupersededSoftwareUpdate] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <Int32> [-NewName <String>] [-PassThru] [-RemoveSoftwareUpdate <IResultObject[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSoftwareUpdateGroup [-AddSoftwareUpdate <IResultObject[]>] [-ClearExpiredSoftwareUpdate] [-ClearSoftwareUpdate] [-ClearSupersededSoftwareUpdate] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-NewName <String>] [-PassThru] [-RemoveSoftwareUpdate <IResultObject[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSoftwareUpdateGroup [-AddSoftwareUpdate <IResultObject[]>] [-ClearExpiredSoftwareUpdate] [-ClearSoftwareUpdate] [-ClearSupersededSoftwareUpdate] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-NewName <String>] [-PassThru] [-RemoveSoftwareUpdate <IResultObject[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

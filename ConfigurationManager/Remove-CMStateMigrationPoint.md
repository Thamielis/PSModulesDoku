Remove-CMStateMigrationPoint
----------------------------




### Synopsis
Removes a state migration point from a Configuration Manager site.



---


### Description

The Remove-CMStateMigrationPoint cmdlet removes a state migration point from a Configuration Manager site. This site system role stores user information while you perform an operating system deployment. If you remove a state migration point, you also remove all associated stored user information.



Each state migration point can be a member of only one Configuration Manager site.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMStateMigrationPoint](Add-CMStateMigrationPoint)



* [Get-CMStateMigrationPoint](Get-CMStateMigrationPoint)





---


### Examples
#### Example 1: Remove a specified migration point
```PowerShell
PS XYZ:\> Remove-CMStateMigrationPoint -SiteCode "CM1" -SiteSystemServerName "SMP01.Western.Contoso.com"
```
This command removes a state migration point that belongs to the site that has the site code CM1. The command specifies the name of computer that hosts the site system role.
#### Example 2: Remove a migration point using a variable
```PowerShell
PS XYZ:\> $CMSMP = Get-CMStateMigrationPoint -SiteCode "CM1" -SiteSystemServerName "SMP01.TSQA.Contoso.com"
PS XYZ:\> Remove-CMStateMigrationPoint -InputObject $CMSMP
```
The first command uses the Get-CMStateMigrationPoint to get a state migration point that belongs to the specified site and has the specified host name, and then stores that object in the $CMSMP variable.


The second command removes the state migration point stored in the $CMSMP variable.


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

Specifies a state migration point object. To obtain a state migration point object, use the Get-CMStateMigrationPoint cmdlet.






|Type             |Required|Position|PipelineInput |Aliases            |
|-----------------|--------|--------|--------------|-------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|StateMigrationPoint|



#### **SiteCode**

Specifies a site code for a Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies the host name for a state migration point.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|true    |0       |False        |Name<br/>ServerName|



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
* 






---


### Notes




---


### Syntax
```PowerShell
Remove-CMStateMigrationPoint [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMStateMigrationPoint [-SiteSystemServerName] <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

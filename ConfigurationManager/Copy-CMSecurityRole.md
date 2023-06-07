Copy-CMSecurityRole
-------------------




### Synopsis
Create a custom security role.



---


### Description

Use this cmdlet to create a new security role by using an existing security role as a template. Configuration Manager provides several built-in security roles. If you require additional security roles, you can create a custom security role by creating a copy of an existing security role, and then modifying the copy.



For more information on security roles and permissions, see Fundamentals of role-based administration in Configuration Manager (/mem/configmgr/core/understand/fundamentals-of-role-based-administration).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Export-CMSecurityRole](Export-CMSecurityRole)



* [Get-CMSecurityRole](Get-CMSecurityRole)



* [Import-CMSecurityRole](Import-CMSecurityRole)



* [Remove-CMSecurityRole](Remove-CMSecurityRole)



* [Set-CMSecurityRole](Set-CMSecurityRole)



* [Add-CMSecurityRoleToAdministrativeUser](Add-CMSecurityRoleToAdministrativeUser)



* [Set-CMSecurityRolePermission](Set-CMSecurityRolePermission)



* [Automate role-based administration with Windows PowerShell](Automate role-based administration with Windows PowerShell)





---


### Examples
#### Example 1: Copy a security role by using an ID
```PowerShell
Copy-CMSecurityRole -Name "SecRole02" -SourceRoleId "SMS000CR"
```



---


### Parameters
#### **Description**

Specify an optional description for the security role.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[String]`|false   |named   |False        |RoleDescription|



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

Specify a security role object to copy. To get this object, use the Get-CMSecurityRole (Get-CMSecurityRole.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specify a name for the new security role.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |RoleName|



#### **SourceRoleId**

Specify the ID of the security role to copy. This value is the `RoleID` property, for example `SMS000AR` for the OS Deployment Manager role.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|true    |named   |False        |CopiedFromId|



#### **SourceRoleName**

Specify the name of the security role to copy.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
Copy-CMSecurityRole [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Copy-CMSecurityRole [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> -SourceRoleId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Copy-CMSecurityRole [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> -SourceRoleName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```

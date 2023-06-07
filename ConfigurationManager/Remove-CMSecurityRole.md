Remove-CMSecurityRole
---------------------




### Synopsis
Remove a custom security role.



---


### Description

Use this cmdlet to remove a custom security role from Configuration Manager. Specify the name or ID of a security role you want to remove or use the Get-CMSecurityRole (Get-CMSecurityRole.md)cmdlet to get one.



You can use the Remove-CMSecurityRole cmdlet to remove old, unneeded custom security roles. You can't remove built-in security roles. Every administrative user must have at least one security role. Before you remove a security role, make sure every user has a role in addition to the one you remove.



For more information on security roles and permissions, see Fundamentals of role-based administration in Configuration Manager (/mem/configmgr/core/understand/fundamentals-of-role-based-administration).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Copy-CMSecurityRole](Copy-CMSecurityRole)



* [Export-CMSecurityRole](Export-CMSecurityRole)



* [Get-CMSecurityRole](Get-CMSecurityRole)



* [Import-CMSecurityRole](Import-CMSecurityRole)



* [Set-CMSecurityRole](Set-CMSecurityRole)



* [Remove-CMSecurityRoleFromAdministrativeUser](Remove-CMSecurityRoleFromAdministrativeUser)



* [Automate role-based administration with Windows PowerShell](Automate role-based administration with Windows PowerShell)





---


### Examples
#### Example 1: Remove a security role by using a name
```PowerShell
Remove-CMSecurityRole -Name "MainSecurityRole" -Force
```

#### Example 2: Remove a security role by using a variable
```PowerShell
$role = Get-CMSecurityRole -Name "Custom*"
Remove-CMSecurityRole -InputObject $role[1]
```



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

Specify the ID of the security role to remove. This value is the `RoleID` property. Since this cmdlet only works with custom roles, this value should always start with the site code. (IDs for built-in roles start with `SMS`.)






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |RoleId |



#### **InputObject**

Specify a security role object to remove. To get this object, use the Get-CMSecurityRole (Get-CMSecurityRole.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specify the name of the security role to remove.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |RoleName|



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
Remove-CMSecurityRole [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSecurityRole [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSecurityRole [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```

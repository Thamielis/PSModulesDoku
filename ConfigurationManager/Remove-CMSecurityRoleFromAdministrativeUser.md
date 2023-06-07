Remove-CMSecurityRoleFromAdministrativeUser
-------------------------------------------




### Synopsis
Remove the association between a security role and an administrative user.



---


### Description

Use this cmdlet to remove the association between one or more security roles and an administrative user. After you remove the association of a security role with an administrative user, the administrative user can't view the objects in Configuration Manager that are associated with the security role. They also no longer have the permission to do the tasks that are related to those objects.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMSecurityRoleToAdministrativeUser](Add-CMSecurityRoleToAdministrativeUser)



* [Remove-CMSecurityScopeFromAdministrativeUser](Remove-CMSecurityScopeFromAdministrativeUser)



* [Get-CMAdministrativeUser](Get-CMAdministrativeUser)



* [Get-CMSecurityRole](Get-CMSecurityRole)



* [Automate role-based administration with Windows PowerShell](Automate role-based administration with Windows PowerShell)





---


### Examples
#### Example 1: Remove a security role from an administrative user
```PowerShell
Remove-CMSecurityRoleFromAdministrativeUser -AdministrativeUserName "Contoso\PattiFuller" -RoleName "Security Update Manager" -Force
```



---


### Parameters
#### **AdministrativeUser**

Specify an administrative user object to configure. To get this object, use the Get-CMAdministrativeUser (Get-CMAdministrativeUser.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **AdministrativeUserId**

Specify the ID of the administrative user to configure. This value is the `AdminID` property, which is an integer value. For example, `16777234`.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |named   |False        |



#### **AdministrativeUserName**

Specify the name of the administrative user to configure.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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



#### **Role**

Specify a security role object to remove. To get this object, use the Get-CMSecurityRole (Get-CMSecurityRole.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **RoleId**

Specify the ID of the security role to remove. This value is the `RoleID` property, for example `SMS000AR` for the OS Deployment Manager role.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **RoleName**

Specify the name of the security role to remove.






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
Remove-CMSecurityRoleFromAdministrativeUser -AdministrativeUser <IResultObject> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -RoleId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSecurityRoleFromAdministrativeUser -AdministrativeUser <IResultObject> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -RoleName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSecurityRoleFromAdministrativeUser -AdministrativeUser <IResultObject> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Role <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSecurityRoleFromAdministrativeUser -AdministrativeUserId <Int32> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -RoleId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSecurityRoleFromAdministrativeUser -AdministrativeUserId <Int32> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -RoleName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSecurityRoleFromAdministrativeUser -AdministrativeUserId <Int32> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Role <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSecurityRoleFromAdministrativeUser -AdministrativeUserName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -RoleName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSecurityRoleFromAdministrativeUser -AdministrativeUserName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -RoleId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSecurityRoleFromAdministrativeUser -AdministrativeUserName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Role <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```

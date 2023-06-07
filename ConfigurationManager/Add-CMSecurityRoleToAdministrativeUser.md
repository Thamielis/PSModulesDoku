Add-CMSecurityRoleToAdministrativeUser
--------------------------------------




### Synopsis
Add a security role to a user or group.



---


### Description

Use this cmdlet to add a security role to an administrative user or administrative group in Configuration Manager.



Permissions defined in a role represent object types and actions available for each object type. Configuration Manager provides some built-in security roles. You can also create custom security roles. For more information about security roles, see Fundamentals of role-based administration in Configuration Manager (/mem/configmgr/core/understand/fundamentals-of-role-based-administration).



You can specify an administrative user or group by name or by ID or you can use the use the Get-CMAdministrativeUser (Get-CMAdministrativeUser.md)cmdlet to get a user or group object. An administrative user in Configuration Manager defines a local or domain user or group. You can specify a role to add by name or by ID, or you can use the Get-CMSecurityRole (Get-CMSecurityRole.md)cmdlet to get a role.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Remove-CMSecurityRoleFromAdministrativeUser](Remove-CMSecurityRoleFromAdministrativeUser)



* [Add-CMSecurityScopeToAdministrativeUser](Add-CMSecurityScopeToAdministrativeUser)



* [Get-CMAdministrativeUser](Get-CMAdministrativeUser)



* [Get-CMSecurityRole](Get-CMSecurityRole)



* [Automate role-based administration with Windows PowerShell](Automate role-based administration with Windows PowerShell)





---


### Examples
#### Example 1: Add custom security role to a domain user group
```PowerShell
Add-CMSecurityRoleToAdministrativeUser -AdministrativeUserName "Contoso\Western Administrators " -RoleName "SecurityRole17"
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


You can use wildcard characters:


* `*`: Multiple characters


* `?`: Single character






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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

Specify a security role object to add. To get this object, use the Get-CMSecurityRole (Get-CMSecurityRole.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases|
|-----------------|--------|--------|--------------|-------|
|`[IResultObject]`|true    |named   |True (ByValue)|Role   |



#### **RoleId**

Specify the ID of the security role to add. This value is the `RoleID` property, for example `SMS000AR` for the OS Deployment Manager role.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **RoleName**

Specify the name of the security role to add.






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
Add-CMSecurityRoleToAdministrativeUser -AdministrativeUser <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] -RoleId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSecurityRoleToAdministrativeUser -AdministrativeUser <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] -RoleName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSecurityRoleToAdministrativeUser -AdministrativeUser <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSecurityRoleToAdministrativeUser -AdministrativeUserId <Int32> [-DisableWildcardHandling] [-ForceWildcardHandling] -RoleId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSecurityRoleToAdministrativeUser -AdministrativeUserId <Int32> [-DisableWildcardHandling] [-ForceWildcardHandling] -RoleName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSecurityRoleToAdministrativeUser -AdministrativeUserId <Int32> [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSecurityRoleToAdministrativeUser -AdministrativeUserName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -RoleName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSecurityRoleToAdministrativeUser -AdministrativeUserName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -RoleId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSecurityRoleToAdministrativeUser -AdministrativeUserName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```

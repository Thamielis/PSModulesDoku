Remove-CMSecurityScopeFromAdministrativeUser
--------------------------------------------




### Synopsis
Remove the association between a security scope and an administrative user.



---


### Description

Use this cmdlet to remove the association between a security scope and an administrative user. An administrative user in Configuration Manager defines a local or domain user or group.



After you remove the association between a security scope and an administrative user, the administrative user can't view the objects in Configuration Manager that are associated with the security scope, and no longer has the permission to perform the tasks that are related to those objects.



For more information about security scopes, see Fundamentals of role-based administration in Configuration Manager (/mem/configmgr/core/understand/fundamentals-of-role-based-administration).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMSecurityScopeToAdministrativeUser](Add-CMSecurityScopeToAdministrativeUser)



* [Remove-CMSecurityRoleFromAdministrativeUser](Remove-CMSecurityRoleFromAdministrativeUser)



* [Get-CMAdministrativeUser](Get-CMAdministrativeUser)



* [Get-CMSecurityScope](Get-CMSecurityScope)



* [New-CMSecurityScope](New-CMSecurityScope)



* [Remove-CMSecurityScope](Remove-CMSecurityScope)



* [Set-CMSecurityScope](Set-CMSecurityScope)



* [Automate role-based administration with Windows PowerShell](Automate role-based administration with Windows PowerShell)





---


### Examples
#### Example 1: Remove a security scope from an administrative user
```PowerShell
Remove-CMSecurityScopeFromAdministrativeUser -AdministrativeUserName "Contoso\PattiFuller" -SecurityScopeName "SecScope02" -Force
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



#### **SecurityScope**

Specify a security scope object to remove. To get this object, use the Get-CMSecurityScope (Get-CMSecurityScope.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **SecurityScopeId**

Specify the ID of the security scope to remove. This value is the `CategoryID` property, for example `SMS00UNA` for the Default scope.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SecurityScopeName**

Specify the name of the security scope to remove.






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
Remove-CMSecurityScopeFromAdministrativeUser -AdministrativeUser <IResultObject> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SecurityScopeId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSecurityScopeFromAdministrativeUser -AdministrativeUser <IResultObject> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SecurityScopeName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSecurityScopeFromAdministrativeUser -AdministrativeUser <IResultObject> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SecurityScope <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSecurityScopeFromAdministrativeUser -AdministrativeUserId <Int32> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SecurityScopeId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSecurityScopeFromAdministrativeUser -AdministrativeUserId <Int32> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SecurityScopeName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSecurityScopeFromAdministrativeUser -AdministrativeUserId <Int32> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SecurityScope <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSecurityScopeFromAdministrativeUser -AdministrativeUserName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SecurityScopeName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSecurityScopeFromAdministrativeUser -AdministrativeUserName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SecurityScopeId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSecurityScopeFromAdministrativeUser -AdministrativeUserName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SecurityScope <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```

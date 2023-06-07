Add-CMSecurityScopeToAdministrativeUser
---------------------------------------




### Synopsis
Add a security scope to a user or group.



---


### Description

Use this cmdlet to add a security scope to an administrative user or administrative group in Configuration Manager.



For more information about security scopes, see Fundamentals of role-based administration in Configuration Manager (/mem/configmgr/core/understand/fundamentals-of-role-based-administration).



You can specify an administrative user or group by name or by ID or you can use the use the Get-CMAdministrativeUser (Get-CMAdministrativeUser.md)cmdlet to obtain a user or group object. An administrative user in Configuration Manager defines a local or domain user or group. You can specify a security scope to add by name or by ID or you can use the Get-CMSecurityScope (Get-CMSecurityScope.md)cmdlet to obtain a security scope.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Remove-CMSecurityScopeFromAdministrativeUser](Remove-CMSecurityScopeFromAdministrativeUser)



* [Add-CMSecurityRoleToAdministrativeUser](Add-CMSecurityRoleToAdministrativeUser)



* [Get-CMAdministrativeUser](Get-CMAdministrativeUser)



* [Get-CMSecurityScope](Get-CMSecurityScope)



* [Automate role-based administration with Windows PowerShell](Automate role-based administration with Windows PowerShell)





---


### Examples
#### Example 1: Add a custom security scope to a domain user group
```PowerShell
Add-CMSecurityScopeToAdministrativeUser -AdministrativeUserName "Contoso\Western Administrators" -SecurityScopeName "Scope22"
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



#### **SecurityScope**

Specify a security scope object to add. To get this object, use the Get-CMSecurityScope (Get-CMSecurityScope.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **SecurityScopeId**

Specify the ID of the security scope to add. This value is the `CategoryID` property, for example `SMS00UNA` for the Default scope.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SecurityScopeName**

Specify the name of the security scope to add.






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
Add-CMSecurityScopeToAdministrativeUser -AdministrativeUser <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] -SecurityScopeId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSecurityScopeToAdministrativeUser -AdministrativeUser <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] -SecurityScopeName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSecurityScopeToAdministrativeUser -AdministrativeUser <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] -SecurityScope <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSecurityScopeToAdministrativeUser -AdministrativeUserId <Int32> [-DisableWildcardHandling] [-ForceWildcardHandling] -SecurityScopeId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSecurityScopeToAdministrativeUser -AdministrativeUserId <Int32> [-DisableWildcardHandling] [-ForceWildcardHandling] -SecurityScopeName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSecurityScopeToAdministrativeUser -AdministrativeUserId <Int32> [-DisableWildcardHandling] [-ForceWildcardHandling] -SecurityScope <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSecurityScopeToAdministrativeUser -AdministrativeUserName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -SecurityScopeName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSecurityScopeToAdministrativeUser -AdministrativeUserName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -SecurityScopeId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMSecurityScopeToAdministrativeUser -AdministrativeUserName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -SecurityScope <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```

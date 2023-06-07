Get-CMSecurityRole
------------------




### Synopsis
Get security roles.



---


### Description

Use this cmdlet to get one or more security roles from the Configuration Manager site. For more information on security roles and permissions, see Fundamentals of role-based administration in Configuration Manager (/mem/configmgr/core/understand/fundamentals-of-role-based-administration).



If your account doesn't have permissions to view security roles in the site, this cmdlet returns no results.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Copy-CMSecurityRole](Copy-CMSecurityRole)



* [Export-CMSecurityRole](Export-CMSecurityRole)



* [Import-CMSecurityRole](Import-CMSecurityRole)



* [Remove-CMSecurityRole](Remove-CMSecurityRole)



* [Set-CMSecurityRole](Set-CMSecurityRole)



* [Add-CMSecurityRoleToAdministrativeUser](Add-CMSecurityRoleToAdministrativeUser)



* [Get-CMSecurityRolePermission](Get-CMSecurityRolePermission)



* [Automate role-based administration with Windows PowerShell](Automate role-based administration with Windows PowerShell)





---


### Examples
#### Example 1: Get all security roles
```PowerShell
Get-CMSecurityRole | Select-Object RoleID, RoleName
```

#### Example 2: Get a security role by using a wildcard
```PowerShell
Get-CMSecurityRole -Name "App*"
```

#### Example 3: List all custom security roles
```PowerShell
Get-CMSecurityRole | Where-Object { $_.IsBuiltIn -eq $false }
```



---


### Parameters
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

Specify the ID of the security role to get. This value is the `RoleID` property, for example `SMS000AR` for the OS Deployment Manager role.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |RoleId |



#### **Name**

Specify the name of the security role to get.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|false   |named   |False        |RoleName|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_Role


* IResultObject#SMS_Role






---


### Notes
For more information on this return object and its properties, see SMS_Role server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_role-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMSecurityRole [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMSecurityRole [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```

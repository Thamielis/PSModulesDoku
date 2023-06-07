Get-CMSecurityRolePermission
----------------------------




### Synopsis
Get the permissions for the specified security role.



---


### Description

Use this cmdlet to get the permissions for the specified security role. For more information on security roles and permissions, see Fundamentals of role-based administration in Configuration Manager (/mem/configmgr/core/understand/fundamentals-of-role-based-administration).



If your account doesn't have permissions to view security roles in the site, this cmdlet returns no results.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMSecurityRolePermission](Set-CMSecurityRolePermission)



* [Get-CMSecurityRole](Get-CMSecurityRole)



* [Automate role-based administration with Windows PowerShell](Automate role-based administration with Windows PowerShell)





---


### Examples
#### Example 1: Get permissions for a specific role
```PowerShell
$roleName = "Application author"
$role = Get-CMSecurityRole -Name $roleName
$rolePermission = $role | Get-CMSecurityRolePermission
```

#### Example 2: View classes for a specific role
```PowerShell
$rolePermission | Select-Object ObjectTypeDisplayName | Sort-Object -Property ObjectTypeDisplayName
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

Specify the ID of the security role to get its permissions. This value is the `RoleID` property, for example `SMS000AR` for the OS Deployment Manager role.


To view all roles and IDs for the site, use the following command:




Get-CMSecurityRole | Select-Object RoleID, RoleName







|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |RoleId |



#### **InputObject**

Specify a security role object to get its permissions. To get this object, use the Get-CMSecurityRole (Get-CMSecurityRole.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases     |
|-----------------|--------|--------|--------------|------------|
|`[IResultObject]`|true    |named   |True (ByValue)|SecurityRole|



#### **Name**

Specify the name of the security role to get its permissions.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |RoleName|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#RoleOperation


* IResultObject#RoleOperation






---


### Notes
The return object is the `RoleOperation` class, which includes an instance of the `SMS_ARoleOperation` class. For more information, see SMS_ARoleOperation server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_aroleoperation-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMSecurityRolePermission [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMSecurityRolePermission [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMSecurityRolePermission [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [<CommonParameters>]
```

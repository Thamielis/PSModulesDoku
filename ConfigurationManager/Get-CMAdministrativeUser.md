Get-CMAdministrativeUser
------------------------




### Synopsis
Get an administrative user.



---


### Description

Use this cmdlet to get one or more administrative users in Configuration Manager. An administrative user has a defined set of permissions and may be a member of one or more scopes or roles. An administrative user in Configuration Manager defines a local or domain user or group. For more information about security roles, see Fundamentals of role-based administration in Configuration Manager (/mem/configmgr/core/understand/fundamentals-of-role-based-administration).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMAdministrativeUser](New-CMAdministrativeUser)



* [Remove-CMAdministrativeUser](Remove-CMAdministrativeUser)



* [New-CMAdministrativeUserPermission](New-CMAdministrativeUserPermission)



* [Automate role-based administration with Windows PowerShell](Automate role-based administration with Windows PowerShell)





---


### Examples
#### Example 1: Get all administrative users
```PowerShell
Get-CMAdministrativeUser | Select-Object LogonName, RoleNames, CategoryNames, CollectionNames
```

#### Example 2: Get an administrative user by name
```PowerShell
Get-CMAdministrativeUser -Name "Contoso\jqpublic"
```

#### Example 3: Get all users with specific scope
```PowerShell
Get-CMAdministrativeUser | Where-Object { $_.CategoryNames -contains "Default" } | Select-Object LogonName
```

#### Example 4: Get all users with specific role
```PowerShell
Get-CMAdministrativeUser -RoleName "Full Administrator" | Select-Object LogonName
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

Specify the ID of the administrative user to get. This value is the `AdminID` property. It's an integer value, for example `16777234`.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |AdminId|



#### **Name**

Specify the name of the administrative user to get. For example, `domain\username` or `domain\groupname`


You can use wildcard characters:


* `*`: Multiple characters


* `?`: Single character






|Type      |Required|Position|PipelineInput|Aliases                               |
|----------|--------|--------|-------------|--------------------------------------|
|`[String]`|false   |named   |False        |DisplayName<br/>LogonName<br/>UserName|



#### **RoleName**

Specify an array of security role names. This name can be for a built-in or custom role. To see the list of built-in security roles, see Security roles (/mem/configmgr/core/understand/fundamentals-of-role-based-administration#security-roles).






|Type        |Required|Position|PipelineInput|Aliases  |
|------------|--------|--------|-------------|---------|
|`[String[]]`|false   |named   |False        |RoleNames|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_Admin


* IResultObject#SMS_Admin






---


### Notes
For more information on this return object and its properties, see SMS_Admin server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_admin-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMAdministrativeUser [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-RoleName <String[]>] [<CommonParameters>]
```
```PowerShell
Get-CMAdministrativeUser [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [-RoleName <String[]>] [<CommonParameters>]
```

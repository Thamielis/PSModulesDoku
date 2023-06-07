New-CMAdministrativeUser
------------------------




### Synopsis
Create an administrative user.



---


### Description

Use this cmdlet to create an administrative user for Configuration Manager. An administrative user in Configuration Manager defines a local or domain user or group. When you create the administrative user in Configuration Manager, you can give it access to security roles, security scopes, and collections. For more information about security roles, see Fundamentals of role-based administration in Configuration Manager (/mem/configmgr/core/understand/fundamentals-of-role-based-administration).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMAdministrativeUser](Get-CMAdministrativeUser)



* [Remove-CMAdministrativeUser](Remove-CMAdministrativeUser)



* [New-CMAdministrativeUserPermission](New-CMAdministrativeUserPermission)



* [Automate role-based administration with Windows PowerShell](Automate role-based administration with Windows PowerShell)





---


### Examples
#### Example 1: Add an administrative user
```PowerShell
$name = "Contoso\AdminUser1"
$roles = "Application Administrator","Software Update Manager"
$scopes = "scope1","scope2"
$colls = "userCollection1","deviceCollection1"

New-CMAdministrativeUser -Name $name -RoleName $roles -SecurityScopeName $scopes -CollectionName $colls
```

#### Example 2: Add a domain group
```PowerShell
New-CMAdministrativeUser -Name "Contoso\Security Analysts" -RoleName "Read-only Analyst"
```



---


### Parameters
#### **CollectionName**

Specify an array of collection names. The cmdlet assigns the new administrative user to each of these collections.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



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



#### **Name**

Specify the name of the administrative user to add. Use the format `domain\name`, where `name` is either the user or the group.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |named   |False        |LogonName|



#### **Permission**

Specify an array of permissions objects to assign to this new user. To get these objects, use the New-CMAdministrativeUserPermission (New-CMAdministrativeUserPermission.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases    |
|-------------------|--------|--------|-------------|-----------|
|`[IResultObject[]]`|true    |named   |False        |Permissions|



#### **RoleName**

Specify an array of security role names. This name can be for a built-in or custom role. To see the list of built-in security roles, see Security roles (/mem/configmgr/core/understand/fundamentals-of-role-based-administration#security-roles).






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|true    |named   |False        |



#### **SecurityScopeName**

Specify an array of security scope names. A security scope name can be "Default" or the name of a custom security scope. The cmdlet assigns the security scopes that you specify to the administrative user.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



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
None





---


### Outputs
* IResultObject#SMS_Admin






---


### Notes
For more information on this return object and its properties, see SMS_Admin server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_admin-server-wmi-class).



---


### Syntax
```PowerShell
New-CMAdministrativeUser [-CollectionName <String[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> -RoleName <String[]> [-SecurityScopeName <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMAdministrativeUser [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> -Permission <IResultObject[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```

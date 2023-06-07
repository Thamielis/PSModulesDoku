New-CMSecurityScope
-------------------




### Synopsis
Create a security scope.



---


### Description

Use this cmdlet to create a security scope. Security scopes provide administrative users with access to securable objects.



For more information on security scopes, see Fundamentals of role-based administration in Configuration Manager (/mem/configmgr/core/understand/fundamentals-of-role-based-administration).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSecurityScope](Get-CMSecurityScope)



* [Set-CMSecurityScope](Set-CMSecurityScope)



* [Remove-CMSecurityScope](Remove-CMSecurityScope)



* [Add-CMSecurityScopeToAdministrativeUser](Add-CMSecurityScopeToAdministrativeUser)



* [Add-CMObjectSecurityScope](Add-CMObjectSecurityScope)



* [Automate role-based administration with Windows PowerShell](Automate role-based administration with Windows PowerShell)





---


### Examples
#### Example 1: Create a security scope
```PowerShell
New-CMSecurityScope -Name "Scope1" -Description "Custom scope"
```



---


### Parameters
#### **Description**

Specify an optional description for the security scope.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|false   |named   |False        |CategoryDescription|



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

Specify a name for the security scope to create.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|true    |named   |False        |CategoryName|



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
* IResultObject#SMS_SecuredCategory






---


### Notes
For more information on this return object and its properties, see SMS_SecuredCategory server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_securedcategory-server-wmi-class).



---


### Syntax
```PowerShell
New-CMSecurityScope [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```

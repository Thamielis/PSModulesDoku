Get-CMSecurityScope
-------------------




### Synopsis
Get a security scope.



---


### Description

Use this cmdlet to get one or more security scopes in Configuration Manager. You can get a security scope by its name or ID. If you don't provide any parameters, all security scopes are returned.



For more information on security scopes, see Fundamentals of role-based administration in Configuration Manager (/mem/configmgr/core/understand/fundamentals-of-role-based-administration).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMSecurityScope](New-CMSecurityScope)



* [Remove-CMSecurityScope](Remove-CMSecurityScope)



* [Set-CMSecurityScope](Set-CMSecurityScope)



* [Get-CMObjectSecurityScope](Get-CMObjectSecurityScope)



* [Remove-CMSecurityScopeFromAdministrativeUser](Remove-CMSecurityScopeFromAdministrativeUser)



* [New-CMAdministrativeUserPermission](New-CMAdministrativeUserPermission)



* [Automate role-based administration with Windows PowerShell](Automate role-based administration with Windows PowerShell)





---


### Examples
#### Example 1: Get a security scope by name
```PowerShell
Get-CMSecurityScope -Name "Scope1"
```

#### Example 2: Get a security scope by using a wildcard
```PowerShell
Get-CMSecurityScope -Name "Contoso*"
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

Specify the ID of a security scope to get. This value is the `CategoryID` property, for example `SMS00UNA` for the Default scope.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |named   |False        |CategoryId|



#### **Name**

Specify the name of a security scope to get.


You can use wildcard characters:


* `*`: Multiple characters


* `?`: Single character






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|false   |named   |False        |CategoryName|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_SecuredCategory


* IResultObject#SMS_SecuredCategory






---


### Notes
For more information on this return object and its properties, see SMS_SecuredCategory server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_securedcategory-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMSecurityScope [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMSecurityScope [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```

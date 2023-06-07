Add-CMObjectSecurityScope
-------------------------




### Synopsis
Add a security scope to an object.



---


### Description

Use this cmdlet to add a security scope to a Configuration Manager object.



For more information on security scopes, see Fundamentals of role-based administration in Configuration Manager (/mem/configmgr/core/understand/fundamentals-of-role-based-administration).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMObjectSecurityScope](Get-CMObjectSecurityScope)



* [Remove-CMObjectSecurityScope](Remove-CMObjectSecurityScope)



* [Get-CMSecurityScope](Get-CMSecurityScope)



* [Add-CMSecurityScopeToAdministrativeUser](Add-CMSecurityScopeToAdministrativeUser)



* [Automate role-based administration with Windows PowerShell](Automate role-based administration with Windows PowerShell)





---


### Examples
#### Example 1: Add a security scope to application objects
```PowerShell
$Scope = New-CMSecurityScope -Name "Scope1" -Description "Security scope 1"
Get-CMApplication -Name "Central*" | Add-CMObjectSecurityScope -Scope $Scope
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

Specify the ID of a security scope to add to a Configuration Manager object. This value is the `CategoryID` property, for example `SMS00UNA` for the Default scope.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[String]`|true    |named   |False        |SecurityScopeId|



#### **InputObject**

Specify an array of Configuration Manager objects to add the security scope. To get this object, use the Get cmdlet for the object type. For example, Get-CMApplication for app objects.






|Type               |Required|Position|PipelineInput |
|-------------------|--------|--------|--------------|
|`[IResultObject[]]`|true    |named   |True (ByValue)|



#### **Name**

Specify the name of a security scope to add to a Configuration Manager object.






|Type      |Required|Position|PipelineInput|Aliases          |
|----------|--------|--------|-------------|-----------------|
|`[String]`|true    |0       |False        |SecurityScopeName|



#### **Scope**

Specify an array of security scope objects to add. To get this object use the Get-CMSecurityScope (Get-CMSecurityScope.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases                                                                              |
|-------------------|--------|--------|-------------|-------------------------------------------------------------------------------------|
|`[IResultObject[]]`|true    |0       |False        |SecurityScope<br/>SecuredCategory<br/>Scopes<br/>SecurityScopes<br/>SecuredCategories|



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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject[]





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Add-CMObjectSecurityScope [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> -InputObject <IResultObject[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMObjectSecurityScope [-Name] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMObjectSecurityScope [-Scope] <IResultObject[]> [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```

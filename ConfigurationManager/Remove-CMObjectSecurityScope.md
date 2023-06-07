Remove-CMObjectSecurityScope
----------------------------




### Synopsis
Remove a security scope from a Configuration Manager object.



---


### Description

Use this cmdlet to remove one or more security scopes from a Configuration Manager object.



For more information on security scopes, see Fundamentals of role-based administration in Configuration Manager (/mem/configmgr/core/understand/fundamentals-of-role-based-administration).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMObjectSecurityScope](Add-CMObjectSecurityScope)



* [Get-CMObjectSecurityScope](Get-CMObjectSecurityScope)



* [Get-CMSecurityScope](Get-CMSecurityScope)



* [Remove-CMSecurityScope](Remove-CMSecurityScope)



* [Remove-CMSecurityScopeFromAdministrativeUser](Remove-CMSecurityScopeFromAdministrativeUser)



* [Automate role-based administration with Windows PowerShell](Automate role-based administration with Windows PowerShell)





---


### Examples
#### Example 1: Remove a security scope from an application
```PowerShell
$Scope = Get-CMSecurityScope -Name "Scope1"
$apps = Get-CMApplication -Name "Central*"
$app | Remove-CMObjectSecurityScope -Scope $Scope -Force
```

#### Example 3: Add a new security scope then remove all others from application object
```PowerShell
$ScopeName = "Team ABC"
$TeamABCScope = Get-CMSecurityScope | Where-Object {$_.CategoryName -eq $ScopeName}

$app = Get-CMApplication -Name "Edge Enterprise Stable"

Add-CMObjectSecurityScope -InputObject $app -Scope $TeamABCScope

$scopes = Get-CMObjectSecurityScope -InputObject $app | Where-Object {$_.CategoryName -ne $ScopeName}
foreach ( $ExtraScope in $scopes )
  {
  Remove-CMObjectSecurityScope -InputObject $app -Scope $ExtraScope -Force
  }
```



---


### Parameters
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



#### **Id**

Specify the ID of a security scope that's associated with a Configuration Manager object. This value is the `CategoryID` property, for example `SMS00UNA` for the Default scope.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[String]`|true    |named   |False        |SecurityScopeId|



#### **InputObject**

Specify an array of Configuration Manager objects that are associated with a security scope. To get this object, use the Get cmdlet for the object type. For example, Get-CMApplication for app objects.






|Type               |Required|Position|PipelineInput |
|-------------------|--------|--------|--------------|
|`[IResultObject[]]`|true    |named   |True (ByValue)|



#### **Name**

Specify the name of a security scope that's associated with a Configuration Manager object.






|Type      |Required|Position|PipelineInput|Aliases          |
|----------|--------|--------|-------------|-----------------|
|`[String]`|true    |0       |False        |SecurityScopeName|



#### **Scope**

Specify an array of security scope objects to remove. To get this object use the Get-CMSecurityScope (Get-CMSecurityScope.md)cmdlet.






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
Remove-CMObjectSecurityScope [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <String> -InputObject <IResultObject[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMObjectSecurityScope [-Name] <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMObjectSecurityScope [-Scope] <IResultObject[]> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```

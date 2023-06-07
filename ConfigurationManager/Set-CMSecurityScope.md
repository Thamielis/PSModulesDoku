Set-CMSecurityScope
-------------------




### Synopsis
Configure a security scope.



---


### Description

Use this cmdlet to change the configuration settings of a security scope. You can only configure custom scopes.



For more information on security scopes, see Fundamentals of role-based administration in Configuration Manager (/mem/configmgr/core/understand/fundamentals-of-role-based-administration).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSecurityScope](Get-CMSecurityScope)



* [New-CMSecurityScope](New-CMSecurityScope)



* [Remove-CMSecurityScope](Remove-CMSecurityScope)



* [Automate role-based administration with Windows PowerShell](Automate role-based administration with Windows PowerShell)





---


### Examples
#### Example 1: Rename a security scope
```PowerShell
$Scope = Get-CMSecurityScope -Name "Scope1"

Set-CMSecurityScope -InputObject $Scope -NewName "Admin scope"
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



#### **Id**

Specify the ID of a security scope to configure. This value is the `CategoryID` property. Since this cmdlet only works with custom scopes, this value should always start with the site code. (IDs for built-in scopes start with `SMS`.)






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |named   |False        |CategoryId|



#### **InputObject**

Specify a security scope object to configure. To get this object, use the Get-CMSecurityScope (Get-CMSecurityScope.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specify the name of a security scope to configure.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|true    |named   |False        |CategoryName|



#### **NewName**

Specify a new name for the security scope.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
Set-CMSecurityScope [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-NewName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSecurityScope [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-NewName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSecurityScope [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-NewName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

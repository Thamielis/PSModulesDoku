Set-CMObjectSecurityScope
-------------------------




### Synopsis
Add or remove security scopes for Configuration Manager objects. This cmdlet is deprecated.



---


### Description

The Set-CMObjectSecurityScope cmdlet adds and removes security scopes for Configuration Manager objects.



This cmdlet has been deprecated and may be removed in a future release. Use Add-CMObjectSecurityScope (Add-CMObjectSecurityScope.md) and [Remove-CMObjectSecurityScope](Remove-CMObjectSecurityScope.md)to add and remove security scopes from Configuration Manager objects.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMObjectSecurityScope](Add-CMObjectSecurityScope)



* [Get-CMObjectSecurityScope](Get-CMObjectSecurityScope)



* [Remove-CMObjectSecurityScope](Remove-CMObjectSecurityScope)





---


### Examples
#### Example 1: Add a security scope to application objects by using the pipeline
```PowerShell
PS XYZ:\> Get-CMApplication -Name "Application*" | Set-CMObjectSecurityScope -Action AddMembership -Name "Scope1"
```
This command gets all application objects that have a name beginning with Application and uses the pipeline operator to pass the objects to Set-CMObjectSecurityScope . Set-CMObjectSecurityScope adds the security scope named Scope1 to each application object.
#### Example 2: Add a security scope to application objects
```PowerShell
PS XYZ:\> Set-CMObjectSecurityScope -InputObject (Get-CMApplication -Name "Application*") -Action AddMembership -Name "Scope1"
```
This command gets all application objects that have a name beginning with Application and adds the security scope named Scope1 to each application object.


---


### Parameters
#### **Action**

Specifies the action that this cmdlet takes on the security scope. Valid values are:


* AddMembership


* RemoveMembership



Valid Values:

* AddMembership
* RemoveMembership






|Type                       |Required|Position|PipelineInput|Aliases            |
|---------------------------|--------|--------|-------------|-------------------|
|`[SecurityScopeActionType]`|true    |named   |False        |SecurityScopeAction|



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



#### **InputObject**

Specifies an array of Configuration Manager objects associated with a security scope.






|Type               |Required|Position|PipelineInput |
|-------------------|--------|--------|--------------|
|`[IResultObject[]]`|true    |named   |True (ByValue)|



#### **Name**

Specifies a name of a security scope.






|Type      |Required|Position|PipelineInput|Aliases          |
|----------|--------|--------|-------------|-----------------|
|`[String]`|true    |named   |False        |SecurityScopeName|



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
Set-CMObjectSecurityScope -Action {AddMembership | RemoveMembership} [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject[]> -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```

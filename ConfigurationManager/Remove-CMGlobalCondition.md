Remove-CMGlobalCondition
------------------------




### Synopsis
Removes a Configuration Manager global condition object.



---


### Description

The Remove-CMGlobalCondition cmdlet removes a global condition object.



Configuration Manager uses global conditions to represent business or technical conditions. Global conditions specify how to provide and deploy applications to client devices.



You can specify a global condition by name or ID or use the Get-CMGlobalCondition cmdlet to obtain a global condition object. You cannot remove read-only global conditions.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMGlobalCondition](New-CMGlobalCondition)



* [Get-CMGlobalCondition](Get-CMGlobalCondition)



* [Set-CMGlobalCondition](Set-CMGlobalCondition)





---


### Examples
#### Example 1: Remove a global condition
```PowerShell
PS XYZ:\> Remove-CMGlobalCondition -Name "GC56" -Force
```
This command removes a global condition named GC56. Because the command uses the Force parameter, the system does not prompt you before it removes the condition.
#### Example 2: Remove a global condition using a variable
```PowerShell
PS XYZ:\> $CMGC = Get-CMGlobalCondition -Name "GC57"
PS XYZ:\> Remove-CMGlobalCondition -InputObject $CMGC
Remove
Are you sure you wish to remove GlobalCondition:
LocalizedDisplayName=" GC57"?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```
The first command uses the Get-CMGlobalCondition cmdlet to get the global condition named GC57 and stores it in the $CMGC variable.


The second command removes the global condition stored in that variable. This command does not use the Force parameter, so it prompts you for confirmation before it removes the global condition.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Performs the action without a confirmation message.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies an array of identifiers of global conditions. This value corresponds to the CI_ID property of a global condition object.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |CIId   |



#### **InputObject**

Specifies a global condition object. To obtain a global condition object, use the Get-CMGlobalCondition cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies an array of names for global conditions. This value corresponds to the LocalizedDisplayName property of a global condition object.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |named   |False        |LocalizedDisplayName|



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
Remove-CMGlobalCondition [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMGlobalCondition [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMGlobalCondition [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```

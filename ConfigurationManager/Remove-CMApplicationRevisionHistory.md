Remove-CMApplicationRevisionHistory
-----------------------------------




### Synopsis
Removes a revision history from a Configuration Manager application.



---


### Description

The Remove-CMApplicationRevisionHistory cmdlet removes a revision history from a Configuration Manager application. The revision history contains a list of revisions to an application or a development type that the application contains.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMApplicationRevisionHistory](Get-CMApplicationRevisionHistory)



* [Restore-CMApplicationRevisionHistory](Restore-CMApplicationRevisionHistory)





---


### Examples
#### Example 1: Remove a revision history
```PowerShell
PS XYZ:\> Remove-CMApplicationRevisionHistory -Name "MSXML 6.0 Parser"
```
This command removes the revision history named MSXML 6.0 Parser.


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

Specifies an array of IDs that identify the application revision histories that you delete.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[UInt32]`|true    |named   |False        |CIId   |



#### **InputObject**

Specifies an application object. To get an application object, use the Get-CMApplication (Get-CMApplication.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases            |
|-----------------|--------|--------|--------------|-------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|ApplicationRevision|



#### **Name**

Specifies an array of names for the application revision histories that you delete.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |named   |False        |LocalizedDisplayName|



#### **Revision**

Specifies the version number of the revision that you delete from the history.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[UInt32]`|true    |named   |False        |



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
Remove-CMApplicationRevisionHistory [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <UInt32> -Revision <UInt32> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMApplicationRevisionHistory [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMApplicationRevisionHistory [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> -Revision <UInt32> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMApplicationRevisionHistory [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> -Revision <UInt32> [-Confirm] [-WhatIf] [<CommonParameters>]
```

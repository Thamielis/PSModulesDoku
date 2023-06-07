Remove-CMTaskSequenceGroup
--------------------------




### Synopsis
Removes a Configuration Manager task sequence group.



---


### Description

The Remove-CMTaskSequenceGroup cmdlet removes task sequence group(s) from a task sequence.  The cmdlet supports pipeline from a task sequence object, and could be filtered by the name of the group.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMTaskSequenceGroup](New-CMTaskSequenceGroup)



* [Get-CMTaskSequenceGroup](Get-CMTaskSequenceGroup)



* [Set-CMTaskSequenceGroup](Set-CMTaskSequenceGroup)





---


### Examples
#### Example 1
```PowerShell
PS XYZ:\> $ReferencedTaskSequence | Remove-CMTaskSequenceGroup -StepName $gpName -Force
```
The command removes the task sequence groups from a task sequence with the name specified.


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



#### **InputObject**

Specifies a task sequence object.






|Type             |Required|Position|PipelineInput |Aliases     |
|-----------------|--------|--------|--------------|------------|
|`[IResultObject]`|true    |named   |True (ByValue)|TaskSequence|



#### **StepName**

Specifies the name of a step.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **TaskSequenceId**

Specifies the ID of a task sequence.






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[String]`|true    |named   |False        |Id<br/>TaskSequencePackageId|



#### **TaskSequenceName**

Specifies the name of a task sequence.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
Remove-CMTaskSequenceGroup [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMTaskSequenceGroup [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-StepName <String>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMTaskSequenceGroup [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-StepName <String>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```

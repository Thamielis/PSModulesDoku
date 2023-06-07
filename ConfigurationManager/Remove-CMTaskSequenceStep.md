Remove-CMTaskSequenceStep
-------------------------




### Synopsis
Removes a Configuration Manager task sequence step.



---


### Description

The Remove-CMTaskSequenceStep cmdlet removes task sequence group(s) or step(s) from a specific task sequence. The cmdlet supports pipeline from a task sequence object, and could be filtered by the name of the group/step.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMTaskSequenceStep](Add-CMTaskSequenceStep)



* [Get-CMTaskSequenceStep](Get-CMTaskSequenceStep)



* [Get-CMTaskSequenceStepCondition](Get-CMTaskSequenceStepCondition)



* [Get-CMTaskSequence](Get-CMTaskSequence)





---


### Examples
#### Example 1
```PowerShell
PS XYZ:\> $ReferencedTaskSequence | Remove-CMTaskSequenceStep -StepName $st1.Name -Force
```
The command removes a task sequence step with a specific name by force.


---


### Parameters
#### **ActionClassName**

Specifies an action class name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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

Specifies the Name of a task sequence.






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
Remove-CMTaskSequenceStep [-ActionClassName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMTaskSequenceStep [-ActionClassName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-StepName <String>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMTaskSequenceStep [-ActionClassName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-StepName <String>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```

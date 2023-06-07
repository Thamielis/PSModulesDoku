Add-CMTaskSequenceStep
----------------------




### Synopsis
Add a step or group to a task sequence.



---


### Description

Use this cmdlet to add a group or step to an existing task sequence. For more information about task sequences steps, see Task sequence steps (/mem/configmgr/osd/understand/task-sequence-steps).



When programmatically adding steps to a task sequence, it's important to understand the index order of steps. To help visualize the index, this article uses the following example task sequence:



- step1



- step2



- step3



- step4



- group5



- step5.1   - step5.2   - step5.3   - group5.4     - step5.4.1   - step5.5 - step6



When you use the task sequence editor (/mem/configmgr/osd/understand/task-sequence-editor#bkmk_edit)to add a step, the new step is added after the currently selected step. This cmdlet works similarly, it adds the step after the specified index. You use the InsertStepStartIndex parameter to specify the step index.



This cmdlet can only add steps to the main level of the task sequence, not in groups. To add steps in groups, use Set-CMTaskSequenceGroup (Set-CMTaskSequenceGroup.md). For example, with the sample task sequence, if you use Add-CMTaskSequenceStep with the InsertStepStartIndex parameter value `5`, the cmdlet adds the new step after group5 and before step6 .



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTaskSequenceStep](Get-CMTaskSequenceStep)



* [Get-CMTaskSequenceStepCondition](Get-CMTaskSequenceStepCondition)



* [Remove-CMTaskSequenceStep](Remove-CMTaskSequenceStep)



* [Get-CMTaskSequenceGroup](Get-CMTaskSequenceGroup)



* [New-CMTaskSequenceGroup](New-CMTaskSequenceGroup)



* [Set-CMTaskSequenceGroup](Set-CMTaskSequenceGroup)



* [About task sequence steps](About task sequence steps)





---


### Examples
#### Example 1: Create a custom task sequence that runs two PowerShell scripts
```PowerShell
$step1 = New-CMTaskSequenceStepRunPowerShellScript -Name "Run script 1" -PackageID $PackageId -ScriptName "script1.ps1" -ExecutionPolicy Bypass
$step2 = New-CMTaskSequenceStepRunPowerShellScript -Name "Run script 2" -PackageID $PackageId -ScriptName "script2.ps1" -ExecutionPolicy Bypass
$ts = New-CMTaskSequence -Name "Run scripts" -CustomTaskSequence
$ts | Add-CMTaskSequenceStep -Step ($step1, $step2)
```
The resulting task sequence looks like the following list:


- Run script 1


- Run script 2




The steps are ordered this way because of how they're ordered in the Step parameter.
#### Example 2: Create a custom task sequence that runs two PowerShell scripts with a different order
```PowerShell
$step1 = New-CMTaskSequenceStepRunPowerShellScript -Name "Run script 1" -PackageID $PackageId -ScriptName "script1.ps1" -ExecutionPolicy Bypass
$step2 = New-CMTaskSequenceStepRunPowerShellScript -Name "Run script 2" -PackageID $PackageId -ScriptName "script2.ps1" -ExecutionPolicy Bypass
$ts = New-CMTaskSequence -Name "Run scripts" -CustomTaskSequence
$ts | Add-CMTaskSequenceStep -Step $step1
$ts | Add-CMTaskSequenceStep -Step $step2
```
The resulting task sequence looks like the following list:


- Run script 2


- Run script 1




Because of how each instance of Add-CMTaskSequenceStep is ordered, and neither uses the InsertStepStartIndex parameter, by default they use index `0`. So the cmdlet adds the second step before the first step.
#### Example 3: Add a step at a specific index
```PowerShell
$step = New-CMTSStepSetVariable -name "newStep" -TaskSequenceVariable "testVar" -TaskSequenceVariableValue "testValue"
Add-CMTaskSequenceStep -TaskSequenceName "ts1" -Step $step -InsertStepStartIndex 2
```

#### Example 4: Copy a task sequence and add a new step
```PowerShell
$ts = Copy-CMTaskSequence -Name "Deploy Windows 10 (v1)"
$ts | Set-CMTaskSequence -NewName "Deploy Windows 10 (v2)"

$ts | Add-CMObjectSecurityScope -Name "Contoso main" | Out-Null
$ts | Remove-CMObjectSecurityScope -Name "Default" -Force |Out-Null

$pkgId = (Get-CMPackage -Name "Widget tool" -Fast).PackageID
$condition = ($ts | Get-CMTaskSequenceStep -StepName "Restart in Windows PE").Condition.Operands

$step = New-CMTaskSequenceStepRunCommandLine -CommandLine "widget.exe /q" -PackageId $pkgId -Name "Install Widget in Windows PE" -Condition $condition
$ts | Add-CMTaskSequenceStep -Step $step -InsertStepStartIndex 11
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



#### **InputObject**

Specify a task sequence object to which the cmdlet adds the step. To get this object, use the Get-CMTaskSequence (Get-CMTaskSequence.md), [Copy-CMTaskSequence](Copy-CMTaskSequence.md), or [New-CMTaskSequence](New-CMTaskSequence.md)cmdlets.






|Type             |Required|Position|PipelineInput |Aliases     |
|-----------------|--------|--------|--------------|------------|
|`[IResultObject]`|true    |named   |True (ByValue)|TaskSequence|



#### **InsertStepStartIndex**

Specify an integer value for the task sequence index. The cmdlet adds the new step after this specified index. For example, using the example task sequence in the Description (#description), if you specify a value of `4`, the cmdlet adds the new step after step4 .


If you specify a value of `0`, the cmdlet adds the new step at the top of the task sequence. This behavior is the default if you don't specify this parameter. For example, the cmdlet adds the new step before step1 .


There's no maximum value. If you specify a value that's greater than the last step's index, the cmdlet adds the new step at the end of the task sequence. For example, if you specify a value of `10`, the cmdlet adds the new step after step6 .






|Type      |Required|Position|PipelineInput|Aliases              |
|----------|--------|--------|-------------|---------------------|
|`[UInt32]`|false   |named   |False        |InsertStepsStartIndex|



#### **Step**

Specify one or more step objects to add to the task sequence. To get this object, use one of the New-CMTSStep\ * cmdlets. For example, Get-CMTSStepApplyDataImage (Get-CMTSStepApplyDataImage.md).






|Type               |Required|Position|PipelineInput|Aliases|
|-------------------|--------|--------|-------------|-------|
|`[IResultObject[]]`|true    |named   |False        |Steps  |



#### **TaskSequenceId**

Specify the ID of a task sequence to which the cmdlet adds the step. This ID is the task sequence package ID, for example `XYZ00861`.






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[String]`|true    |named   |False        |Id<br/>TaskSequencePackageId|



#### **TaskSequenceName**

Specify the name of a task sequence to which the cmdlet adds the step.






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
While not listed in the related links section, you can use the Get-CMTSStep\ , New-CMTSStep\ , Remove-CMTSStep\ *, and Set-CMTSStep\ * cmdlets. For example:

- Get-CMTSStepApplyDataImage (Get-CMTSStepApplyDataImage.md)- New-CMTSStepApplyDataImage (New-CMTSStepApplyDataImage.md)- Remove-CMTSStepApplyDataImage (Remove-CMTSStepApplyDataImage.md)- Set-CMTSStepApplyDataImage (Set-CMTSStepApplyDataImage.md)There's a set of these cmdlets for each task sequence step.



---


### Syntax
```PowerShell
Add-CMTaskSequenceStep [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-InsertStepStartIndex <UInt32>] -Step <IResultObject[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMTaskSequenceStep [-DisableWildcardHandling] [-ForceWildcardHandling] [-InsertStepStartIndex <UInt32>] -Step <IResultObject[]> -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMTaskSequenceStep [-DisableWildcardHandling] [-ForceWildcardHandling] [-InsertStepStartIndex <UInt32>] -Step <IResultObject[]> -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```

New-CMTSStepSetDynamicVariable
------------------------------




### Synopsis
Create a Set Dynamic Variables step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Set Dynamic Variables step object. Use the New-CMTSRule (New-CMTSRule.md) cmdlet to define the rules for this step. Then use the [Add-CMTaskSequenceStep](Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Set Dynamic Variables](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_SetDynamicVariables).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepSetDynamicVariable](Get-CMTSStepSetDynamicVariable)



* [Remove-CMTSStepSetDynamicVariable](Remove-CMTSStepSetDynamicVariable)



* [Set-CMTSStepSetDynamicVariable](Set-CMTSStepSetDynamicVariable)



* [New-CMTSRule](New-CMTSRule)



* [About task sequence steps: Set Dynamic Variables](About task sequence steps: Set Dynamic Variables)





---


### Examples
#### Example 1
```PowerShell
$tsrule1 = New-CMTSRule -Variable @{'OSDDownloadDestinationLocationType' = 'TSCache'} -ReferencedVariableName "_SMSTSInWinPE" -ReferencedVariableOperator Equals -ReferencedVariableValue TRUE

$tsrule2 = New-CMTSRule -Variable @{'OSDMigrateUseHardlinks' = 'true'} -ReferencedVariableName "_SMSTSMediaType" -ReferencedVariableOperator NotEquals -ReferencedVariableValue "OEMMedia"

$step = New-CMTSStepSetDynamicVariable -Name "Set Dynamic Variables" -AddRule $tsrule1,$tsrule2

$tsNameOsd = "Default OS deployment"
$tsOsd = Get-CMTaskSequence -Name $tsNameOsd -Fast

$tsOsd | Add-CMTaskSequenceStep -Step $step -InsertStepStartIndex 11
```



---


### Parameters
#### **AddRule**

Specify one or more rule objects. Rules define the criteria and variables to set when they evaluate true. To get this object, use the New-CMTSRule (New-CMTSRule.md)cmdlet. The order of the rules in the array determines the order in this step.






|Type               |Required|Position|PipelineInput|Aliases |
|-------------------|--------|--------|-------------|--------|
|`[IResultObject[]]`|true    |named   |False        |AddRules|



#### **Condition**

Specify a condition object to use with this step. To get this object, use one of the task sequence condition cmdlets. For example, Get-CMTSStepConditionVariable (Get-CMTSStepConditionVariable.md).






|Type               |Required|Position|PipelineInput|Aliases   |
|-------------------|--------|--------|-------------|----------|
|`[IResultObject[]]`|false   |named   |False        |Conditions|



#### **ContinueOnError**

Add this parameter to enable the step option Continue on error . When you enable this option, if the step fails, the task sequence continues.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Description**

Specify an optional description for this task sequence step.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Disable**

Add this parameter to disable this task sequence step.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[Switch]`|false   |named   |False        |DisableThisStep|



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



#### **Name**

Specify a name for this step to identify it in the task sequence.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |StepName|



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
None





---


### Outputs
* IResultObject#SMS_TaskSequence_SetDynamicVariablesAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_SetDynamicVariablesAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_setdynamicvariablesaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepSetDynamicVariable -AddRule <IResultObject[]> [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```

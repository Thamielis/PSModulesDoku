New-CMTSStepConditionVariable
-----------------------------




### Synopsis
Create a task sequence variable condition for a task sequence step.



---


### Description

Use this cmdlet to create a task sequence variable condition object for a task sequence step. Then use one of the New-CMTSStep\ or Set-CMTSStep\ cmdlets with the Condition or AddCondition** parameters. For example, Set-CMTSStepApplyDataImage (Set-CMTSStepApplyDataImage.md).



For more information, see Use the task sequence editor: Conditions (/mem/configmgr/osd/understand/task-sequence-editor#bkmk_conditions).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTaskSequenceStepCondition](Get-CMTaskSequenceStepCondition)



* [Use the task sequence editor: Conditions](Use the task sequence editor: Conditions)



* [How to access variables in a step condition](How to access variables in a step condition)





---


### Examples
#### Example 1: Default condition
```PowerShell
$tscondition = New-CMTSStepConditionVariable -ConditionVariableName "_SMSTSInWinPE" -ConditionVariableValue "false" -OperatorType Equals

$tsname = "Default IPU"
$tsstep = "Set Dynamic Variables"

Set-CMTSStepSetDynamicVariable -TaskSequenceName $tsname -StepName $tsstep -AddCondition $tscondition
```



---


### Parameters
#### **ConditionVariableName**

Specify the name of the task sequence variable to evaluate. This variable name can be a built-in task sequence variable or a custom one that you created. For more information, see the reference of Task sequence variables in Configuration Manager (/mem/configmgr/osd/understand/task-sequence-variables).






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |Variable|



#### **ConditionVariableValue**

If you use a comparative OperatorType like `Equals`, then specify the value of the variable to evaluate in the condition.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |Value  |



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



#### **OperatorType**

Specify the operator type to evaluate the value of the variable in the condition. If you use `Exists` or `NotExists`, then the ConditionVariableValue parameter isn't required. For the other comparative operator types, use the ConditionVariableValue parameter to specify the value to compare.



Valid Values:

* Exists
* NotExists
* Equals
* NotEquals
* Greater
* GreaterEqual
* Less
* LessEqual
* Like
* NotLike






|Type                    |Required|Position|PipelineInput|Aliases  |
|------------------------|--------|--------|-------------|---------|
|`[VariableOperatorType]`|true    |named   |False        |Condition|



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
* IResultObject#SMS_TaskSequence_VariableConditionExpression






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_VariableConditionExpression server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_variableconditionexpression-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepConditionVariable -ConditionVariableName <String> [-ConditionVariableValue <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -OperatorType {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual | Like | NotLike} [-Confirm] [-WhatIf] [<CommonParameters>]
```

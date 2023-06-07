New-CMTSStepConditionIfStatement
--------------------------------




### Synopsis
Create an if statement condition for a task sequence step.



---


### Description

Use this cmdlet to create an if statement condition object for a task sequence step. Then use one of the New-CMTSStep\ or Set-CMTSStep\ cmdlets with the Condition or AddCondition** parameters. For example, Set-CMTSStepApplyDataImage (Set-CMTSStepApplyDataImage.md).



For more information, see Use the task sequence editor: Conditions (/mem/configmgr/osd/understand/task-sequence-editor#bkmk_conditions).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepConditionIfStatement](Get-CMTSStepConditionIfStatement)



* [Use the task sequence editor: Conditions](Use the task sequence editor: Conditions)





---


### Examples
#### Example 1
```PowerShell
$file = "C:\Program Files (x86)\Microsoft Endpoint Manager\AdminConsole\bin\en-US\AdminUI.PS.dll-Help.xml"
$datetime = Get-Date ("August 2, 2021")
$conditionFile = New-CMTSStepConditionFile -FilePath $file -FileTimestamp $datetime -FileDateTimeOperator Greater

$model = "Latitude E7470"
$wmiQuery = "Select * From Win32_ComputerSystem Where Model = `"$Model`""
$conditionQuery = New-CMTSStepConditionQueryWMI -Namespace "root\cimv2" -Query $wmiQuery

$condition = New-CMTSStepConditionIfStatement -StatementType All -Condition $conditionFile,$conditionQuery

$tsNameOsd = "Default OS deployment"
$tsStepNameSetDynVar = "Set Dynamic Variables"

Set-CMTSStepSetDynamicVariable -TaskSequenceName $tsNameOsd -StepName $tsStepNameSetDynVar -AddCondition $condition

If  All  the conditions are true:
    File  C:\Program Files (x86)\Microsoft Endpoint Manager\AdminConsole\bin\en-US\AdminUI.PS.dll-Help.xml exists  and  timestamp greater than "8/1/2021 16:00:00"
    WMI Query  Select * From Win32_ComputerSystem Where Model = "Latitude E7470"
```



---


### Parameters
#### **Condition**

Specify one or more condition objects to include in this if statement block. To get these nested objects, use one of the New-CMTSStepCondition\ * cmdlets. For example, New-CMTSStepConditionFile (New-CMTSStepConditionFile.md).






|Type               |Required|Position|PipelineInput|Aliases                       |
|-------------------|--------|--------|-------------|------------------------------|
|`[IResultObject[]]`|false   |named   |False        |SubCondition<br/>SubConditions|



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



#### **StatementType**

Specify the type of if statement to create. There are three types of checks that you can do with this condition:


* If `All` of the conditions are true


* If `Any` of the conditions are true


* If `None` of the conditions are true



Valid Values:

* All
* Any
* None






|Type                      |Required|Position|PipelineInput|Aliases |
|--------------------------|--------|--------|-------------|--------|
|`[ConditionStatementType]`|true    |named   |False        |Operator|



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
* IResultObject#SMS_TaskSequence_ConditionOperator






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_ConditionOperator server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_conditionoperator-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepConditionIfStatement [-Condition <IResultObject[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] -StatementType {All | Any | None} [-Confirm] [-WhatIf] [<CommonParameters>]
```

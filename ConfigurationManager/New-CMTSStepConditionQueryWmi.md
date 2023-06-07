New-CMTSStepConditionQueryWmi
-----------------------------




### Synopsis
Create a WMI query condition for a task sequence step.



---


### Description

Use this cmdlet to create a WMI query condition object for a task sequence step. Then use one of the New-CMTSStep\ or Set-CMTSStep\ cmdlets with the Condition or AddCondition** parameters. For example, Set-CMTSStepApplyDataImage (Set-CMTSStepApplyDataImage.md).



For more information, see Use the task sequence editor: Conditions (/mem/configmgr/osd/understand/task-sequence-editor#bkmk_conditions).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepConditionQueryWmi](Get-CMTSStepConditionQueryWmi)



* [Use the task sequence editor: Conditions](Use the task sequence editor: Conditions)





---


### Examples
#### Example 1: Create a query condition based on hardware model
```PowerShell
$model = "Latitude E7470"
$query = "Select * From Win32_ComputerSystem Where Model = `"$model`""

$condition = New-CMTSStepConditionQueryWMI -Namespace "root\cimv2" -Query $query

$tsNameOsd = "Default OS deployment"
$tsStepNameRunPwsh = "Run PowerShell Script"

Set-CMTSStepRunPowerShellScript -TaskSequenceName $tsNameOsd -StepName $tsStepNameRunPwsh -AddCondition $condition
```
This sample script creates the following condition on the step:


`WMI Query  Select * From Win32_ComputerSystem Where Model = "Latitude E7470"`


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



#### **Namespace**

Specify the WMI namespace for the query. For example, `root\cimv2`






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **Query**

Specify the WMI query. The cmdlet doesn't test the validity of the query.






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
None





---


### Outputs
* IResultObject#SMS_TaskSequence_WMIConditionExpression






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_WMIConditionExpression server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_wmiconditionexpression-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepConditionQueryWmi [-DisableWildcardHandling] [-ForceWildcardHandling] [-Namespace <String[]>] -Query <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```

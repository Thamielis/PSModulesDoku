New-CMTSStepConditionFolder
---------------------------




### Synopsis
Create a folder properties condition for a task sequence step.



---


### Description

Use this cmdlet to create a folder properties condition object for a task sequence step. Then use one of the New-CMTSStep\ or Set-CMTSStep\ cmdlets with the Condition or AddCondition** parameters. For example, Set-CMTSStepApplyDataImage (Set-CMTSStepApplyDataImage.md).



For more information, see Use the task sequence editor: Conditions (/mem/configmgr/osd/understand/task-sequence-editor#bkmk_conditions).



There are two types of checks that you can do with this condition:



- To check if the folder exists, use the required FolderPath parameter. - To also check the folder timestamp, use the FolderTimestamp and FolderDateTimeOperator parameters.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepConditionFolder](Get-CMTSStepConditionFolder)



* [Use the task sequence editor: Conditions](Use the task sequence editor: Conditions)





---


### Examples
#### Example 1
```PowerShell
$folder = "C:\Program Files (x86)\Microsoft Endpoint Manager\AdminConsole\bin\en-US"
$datetime = Get-Date ("August 2, 2021")

$condition = New-CMTSStepConditionFolder -FolderPath $folder -FolderTimestamp $datetime -FolderDateTimeOperator Greater

$tsNameOsd = "Default OS deployment"
$tsStepNameRunPwsh = "Run PowerShell Script"

Set-CMTSStepRunPowerShellScript -TaskSequenceName $tsNameOsd -StepName $tsStepNameRunPwsh -AddCondition $condition
```
This sample script creates the following condition on the step:


`Folder  C:\Program Files (x86)\Microsoft Endpoint Manager\AdminConsole\bin\en-US exists  and  timestamp greater than "8/1/2021 16:00:00"`


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FolderDateTimeOperator**

When you use the FolderTimestamp parameter, use this parameter to specify the operator for the task sequence to evaluate the folder's timestamp.



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






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[VariableOperatorType]`|false   |named   |False        |



#### **FolderPath**

Specify the full path of the folder for this condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **FolderTimestamp**

To evaluate the folder's timestamp, use this parameter to specify a datetime object. To get this object, use the built-in Get-Date (/powershell/module/microsoft.powershell.utility/get-date)cmdlet.


Then use the FolderDateTimeOperator parameter to set the evaluation operator.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
* IResultObject#SMS_TaskSequence_FolderConditionExpression






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_FolderConditionExpression server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_folderconditionexpression-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepConditionFolder [-DisableWildcardHandling] [-FolderDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] -FolderPath <String> [-FolderTimestamp <DateTime>] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```

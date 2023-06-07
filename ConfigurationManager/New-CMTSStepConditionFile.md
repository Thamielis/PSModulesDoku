New-CMTSStepConditionFile
-------------------------




### Synopsis
Create a file properties condition for a task sequence step.



---


### Description

Use this cmdlet to create a file properties condition object for a task sequence step. Then use one of the New-CMTSStep\ or Set-CMTSStep\ cmdlets with the Condition or AddCondition** parameters. For example, Set-CMTSStepApplyDataImage (Set-CMTSStepApplyDataImage.md).



For more information, see Use the task sequence editor: Conditions (/mem/configmgr/osd/understand/task-sequence-editor#bkmk_conditions).



There are three types of checks that you can do with this condition:



- To check if the file exists, use the required FilePath parameter. - To also check the file version, use the FileVersion and VersionOperator parameters. - To also check the file timestamp, use the FileTimestamp and FileDateTimeOperator parameters.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepConditionFile](Get-CMTSStepConditionFile)



* [Use the task sequence editor: Conditions](Use the task sequence editor: Conditions)





---


### Examples
#### Example 1
```PowerShell
$file = "C:\Program Files (x86)\Microsoft Endpoint Manager\AdminConsole\bin\en-US\AdminUI.PS.dll-Help.xml"
$datetime = Get-Date ("August 2, 2021")

$condition = New-CMTSStepConditionFile -FilePath $file -FileTimestamp $datetime -FileDateTimeOperator Greater

$tsNameOsd = "Default OS deployment"
$tsStepNameRunPwsh = "Run PowerShell Script"

Set-CMTSStepRunPowerShellScript -TaskSequenceName $tsNameOsd -StepName $tsStepNameRunPwsh -AddCondition $condition
```
This sample script creates the following condition on the step:


`File  C:\Program Files (x86)\Microsoft Endpoint Manager\AdminConsole\bin\en-US\AdminUI.PS.dll-Help.xml exists  and  timestamp greater than "8/1/2021 16:00:00"`


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FileDateTimeOperator**

When you use the FileTimestamp parameter, use this parameter to specify the operator for the task sequence to evaluate the file's timestamp.



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



#### **FilePath**

Specify the full path including the name of the file for this condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **FileTimestamp**

To evaluate the file's timestamp, use this parameter to specify a datetime object. To get this object, use the built-in Get-Date (/powershell/module/microsoft.powershell.utility/get-date)cmdlet.


Then use the FileDateTimeOperator parameter to set the evaluation operator.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **FileVersion**

To evaluate the file's version, use this parameter to specify the version string.


Then use the VersionOperator parameter to set the evaluation operator.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **VersionOperator**

When you use the FileVersion parameter, use this parameter to specify the operator for the task sequence to evaluate the file's version.



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
* IResultObject#SMS_TaskSequence_FileConditionExpression






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_FileConditionExpression server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_fileconditionexpression-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepConditionFile [-DisableWildcardHandling] [-FileDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] -FilePath <String> [-FileTimestamp <DateTime>] [-FileVersion <String>] [-ForceWildcardHandling] [-VersionOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-Confirm] [-WhatIf] [<CommonParameters>]
```

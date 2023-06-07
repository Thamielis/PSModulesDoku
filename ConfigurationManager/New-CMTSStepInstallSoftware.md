New-CMTSStepInstallSoftware
---------------------------




### Synopsis
Create an Install Package step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Install Package step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Install Package](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_InstallPackage).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepInstallSoftware](Get-CMTSStepInstallSoftware)



* [Remove-CMTSStepInstallSoftware](Remove-CMTSStepInstallSoftware)



* [Set-CMTSStepInstallSoftware](Set-CMTSStepInstallSoftware)



* [About task sequence steps: Install Package](About task sequence steps: Install Package)





---


### Examples
#### Example 1
```PowerShell
$program = Get-CMProgram -PackageId "XYZ0000F" -ProgramName "Install"

$step = New-CMTSStepInstallSoftware -Name "Install Package" -Program $program

$tsNameOsd = "Default OS deployment"
$tsOsd = Get-CMTaskSequence -Name $tsNameOsd -Fast

$tsOsd | Add-CMTaskSequenceStep -Step $step -InsertStepStartIndex 11
```



---


### Parameters
#### **BaseVariableName**

Use this parameter to install software packages according to a dynamic variable list. Then the task sequence installs packages using this base variable name. For more information, see Install software packages according to dynamic variable list (/mem/configmgr/osd/understand/task-sequence-steps#install-software-packages-according-to-dynamic-variable-list).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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



#### **ContinueOnInstallError**

Add this parameter to continue installing other packages in the list if a package fails to install. If you don't specify this setting, and the installation fails, the step immediately ends.






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



#### **Program**

Specify a program object from a package to install. To get this object, use the Get-CMProgram (Get-CMProgram.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



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
* IResultObject#SMS_TaskSequence_InstallSoftwareAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_InstallSoftwareAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_installsoftwareaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepInstallSoftware [-BaseVariableName <String>] [-Condition <IResultObject[]>] [-ContinueOnError] [-ContinueOnInstallError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Program <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

New-CMTSStepInstallApplication
------------------------------




### Synopsis
Create an Install Application step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Install Application step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Install Application](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_InstallApplication).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepInstallApplication](Get-CMTSStepInstallApplication)



* [Remove-CMTSStepInstallApplication](Remove-CMTSStepInstallApplication)



* [Set-CMTSStepInstallApplication](Set-CMTSStepInstallApplication)



* [About task sequence steps: Install Application](About task sequence steps: Install Application)





---


### Examples
#### Example 1
```PowerShell
$app = Get-CMApplication -Name "Central app"

$step = New-CMTSStepInstallApplication -Name "Install Application" -Application $app

$tsNameOsd = "Default OS deployment"
$tsOsd = Get-CMTaskSequence -Name $tsNameOsd -Fast

$tsOsd | Add-CMTaskSequenceStep -Step $step -InsertStepStartIndex 11
```



---


### Parameters
#### **Application**

Specify one or more application objects to install. To get this object, use the Get-CMApplication (Get-CMApplication.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases     |
|-------------------|--------|--------|-------------|------------|
|`[IResultObject[]]`|false   |named   |False        |Applications|



#### **BaseVariableName**

Use this parameter to install applications according to a dynamic variable list. Then the task sequence installs applications using this base variable name. For more information, see Install applications according to dynamic variable list (/mem/configmgr/osd/understand/task-sequence-steps#install-applications-according-to-dynamic-variable-list).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ClearCache**

Set this parameter to `$true` to clear application content from the client cache after installing the app. This behavior is beneficial on devices with small hard drives or when installing lots of large apps in succession.






|Type       |Required|Position|PipelineInput|Aliases        |
|-----------|--------|--------|-------------|---------------|
|`[Boolean]`|false   |named   |False        |RemoveFromCache|



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

Add this parameter to continue installing other applications in the list if an application fails to install. If you don't specify this setting, and the installation fails, the step immediately ends.






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



#### **RetryCount**

If one of the application installations unexpectedly restarts the computer, retry this step for the number of times that you specify with this parameter. By default, the step retries twice. Specify an integer value from `1` to `5`.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



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
* IResultObject#SMS_TaskSequence_InstallApplicationAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_InstallApplicationAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_installapplicationaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepInstallApplication [-Application <IResultObject[]>] [-BaseVariableName <String>] [-ClearCache <Boolean>] [-Condition <IResultObject[]>] [-ContinueOnError] [-ContinueOnInstallError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-RetryCount <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

New-CMTSStepAutoApplyDriver
---------------------------




### Synopsis
Create an Auto Apply Drivers step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Auto Apply Drivers step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Auto Apply Drivers](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_AutoApplyDrivers).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepAutoApplyDriver](Get-CMTSStepAutoApplyDriver)



* [Remove-CMTSStepAutoApplyDriver](Remove-CMTSStepAutoApplyDriver)



* [Set-CMTSStepAutoApplyDriver](Set-CMTSStepAutoApplyDriver)



* [About task sequence steps: Auto Apply Drivers](About task sequence steps: Auto Apply Drivers)





---


### Examples
#### Example 1
```PowerShell
$category = Get-CMCategory -CategoryType DriverCategories -Name "Surface"

$step = New-CMTSStepAutoApplyDriver -Name "Auto Apply Drivers" -DriverCategory $category -InstallDriverOption InstallAllCompatible

$tsNameOsd = "Default OS deployment"
$tsOsd = Get-CMTaskSequence -Name $tsNameOsd -Fast

$tsOsd | Add-CMTaskSequenceStep -Step $step -InsertStepStartIndex 11
```



---


### Parameters
#### **AllowUnsignedDriver**

Add this parameter to allow Windows to install drivers without a digital signature.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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



#### **DriverCategory**

Specify one or more driver category objects, to limit driver matching to only consider drivers in the selected categories. To get this object, use the Get-CMCategory (Get-CMCategory.md)cmdlet with `-CategoryType DriverCategories`.






|Type               |Required|Position|PipelineInput|Aliases         |
|-------------------|--------|--------|-------------|----------------|
|`[IResultObject[]]`|false   |named   |False        |DriverCategories|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InstallDriverOption**

Specify how this step behaves:


* `BestMatch`: Install only the best matched compatible drivers.


* `InstallAllCompatible`: Installs all drivers compatible for each detected hardware device.



Valid Values:

* BestMatch
* InstallAllCompatible






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[InstallDriverType]`|false   |named   |False        |



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
* IResultObject#SMS_TaskSequence_AutoApplyAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_AutoApplyAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_autoapplyaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepAutoApplyDriver [-AllowUnsignedDriver] [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-DriverCategory <IResultObject[]>] [-ForceWildcardHandling] [-InstallDriverOption {BestMatch | InstallAllCompatible}] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```

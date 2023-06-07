New-CMTSStepConditionOperatingSystem
------------------------------------




### Synopsis
Create an OS version condition for a task sequence step.



---


### Description

Use this cmdlet to create an OS version condition object for a task sequence step. Then use one of the New-CMTSStep\ or Set-CMTSStep\ cmdlets with the Condition or AddCondition** parameters. For example, Set-CMTSStepApplyDataImage (Set-CMTSStepApplyDataImage.md).



For more information, see Use the task sequence editor: Conditions (/mem/configmgr/osd/understand/task-sequence-editor#bkmk_conditions).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepConditionOperatingSystem](Get-CMTSStepConditionOperatingSystem)



* [New-CMTSStepConditionOperatingSystemLanguage](New-CMTSStepConditionOperatingSystemLanguage)



* [Use the task sequence editor: Conditions](Use the task sequence editor: Conditions)





---


### Examples
#### Example 1
```PowerShell
$osPlat = Get-CMSupportedPlatform -Name "*Windows 1? (64-bit) Client" -Fast

$condition = New-CMTSStepConditionOperatingSystem -SupportedPlatform $osPlat

$tsNameOsd = "Default OS deployment"
$tsStepNameDynVar = "Set Dynamic Variables"

Set-CMTSStepSetDynamicVariable -TaskSequenceName $tsNameOsd -StepName $tsStepNameDynVar -AddCondition $condition
```
This sample script creates the following condition on the step:


`Operating System  equals All Windows 10 (64-bit) Or All Windows 11 (64-bit)`


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



#### **SupportedPlatform**

Specify one or more supported platform objects for this condition. To get this object, use the Get-CMSupportedPlatform (Get-CMSupportedPlatform.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases           |
|-------------------|--------|--------|-------------|------------------|
|`[IResultObject[]]`|true    |named   |False        |SupportedPlatforms|



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
* IResultObject#SMS_TaskSequence_OSConditionGroup






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_OSConditionGroup server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_osconditiongroup-server-wmi-class).

To create an OS language condition, use the New-CMTSStepConditionOperatingSystemLanguage (New-CMTSStepConditionOperatingSystemLanguage.md)cmdlet.



---


### Syntax
```PowerShell
New-CMTSStepConditionOperatingSystem [-DisableWildcardHandling] [-ForceWildcardHandling] -SupportedPlatform <IResultObject[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```

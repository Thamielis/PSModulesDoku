New-CMTSStepSetupWindowsAndConfigMgr
------------------------------------




### Synopsis
Create a Setup Windows and ConfigMgr step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Setup Windows and ConfigMgr step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Setup Windows and ConfigMgr](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_SetupWindowsandConfigMgr).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepSetupWindowsAndConfigMgr](Get-CMTSStepSetupWindowsAndConfigMgr)



* [Remove-CMTSStepSetupWindowsAndConfigMgr](Remove-CMTSStepSetupWindowsAndConfigMgr)



* [Set-CMTSStepSetupWindowsAndConfigMgr](Set-CMTSStepSetupWindowsAndConfigMgr)



* [About task sequence steps: Setup Windows and ConfigMgr](About task sequence steps: Setup Windows and ConfigMgr)





---


### Examples
#### Example 1
```PowerShell
$step = New-CMTSStepSetupWindowsAndConfigMgr -Name "Setup Windows and ConfigMgr" -PackageId "XYZ0002"

$tsNameOsd = "Default OS deployment"
$tsOsd = Get-CMTaskSequence -Name $tsNameOsd -Fast

$tsOsd | Add-CMTaskSequenceStep -Step $step -InsertStepStartIndex 11
```



---


### Parameters
#### **Condition**

Specify a condition object to use with this step. To get this object, use one of the task sequence condition cmdlets. For example, Get-CMTSStepConditionVariable (Get-CMTSStepConditionVariable.md).






|Type               |Required|Position|PipelineInput|Aliases   |
|-------------------|--------|--------|-------------|----------|
|`[IResultObject[]]`|false   |named   |False        |Conditions|



#### **ContinueOnError**

Add this parameter to enable the step option Continue on error .


Specifically with this step, if there's an error, the task sequence fails whether or not this setting is enabled.






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



#### **InstallationProperty**

The task sequence step automatically specifies site assignment and the default configuration. Use this parameter to specify any additional installation properties to use when you install the client. To enter multiple installation properties, separate them with a space.






|Type      |Required|Position|PipelineInput|Aliases               |
|----------|--------|--------|-------------|----------------------|
|`[String]`|false   |named   |False        |InstallationProperties|



#### **Name**

Specify a name for this step to identify it in the task sequence.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |StepName|



#### **PackageId**

Specify the package ID of the the Configuration Manager client installation package to use with this step. This value is a standard package ID, for example `XYZ0002`.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[String]`|true    |named   |False        |ClientPackageId|



#### **PreproductionPackageId**

Specify the package ID of the pre-production client installation package to use with this step.


If there's a pre-production client package available, and the computer is a member of the piloting collection, the task sequence uses this package instead of the production client package. The pre-production client is a newer version for testing in the production environment.






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[String]`|false   |named   |False        |PreproductionClientPackageId|



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
* IResultObject#SMS_TaskSequence_SetupWindowsAndSMSAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_SetupWindowsAndSMSAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_setupwindowsandsmsaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepSetupWindowsAndConfigMgr [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-ForceWildcardHandling] [-InstallationProperty <String>] -Name <String> -PackageId <String> [-PreproductionPackageId <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

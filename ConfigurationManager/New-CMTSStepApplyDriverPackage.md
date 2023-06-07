New-CMTSStepApplyDriverPackage
------------------------------




### Synopsis
Create an Apply Driver Package step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Apply Driver Package step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Apply Driver Package](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ApplyDriverPackage).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepApplyDriverPackage](Get-CMTSStepApplyDriverPackage)



* [Remove-CMTSStepApplyDriverPackage](Remove-CMTSStepApplyDriverPackage)



* [Set-CMTSStepApplyDriverPackage](Set-CMTSStepApplyDriverPackage)



* [Get-CMDriverPackage](Get-CMDriverPackage)



* [About task sequence steps: Apply Driver Package](About task sequence steps: Apply Driver Package)





---


### Examples
#### Example 1
```PowerShell
$pkgDriver = Get-CMDriverPackage -Name "Surface 4 drivers" -Fast
$step = New-CMTSStepApplyDriverPackage -Name "Apply driver package" -PackageId $pkgDriver.PackageID

$tsName = "Default OS deployment"
$tsOsd = Get-CMTaskSequence -Name $tsName -Fast

$tsOsd | Add-CMTaskSequenceStep -Step $step -InsertStepStartIndex 11
```



---


### Parameters
#### **BootCriticalContentUniqueId**

This parameter is deprecated, it only applies to pre-Windows Vista OS versions.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **BootCriticalDriverId**

This parameter is deprecated, it only applies to pre-Windows Vista OS versions.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **BootCriticalHardwareComponent**

This parameter is deprecated, it only applies to pre-Windows Vista OS versions.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **BootCriticalId**

This parameter is deprecated, it only applies to pre-Windows Vista OS versions.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **BootCriticalInfFile**

This parameter is deprecated, it only applies to pre-Windows Vista OS versions.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Condition**

Specify a condition object to use with this step.






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



#### **EnableRecurse**

Add this parameter to install the driver package by running DISM with the recurse option.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableUnsignedDriver**

Add this parameter to do an unattended installation of unsigned drivers on a version of Windows where this action is allowed.






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



#### **PackageId**

Specify the package ID of the driver package for this step to apply. This value is a standard package ID, for example, `XYZ0030D`.






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
* IResultObject#SMS_TaskSequence_ApplyDriverPackageAction






---


### Notes




---


### Syntax
```PowerShell
New-CMTSStepApplyDriverPackage [-BootCriticalContentUniqueId <String>] [-BootCriticalDriverId <String>] [-BootCriticalHardwareComponent <String>] [-BootCriticalId <String>] [-BootCriticalInfFile <String>] [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-EnableRecurse] [-EnableUnsignedDriver] [-ForceWildcardHandling] -Name <String> -PackageId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```

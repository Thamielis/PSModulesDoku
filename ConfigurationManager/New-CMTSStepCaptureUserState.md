New-CMTSStepCaptureUserState
----------------------------




### Synopsis
Create a Capture User State step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Capture User State step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Capture User State](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_CaptureUserState).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepCaptureUserState](Get-CMTSStepCaptureUserState)



* [Remove-CMTSStepCaptureUserState](Remove-CMTSStepCaptureUserState)



* [Set-CMTSStepCaptureUserState](Set-CMTSStepCaptureUserState)



* [About task sequence steps: Capture User State](About task sequence steps: Capture User State)





---


### Examples
#### Example 1
```PowerShell
$pkgUsmt = Get-CMPackage -Name "User State Migration Tool for Windows" -Fast

$step = New-CMTSStepCaptureUserState -Name "Capture User State" -Package $pkgUsmt -ModeOption Standard -VerboseLogging $true -FileAccessOption Normal -ContinueOnLockedFile $true -UseHardLinks $true

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



#### **ConfigFile**

When you specify `-ModeOption Customize` to customize how user profiles are captured, use this parameter to specify the file names of custom XML configuration files. These files need to be in the USMT package.






|Type        |Required|Position|PipelineInput|Aliases    |
|------------|--------|--------|-------------|-----------|
|`[String[]]`|false   |named   |False        |ConfigFiles|



#### **ContinueOnError**

Add this parameter to enable the step option Continue on error . When you enable this option, if the step fails, the task sequence continues.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ContinueOnLockedFile**

When you specify `-FileAccessOption Normal`, set this parameter to `$true` to allow USMT to continue if some files can't be captured.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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



#### **FileAccessOption**

There are two options for how USMT accesses the file system:


* `Normal`: USMT uses standard file system access. When you specify this option, you can also enable ContinueOnLockedFile , OfflineUserState , and - .


* `VolumeCopyShadowService`: USMT uses the Volume Copy Shadow Services (VSS).



Valid Values:

* Normal
* VolumeCopyShadowService






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[FileAccessType]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ModeOption**

There are two modes in which USMT can operate:


* `Standard`: Capture all user profiles by using standard options. This option is the default.


* `Customize`: Customize how user profiles are captured. If you specify this option, use the ConfigFile parameter to specify the custom XML configuration files.



Valid Values:

* Standard
* Customize






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[ModeType]`|false   |named   |False        |



#### **Name**

Specify a name for this step to identify it in the task sequence.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |StepName|



#### **OfflineUserState**

When you specify `-FileAccessOption Normal`, set this parameter to `$true` to capture in offline mode in Windows PE.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Package**

Specify an object for the USMT package. To get this object, use the Get-CMPackage (Get-CMPackage.md)cmdlet.






|Type             |Required|Position|PipelineInput|Aliases                      |
|-----------------|--------|--------|-------------|-----------------------------|
|`[IResultObject]`|true    |named   |False        |UserStateMigrationToolPackage|



#### **SkipEncryptedFile**

Set this parameter to `$true` to skip files that use the encrypting file system (EFS).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UseHardLinks**

When you specify `-FileAccessOption Normal`, set this parameter to `$true` to capture locally by using NTFS hard-links.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **VerboseLogging**

Set this parameter to `$true` to enable USMT verbose logging.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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
* IResultObject#SMS_TaskSequence_CaptureUserStateAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_CaptureUserStateAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_captureuserstateaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepCaptureUserState [-Condition <IResultObject[]>] [-ConfigFile <String[]>] [-ContinueOnError] [-ContinueOnLockedFile <Boolean>] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-FileAccessOption {Normal | VolumeCopyShadowService}] [-ForceWildcardHandling] [-ModeOption {Standard | Customize}] -Name <String> [-OfflineUserState <Boolean>] -Package <IResultObject> [-SkipEncryptedFile <Boolean>] [-UseHardLinks <Boolean>] [-VerboseLogging <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

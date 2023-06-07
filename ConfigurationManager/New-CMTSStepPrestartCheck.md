New-CMTSStepPrestartCheck
-------------------------




### Synopsis
Create a Check Readiness step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Check Readiness step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Check Readiness](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_CheckReadiness).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepPrestartCheck](Get-CMTSStepPrestartCheck)



* [Remove-CMTSStepPrestartCheck](Remove-CMTSStepPrestartCheck)



* [Set-CMTSStepPrestartCheck](Set-CMTSStepPrestartCheck)



* [About task sequence steps: Check Readiness](About task sequence steps: Check Readiness)





---


### Examples
#### Example 1
```PowerShell
$parameters = @{
  Name = "Check Readiness"
  CheckMemory = $true
  Memory = 4096
  CheckSpeed = $true
  Speed = 1024
  CheckSpace = $true
  DiskSpace = 512000
  CheckOS = $true
  OS = "Client"
  CheckOSArchitecture = $true
  OSArchitecture = "Arch64"
  CheckMinOSVersion = $true
  MinOSVersion = "10.0.16299"
  CheckMaxOSVersion = $true
  MaxOSVersion = "10.0.99999"
  CheckCMClientMinVersion = $true
  CMClientMinVersion = "5.00.8913.1005"
  CheckOSLanguageId = $true
  OSLanguageID = 1033
  CheckPowerState = $true
  CheckNetworkConnected = $true
  CheckNetworkWired = $false
  CheckUefi = $true
}

$step = New-CMTSStepPrestartCheck @parameters

$tsNameOsd = "Default OS deployment"
$tsOsd = Get-CMTaskSequence -Name $tsNameOsd -Fast

$tsOsd | Add-CMTaskSequenceStep -Step $step -InsertStepStartIndex 11
```



---


### Parameters
#### **CheckCMClientMinVersion**

Set this parameter to `$true` to enable the Minimum client version check. Use the parameter CMClientMinVersion to set the specific client version number.






|Type       |Required|Position|PipelineInput|Aliases              |
|-----------|--------|--------|-------------|---------------------|
|`[Boolean]`|false   |named   |False        |CheckClientMinVersion|



#### **CheckMaxOSVersion**

Set this parameter to `$true` to enable the Maximum OS version check. Use the parameter MaxOSVersion to set the specific OS version number.






|Type       |Required|Position|PipelineInput|Aliases                |
|-----------|--------|--------|-------------|-----------------------|
|`[Boolean]`|false   |named   |False        |EnableCheckMaxOSVersion|



#### **CheckMemory**

Set this parameter to `$true` to enable the Minimum memory (MB) check. Use the parameter Memory to set the specific memory size.






|Type       |Required|Position|PipelineInput|Aliases          |
|-----------|--------|--------|-------------|-----------------|
|`[Boolean]`|false   |named   |False        |EnableCheckMemory|



#### **CheckMinOSVersion**

Set this parameter to `$true` to enable the Minimum OS version check. Use the parameter MinOSVersion to set the specific OS version number.






|Type       |Required|Position|PipelineInput|Aliases                |
|-----------|--------|--------|-------------|-----------------------|
|`[Boolean]`|false   |named   |False        |EnableCheckMinOSVersion|



#### **CheckNetworkConnected**

Set this parameter to `$true` to enable the Network adapter connected check.






|Type       |Required|Position|PipelineInput|Aliases         |
|-----------|--------|--------|-------------|----------------|
|`[Boolean]`|false   |named   |False        |NetworkConnected|



#### **CheckNetworkWired**

Set this parameter to `$true` to enable the Network adapter is not wireless check.






|Type       |Required|Position|PipelineInput|Aliases     |
|-----------|--------|--------|-------------|------------|
|`[Boolean]`|false   |named   |False        |NetworkWired|



#### **CheckOS**

Set this parameter to `$true` to enable the check for the type of OS, either client or server. Use the parameter OS to set the specific OS type.






|Type       |Required|Position|PipelineInput|Aliases          |
|-----------|--------|--------|-------------|-----------------|
|`[Boolean]`|false   |named   |False        |EnableCheckOSType|



#### **CheckOSArchitecture**

Set this parameter to `$true` to enable the Architecture of current OS check. Use the parameter OSArchitecture to set the specific architecture type.






|Type       |Required|Position|PipelineInput|Aliases                  |
|-----------|--------|--------|-------------|-------------------------|
|`[Boolean]`|false   |named   |False        |EnableCheckOSArchitecture|



#### **CheckOSLanguageId**

Set this parameter to `$true` to enable the check of the Language of current OS . Use the parameter OSLanguageID to set the specific language.






|Type       |Required|Position|PipelineInput|Aliases           |
|-----------|--------|--------|-------------|------------------|
|`[Boolean]`|false   |named   |False        |EnableOSLanguageId|



#### **CheckPowerState**

Set this parameter to `$true` to enable the AC power plugged in check.






|Type       |Required|Position|PipelineInput|Aliases   |
|-----------|--------|--------|-------------|----------|
|`[Boolean]`|false   |named   |False        |NotBattery|



#### **CheckSpace**

Set this parameter to `$true` to enable the Minimum free disk space (MB) check. Use the parameter DiskSpace to set the specific size.






|Type       |Required|Position|PipelineInput|Aliases                 |
|-----------|--------|--------|-------------|------------------------|
|`[Boolean]`|false   |named   |False        |EnableCheckFreeDiskSpace|



#### **CheckSpeed**

Set this parameter to `$true` to enable the Minimum processor speed (MHz) check. Use the parameter Speed to set the specific speed.






|Type       |Required|Position|PipelineInput|Aliases                  |
|-----------|--------|--------|-------------|-------------------------|
|`[Boolean]`|false   |named   |False        |EnableCheckProcessorSpeed|



#### **CheckTpmActivated**

Applies to version 2111 and later. Set this parameter to `$true` to enable the TPM 2.0 or above is activated check.






|Type       |Required|Position|PipelineInput|Aliases     |
|-----------|--------|--------|-------------|------------|
|`[Boolean]`|false   |named   |False        |TpmActivated|



#### **CheckTpmEnabled**

Applies to version 2111 and later. Set this parameter to `$true` to enable the TPM 2.0 or above is enabled check.






|Type       |Required|Position|PipelineInput|Aliases   |
|-----------|--------|--------|-------------|----------|
|`[Boolean]`|false   |named   |False        |TpmEnabled|



#### **CheckUefi**

Applies to version 2006 and later. Set this parameter to `$true` to enable the Computer is in UEFI mode check.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **CMClientMinVersion**

Use this parameter to configure the specific client version. Specify the client version in the following format: `5.00.8913.1005`. Use the parameter CheckCMClientMinVersion to enable or disable the check.






|Type      |Required|Position|PipelineInput|Aliases         |
|----------|--------|--------|-------------|----------------|
|`[String]`|false   |named   |False        |ClientMinVersion|



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



#### **DiskSpace**

Use this parameter to configure the specific size for the minimum free disk space check. Specify an integer value for the size in MB. Use the parameter CheckSpace to enable or disable the check.






|Type     |Required|Position|PipelineInput|Aliases             |
|---------|--------|--------|-------------|--------------------|
|`[Int32]`|false   |named   |False        |MinimumFreeDiskSpace|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **MaxOSVersion**

Use this parameter to configure the specific OS version. Specify the maximum OS version with major version, minor version, and build number. For example, `10.0.18356`. Use the parameter CheckMaxOSVersion to enable or disable the check.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|false   |named   |False        |CurrentMaxOSVersion|



#### **Memory**

Use this parameter to configure the specific size for the minimum memory check. Specify an integer value for the size in MB. Use the parameter CheckMemory to enable or disable the check.






|Type     |Required|Position|PipelineInput|Aliases      |
|---------|--------|--------|-------------|-------------|
|`[Int32]`|false   |named   |False        |MinimumMemory|



#### **MinOSVersion**

Use this parameter to configure the specific OS version. Specify the minimum OS version with major version, minor version, and build number. For example, `10.0.16299`. Use the parameter CheckMinOSVersion to enable or disable the check.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|false   |named   |False        |CurrentMinOSVersion|



#### **Name**

Specify a name for this step to identify it in the task sequence.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |StepName|



#### **OS**

Use this parameter to configure the specific OS type: `Client` or `Server`. Use the parameter CheckOS to enable or disable the check.



Valid Values:

* Client
* Server






|Type      |Required|Position|PipelineInput|Aliases      |
|----------|--------|--------|-------------|-------------|
|`[OSType]`|false   |named   |False        |CurrentOSType|



#### **OSArchitecture**

Use this parameter to configure the specific OS architecture: `Arch32` for 32-bit or `Arch64` for 64-bit. Use the parameter CheckOSArchitecture to enable or disable the check.



Valid Values:

* Arch32
* Arch64






|Type      |Required|Position|PipelineInput|Aliases              |
|----------|--------|--------|-------------|---------------------|
|`[OSArch]`|false   |named   |False        |CurrentOSArchitecture|



#### **OSLanguageId**

Use this parameter to configure the specific OS language. This check compares the language ID to the OSLanguage property of the Win32_OperatingSystem WMI class on the client. For example, `1033` for English (United States) . Use the parameter CheckOSLanguageId to enable or disable the check.






|Type     |Required|Position|PipelineInput|Aliases   |
|---------|--------|--------|-------------|----------|
|`[Int32]`|false   |named   |False        |LanguageId|



#### **Speed**

Use this parameter to configure the specific speed for the minimum processor speed check. Specify an integer value for the speed in MHz. Use the parameter CheckSpeed to enable or disable the check.






|Type     |Required|Position|PipelineInput|Aliases              |
|---------|--------|--------|-------------|---------------------|
|`[Int32]`|false   |named   |False        |MinimumProcessorSpeed|



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
* IResultObject#SMS_TaskSequence_PrestartCheckAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_PrestartCheckAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_prestartcheckaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepPrestartCheck [-CheckCMClientMinVersion <Boolean>] [-CheckMaxOSVersion <Boolean>] [-CheckMemory <Boolean>] [-CheckMinOSVersion <Boolean>] [-CheckNetworkConnected <Boolean>] [-CheckNetworkWired <Boolean>] [-CheckOS <Boolean>] [-CheckOSArchitecture <Boolean>] [-CheckOSLanguageId <Boolean>] [-CheckPowerState <Boolean>] [-CheckSpace <Boolean>] [-CheckSpeed <Boolean>] [-CheckTpmActivated <Boolean>] [-CheckTpmEnabled <Boolean>] [-CheckUefi <Boolean>] [-CMClientMinVersion <String>] [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-DiskSpace <Int32>] [-ForceWildcardHandling] [-MaxOSVersion <String>] [-Memory <Int32>] [-MinOSVersion <String>] -Name <String> [-OS {Client | Server}] [-OSArchitecture {Arch32 | Arch64}] [-OSLanguageId <Int32>] [-Speed <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

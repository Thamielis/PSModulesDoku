New-CMTSStepUpgradeOperatingSystem
----------------------------------




### Synopsis
Create an Upgrade OS step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Upgrade OS step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Upgrade OS](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_UpgradeOS).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepUpgradeOperatingSystem](Get-CMTSStepUpgradeOperatingSystem)



* [Remove-CMTSStepUpgradeOperatingSystem](Remove-CMTSStepUpgradeOperatingSystem)



* [Set-CMTSStepUpgradeOperatingSystem](Set-CMTSStepUpgradeOperatingSystem)



* [About task sequence steps: Upgrade OS](About task sequence steps: Upgrade OS)





---


### Examples
#### Example 1
```PowerShell
$osUpgPkg = Get-CMOperatingSystemInstaller -Name "OSUpgradePkg01"
$step = New-CMTSStepUpgradeOperatingSystem -Name "Upgrade OS" -UpgradePackage $osUpgPkg -EditionIndex 1

$tsNameOsd = "Default OS upgrade"
$tsUpg = Get-CMTaskSequence -Name $tsNameOsd -Fast

$tsUpg | Add-CMTaskSequenceStep -Step $step -InsertStepStartIndex 11
```



---


### Parameters
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



#### **DriverPackage**

Specify a driver package object to provide its driver content to Windows Setup during upgrade. To get this package, use the Get-CMDriverPackage (Get-CMDriverPackage.md)cmdlet.


Use the StagedContent parameter to specify the location for the driver content.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **DynamicUpdateSetting**

Use this parameter to dynamically update Windows Setup with Windows Update.


* `DisablePolicy`: Don't use Dynamic Update


* `UsingPolicy`: Enable setup to use Dynamic Update, such as search, download, and install updates.


* `OverridePolicy`: Temporarily override the local policy in real time to run Dynamic Update operations. The computer gets updates from Windows Update.



Valid Values:

* DisablePolicy
* UsingPolicy
* OverridePolicy






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[DynamicUpdateOption]`|false   |named   |False        |



#### **EditionIndex**

Specify an integer value of the OS upgrade package edition. Use this parameter with the UpgradePackage parameter.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **IgnoreMessage**

Set this parameter to `$true` to specify that Windows Setup completes the installation, ignoring any dismissible compatibility messages.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Name**

Specify a name for this step to identify it in the task sequence.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |StepName|



#### **ProductKey**

Specify the product key to apply to the upgrade process.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ScanOnly**

Set this parameter to `$true` to run the Windows Setup compatibility scan without starting upgrade.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SetupTimeout**

Specify the number of minutes before Configuration Manager fails this step. This option is useful if Windows Setup stops processing but doesn't terminate.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **SoftwareUpdate**

Starting in version 2107, specify a software update object to upgrade a client's Windows OS by using a feature update. To get this object, use the Get-CMSoftwareUpdate (Get-CMSoftwareUpdate.md)cmdlet.






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[IResultObject[]]`|false   |named   |False        |



#### **SourcePath**

Specify a local or network path to the Windows media that Windows Setup uses.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **StagedContent**

Use this parameter with DriverPackage to specify the location for the driver content. You can specify a local folder, network path, or a task sequence variable.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **UpgradePackage**

Specify an OS upgrade package object. Use the EditionIndex parameter to set the edition.


To get this object, use the Get-CMOperatingSystemInstaller (Get-CMOperatingSystemInstaller.md)cmdlet.






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
* IResultObject#SMS_TaskSequence_UpgradeOperatingSystemAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_UpgradeOperatingSystemAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_upgradeoperatingsystemaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepUpgradeOperatingSystem [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-DriverPackage <IResultObject>] [-DynamicUpdateSetting {DisablePolicy | UsingPolicy | OverridePolicy}] [-EditionIndex <Int32>] [-ForceWildcardHandling] [-IgnoreMessage <Boolean>] -Name <String> [-ProductKey <String>] [-ScanOnly <Boolean>] [-SetupTimeout <Int32>] [-SoftwareUpdate <IResultObject[]>] [-SourcePath <String>] [-StagedContent <String>] [-UpgradePackage <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

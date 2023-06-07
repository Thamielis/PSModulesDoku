New-CMTSStepRestoreUserState
----------------------------




### Synopsis
Create a Restore User State step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Restore User State step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Restore User State](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_RestoreUserState).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepRestoreUserState](Get-CMTSStepRestoreUserState)



* [Remove-CMTSStepRestoreUserState](Remove-CMTSStepRestoreUserState)



* [Set-CMTSStepRestoreUserState](Set-CMTSStepRestoreUserState)



* [About task sequence steps: Restore User State](About task sequence steps: Restore User State)





---


### Examples
#### Example 1
```PowerShell
$pkgUsmt = Get-CMPackage -Name "User State Migration Tool for Windows" -Fast

$step = New-CMTSStepRestoreUserState -Name "Restore User State" -Package $pkgUsmt -ModeOption Standard -VerboseLogging $true -ContinueOnRestore $true -RestoreLocalAccount $false

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

When you specify `-ModeOption Customize` to customize how user profiles are restored, use this parameter to specify the file names of custom XML configuration files. These files need to be in the USMT package.






|Type        |Required|Position|PipelineInput|Aliases    |
|------------|--------|--------|-------------|-----------|
|`[String[]]`|false   |named   |False        |ConfigFiles|



#### **ContinueOnError**

Add this parameter to enable the step option Continue on error . When you enable this option, if the step fails, the task sequence continues.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ContinueOnRestore**

Set this parameter to `$true` to continue restoring user state and settings even if USMT is unable to restore some files.






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



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ModeOption**

There are two modes in which USMT can operate:


* `Standard`: Restore all captured user profiles with standard options. This option is the default.


* `Customize`: Customize how user profiles are restored. If you specify this option, use the ConfigFile parameter to specify the custom XML configuration files.



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



#### **Package**

Specify an object for the USMT package. To get this object, use the Get-CMPackage (Get-CMPackage.md)cmdlet.






|Type             |Required|Position|PipelineInput|Aliases                      |
|-----------------|--------|--------|-------------|-----------------------------|
|`[IResultObject]`|true    |named   |False        |UserStateMigrationToolPackage|



#### **Password**

If you enable the RestoreLocalAccount parameter, use this parameter to assign a new password to the restored local user accounts. USMT can't migrate the original passwords. Specify a secure string for the local account password.






|Type            |Required|Position|PipelineInput|Aliases                   |
|----------------|--------|--------|-------------|--------------------------|
|`[SecureString]`|false   |named   |False        |NewPasswordForLocalAccount|



#### **RestoreLocalAccount**

Set this parameter to `$true` to restore local computer user profiles. These profiles aren't for domain users. USMT can't migrate the original passwords. To assign new passwords to the restored local user accounts, use the Password parameter.






|Type       |Required|Position|PipelineInput|Aliases                        |
|-----------|--------|--------|-------------|-------------------------------|
|`[Boolean]`|false   |named   |False        |RestoreLocalComputerUserProfile|



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
* IResultObject#SMS_TaskSequence_RestoreUserStateAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_RestoreUserStateAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_restoreuserstateaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepRestoreUserState [-Condition <IResultObject[]>] [-ConfigFile <String[]>] [-ContinueOnError] [-ContinueOnRestore <Boolean>] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-ForceWildcardHandling] [-ModeOption {Standard | Customize}] -Name <String> -Package <IResultObject> [-Password <SecureString>] [-RestoreLocalAccount <Boolean>] [-VerboseLogging <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

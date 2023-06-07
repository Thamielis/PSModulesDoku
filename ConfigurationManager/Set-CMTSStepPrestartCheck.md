Set-CMTSStepPrestartCheck
-------------------------




### Synopsis
Configure an instance of the Check Readiness task sequence step.



---


### Description

Use this cmdlet to configure an instance of the Check Readiness task sequence step.



For more information on this step, see About task sequence steps: Check Readiness (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_CheckReadiness).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepPrestartCheck](Get-CMTSStepPrestartCheck)



* [New-CMTSStepPrestartCheck](New-CMTSStepPrestartCheck)



* [Remove-CMTSStepPrestartCheck](Remove-CMTSStepPrestartCheck)



* [About task sequence steps: Check Readiness](About task sequence steps: Check Readiness)





---


### Examples
#### Example 1
```PowerShell
$tsNameOsd = "Default OS deployment"
$tsStepNameCheckReady = "Check Readiness"

Set-CMTSStepPrestartCheck -TaskSequenceName $tsNameOsd -StepName $tsStepNameCheckReady -CheckPowerState $false -CheckNetworkWired $false
```



---


### Parameters
#### **AddCondition**

Specify a condition object to add to this step. To get this object, use one of the task sequence condition cmdlets. For example, Get-CMTSStepConditionVariable (Get-CMTSStepConditionVariable.md).






|Type               |Required|Position|PipelineInput|Aliases      |
|-------------------|--------|--------|-------------|-------------|
|`[IResultObject[]]`|false   |named   |False        |AddConditions|



#### **CheckCMClientMinVersion**

Set this parameter to `$true` to enable the Minimum client version check. Use the parameter CMClientMinVersion to set the specific client version number.






|Type       |Required|Position|PipelineInput|Aliases              |
|-----------|--------|--------|-------------|---------------------|
|`[Boolean]`|false   |named   |False        |CheckClientMinVersion|



#### **CheckMaxOSVersion**

Set this parameter to `$true` to enable the Maximum OS version check. Use the parameter MaxOSVersion to set the specific OS version number.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **CheckMemory**

Set this parameter to `$true` to enable the Minimum memory (MB) check. Use the parameter Memory to set the specific memory size.






|Type       |Required|Position|PipelineInput|Aliases          |
|-----------|--------|--------|-------------|-----------------|
|`[Boolean]`|false   |named   |False        |EnableCheckMemory|



#### **CheckMinOSVersion**

Set this parameter to `$true` to enable the Minimum OS version check. Use the parameter MinOSVersion to set the specific OS version number.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **CheckOSLanguageId**

Set this parameter to `$true` to enable the check of the Language of current OS . Use the parameter OSLanguageID to set the specific language.






|Type       |Required|Position|PipelineInput|Aliases                |
|-----------|--------|--------|-------------|-----------------------|
|`[Boolean]`|false   |named   |False        |EnableCheckOSLanguageId|



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



#### **ClearCondition**

Remove a condition from this step. Use the -Condition parameter to specify the condition to remove.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[Switch]`|false   |named   |False        |ClearConditions|



#### **CMClientMinVersion**

Use this parameter to configure the specific client version. Specify the client version in the following format: `5.00.8913.1005`. Use the parameter CheckCMClientMinVersion to enable or disable the check.






|Type      |Required|Position|PipelineInput|Aliases         |
|----------|--------|--------|-------------|----------------|
|`[String]`|false   |named   |False        |ClientMinVersion|



#### **Condition**

Specify a condition object to use with this step. To get this object, use one of the task sequence condition cmdlets. For example, Get-CMTSStepConditionVariable (Get-CMTSStepConditionVariable.md).






|Type               |Required|Position|PipelineInput|Aliases                       |
|-------------------|--------|--------|-------------|------------------------------|
|`[IResultObject[]]`|false   |named   |False        |SubCondition<br/>SubConditions|



#### **ConditionVariableName**

Specify the name of the task sequence variable to use as a condition.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|false   |named   |False        |Variable|



#### **ConditionVariableValue**

Specify the value of the task sequence variable to use in a condition.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |Value  |



#### **Description**

Specify an optional description for this task sequence step.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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



#### **FileDateTimeOperator**

Specify a variable operator type for a file date/time condition.



Valid Values:

* Exists
* NotExists
* Equals
* NotEquals
* Greater
* GreaterEqual
* Less
* LessEqual
* Like
* NotLike






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[VariableOperatorType]`|false   |named   |False        |



#### **FilePath**

Specify the path for a file condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **FileTimestamp**

Specify a date/time value to use for a file condition.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **FileVersion**

Specify a version string for a file condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **FolderDateTimeOperator**

Specify a variable operator for a folder date/time condition.



Valid Values:

* Exists
* NotExists
* Equals
* NotEquals
* Greater
* GreaterEqual
* Less
* LessEqual
* Like
* NotLike






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[VariableOperatorType]`|false   |named   |False        |



#### **FolderPath**

Specify the path for a folder condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **FolderTimestamp**

Specify a date/time value to use for a folder condition.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a task sequence object from which to get the Check Readiness step. To get this object, use the Get-CMTaskSequence (Get-CMTaskSequence.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases     |
|-----------------|--------|--------|--------------|------------|
|`[IResultObject]`|true    |named   |True (ByValue)|TaskSequence|



#### **IsAnyVersion**

Use this parameter with the SetConditionSoftware parameter to match any version of the product.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **IsContinueOnError**

Use this parameter to enable the step option Continue on error . When you enable this option, if the step fails, the task sequence continues.






|Type       |Required|Position|PipelineInput|Aliases                  |
|-----------|--------|--------|-------------|-------------------------|
|`[Boolean]`|false   |named   |False        |IsThisStepContinueOnError|



#### **IsEnabled**

Use this parameter to enable this task sequence step.






|Type       |Required|Position|PipelineInput|Aliases          |
|-----------|--------|--------|-------------|-----------------|
|`[Boolean]`|false   |named   |False        |IsThisStepEnabled|



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



#### **MoveToIndex**

Move this step to the specified index position in the task sequence.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **MsiFilePath**

Specify the path to a Windows Installer file for a software condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Namespace**

Specify the namespace for a WMI query condition.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **NewStepName**

Use this parameter to rename this task sequence step.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **OperatorType**

Specify an operator to use with a task sequence variable condition.



Valid Values:

* Exists
* NotExists
* Equals
* NotEquals
* Greater
* GreaterEqual
* Less
* LessEqual
* Like
* NotLike






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[VariableOperatorType]`|false   |named   |False        |



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



#### **Query**

Specify a WMI query string to use for a condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RegistryKey**

Specify the key to use with a registry condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RegistryOperator**

Specify an operator to use with a registry condition.



Valid Values:

* Exists
* NotExists
* Equals
* NotEquals
* Greater
* GreaterEqual
* Less
* LessEqual
* Like
* NotLike






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[VariableOperatorType]`|false   |named   |False        |



#### **RegistryValueData**

Specify the value data to use with a registry condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RegistryValueName**

Specify the value name to use with a registry condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RemoveConditionFile**

Use this parameter to remove a file condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveConditionFolder**

Use this parameter to remove a folder condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveConditionIfStatement**

Use this parameter to remove an `if` statement condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveConditionOperatingSystem**

Use this parameter to remove an OS condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveConditionQueryWmi**

Use this parameter to remove a WMI query condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveConditionRegistry**

Use this parameter to remove a registry condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveConditionSoftware**

Use this parameter to remove a software condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveConditionVariable**

Use this parameter to remove a task sequence variable condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RootKey**

Specify the root key to use with a registry condition.



Valid Values:

* HKeyCurrentUser
* HKeyLocalMachine
* HKeyUsers
* HKeyCurrentConfig






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[RegistryRootKeyType]`|false   |named   |False        |



#### **SetConditionFile**

Add a new file condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **SetConditionFolder**

Add a new folder condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **SetConditionIfStatement**

Add a new `if` statement condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **SetConditionOperatingSystem**

Add a new OS condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **SetConditionQueryWmi**

Add a new WMI query condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **SetConditionRegistry**

Add a new registry condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **SetConditionSoftware**

Add a new software condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **SetConditionVariable**

Add a new task sequence variable condition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **Speed**

Use this parameter to configure the specific speed for the minimum processor speed check. Specify an integer value for the speed in MHz. Use the parameter CheckSpeed to enable or disable the check.






|Type     |Required|Position|PipelineInput|Aliases              |
|---------|--------|--------|-------------|---------------------|
|`[Int32]`|false   |named   |False        |MinimumProcessorSpeed|



#### **StatementType**

Set the type for an `if` statement condition.



Valid Values:

* All
* Any
* None






|Type                      |Required|Position|PipelineInput|Aliases |
|--------------------------|--------|--------|-------------|--------|
|`[ConditionStatementType]`|false   |named   |False        |Operator|



#### **StepName**

Specify the name of the step to select for changes.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **StepOrder**

Use this parameter to reorder the step in the task sequence.



Valid Values:

* MoveUp
* MoveDown
* MoveToIndex






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[ReorderType]`|false   |named   |False        |



#### **SupportedPlatform**

Use this parameter to specify the platforms for an OS condition.






|Type               |Required|Position|PipelineInput|Aliases           |
|-------------------|--------|--------|-------------|------------------|
|`[IResultObject[]]`|false   |named   |False        |SupportedPlatforms|



#### **TaskSequenceId**

Specify the package ID of the task sequence from which to get the Check Readiness step. This value is a standard package ID, for example `XYZ00858`.






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[String]`|true    |named   |False        |Id<br/>TaskSequencePackageId|



#### **TaskSequenceName**

Specify the name of the task sequence to target for changes.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ValueType**

Specify the type of value for a registry condition.



Valid Values:

* RegistrySZ
* RegistryExpandSZ
* RegistryDWord






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[RegistryValueType]`|false   |named   |False        |



#### **VersionOperator**

Specify an operator to use with a file condition.



Valid Values:

* Exists
* NotExists
* Equals
* NotEquals
* Greater
* GreaterEqual
* Less
* LessEqual
* Like
* NotLike






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[VariableOperatorType]`|false   |named   |False        |



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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMTSStepPrestartCheck [-AddCondition <IResultObject[]>] [-CheckCMClientMinVersion <Boolean>] [-CheckMaxOSVersion <Boolean>] [-CheckMemory <Boolean>] [-CheckMinOSVersion <Boolean>] [-CheckNetworkConnected <Boolean>] [-CheckNetworkWired <Boolean>] [-CheckOS <Boolean>] [-CheckOSArchitecture <Boolean>] [-CheckOSLanguageId <Boolean>] [-CheckPowerState <Boolean>] [-CheckSpace <Boolean>] [-CheckSpeed <Boolean>] [-CheckTpmActivated <Boolean>] [-CheckTpmEnabled <Boolean>] [-CheckUefi <Boolean>] [-ClearCondition] [-CMClientMinVersion <String>] [-Description <String>] [-DisableWildcardHandling] [-DiskSpace <Int32>] [-ForceWildcardHandling] -InputObject <IResultObject> [-IsContinueOnError <Boolean>] [-IsEnabled <Boolean>] [-MaxOSVersion <String>] [-Memory <Int32>] [-MinOSVersion <String>] [-MoveToIndex <Int32>] [-NewStepName <String>] [-OS {Client | Server}] [-OSArchitecture {Arch32 | Arch64}] [-OSLanguageId <Int32>] [-RemoveConditionFile] [-RemoveConditionFolder] [-RemoveConditionIfStatement] [-RemoveConditionOperatingSystem] [-RemoveConditionQueryWmi] [-RemoveConditionRegistry] [-RemoveConditionSoftware] [-RemoveConditionVariable] [-Speed <Int32>] [-StepName <String>] [-StepOrder {MoveUp | MoveDown | MoveToIndex}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-AddCondition <IResultObject[]>] [-CheckCMClientMinVersion <Boolean>] [-CheckMaxOSVersion <Boolean>] [-CheckMemory <Boolean>] [-CheckMinOSVersion <Boolean>] [-CheckNetworkConnected <Boolean>] [-CheckNetworkWired <Boolean>] [-CheckOS <Boolean>] [-CheckOSArchitecture <Boolean>] [-CheckOSLanguageId <Boolean>] [-CheckPowerState <Boolean>] [-CheckSpace <Boolean>] [-CheckSpeed <Boolean>] [-CheckTpmActivated <Boolean>] [-CheckTpmEnabled <Boolean>] [-CheckUefi <Boolean>] [-ClearCondition] [-CMClientMinVersion <String>] [-Description <String>] [-DisableWildcardHandling] [-DiskSpace <Int32>] [-ForceWildcardHandling] [-IsContinueOnError <Boolean>] [-IsEnabled <Boolean>] [-MaxOSVersion <String>] [-Memory <Int32>] [-MinOSVersion <String>] [-MoveToIndex <Int32>] [-NewStepName <String>] [-OS {Client | Server}] [-OSArchitecture {Arch32 | Arch64}] [-OSLanguageId <Int32>] [-RemoveConditionFile] [-RemoveConditionFolder] [-RemoveConditionIfStatement] [-RemoveConditionOperatingSystem] [-RemoveConditionQueryWmi] [-RemoveConditionRegistry] [-RemoveConditionSoftware] [-RemoveConditionVariable] [-Speed <Int32>] [-StepName <String>] [-StepOrder {MoveUp | MoveDown | MoveToIndex}] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-AddCondition <IResultObject[]>] [-CheckCMClientMinVersion <Boolean>] [-CheckMaxOSVersion <Boolean>] [-CheckMemory <Boolean>] [-CheckMinOSVersion <Boolean>] [-CheckNetworkConnected <Boolean>] [-CheckNetworkWired <Boolean>] [-CheckOS <Boolean>] [-CheckOSArchitecture <Boolean>] [-CheckOSLanguageId <Boolean>] [-CheckPowerState <Boolean>] [-CheckSpace <Boolean>] [-CheckSpeed <Boolean>] [-CheckTpmActivated <Boolean>] [-CheckTpmEnabled <Boolean>] [-CheckUefi <Boolean>] [-ClearCondition] [-CMClientMinVersion <String>] [-Description <String>] [-DisableWildcardHandling] [-DiskSpace <Int32>] [-ForceWildcardHandling] [-IsContinueOnError <Boolean>] [-IsEnabled <Boolean>] [-MaxOSVersion <String>] [-Memory <Int32>] [-MinOSVersion <String>] [-MoveToIndex <Int32>] [-NewStepName <String>] [-OS {Client | Server}] [-OSArchitecture {Arch32 | Arch64}] [-OSLanguageId <Int32>] [-RemoveConditionFile] [-RemoveConditionFolder] [-RemoveConditionIfStatement] [-RemoveConditionOperatingSystem] [-RemoveConditionQueryWmi] [-RemoveConditionRegistry] [-RemoveConditionSoftware] [-RemoveConditionVariable] [-Speed <Int32>] [-StepName <String>] [-StepOrder {MoveUp | MoveDown | MoveToIndex}] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-Condition <IResultObject[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] -SetConditionIfStatement [-StatementType {All | Any | None}] [-StepName <String>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-Condition <IResultObject[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] -SetConditionIfStatement [-StatementType {All | Any | None}] [-StepName <String>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-Condition <IResultObject[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> -SetConditionIfStatement [-StatementType {All | Any | None}] [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-ConditionVariableName <String>] [-ConditionVariableValue <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-OperatorType {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual | Like | NotLike}] -SetConditionVariable [-StepName <String>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-ConditionVariableName <String>] [-ConditionVariableValue <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-OperatorType {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual | Like | NotLike}] -SetConditionVariable [-StepName <String>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-ConditionVariableName <String>] [-ConditionVariableValue <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-OperatorType {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual | Like | NotLike}] -SetConditionVariable [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-DisableWildcardHandling] [-FileDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FilePath <String>] [-FileTimestamp <DateTime>] [-FileVersion <String>] [-ForceWildcardHandling] -SetConditionFile [-StepName <String>] -TaskSequenceId <String> [-VersionOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-DisableWildcardHandling] [-FileDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FilePath <String>] [-FileTimestamp <DateTime>] [-FileVersion <String>] [-ForceWildcardHandling] -SetConditionFile [-StepName <String>] -TaskSequenceName <String> [-VersionOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-DisableWildcardHandling] [-FileDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FilePath <String>] [-FileTimestamp <DateTime>] [-FileVersion <String>] [-ForceWildcardHandling] -InputObject <IResultObject> -SetConditionFile [-StepName <String>] [-VersionOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-DisableWildcardHandling] [-FolderDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FolderPath <String>] [-FolderTimestamp <DateTime>] [-ForceWildcardHandling] -SetConditionFolder [-StepName <String>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-DisableWildcardHandling] [-FolderDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FolderPath <String>] [-FolderTimestamp <DateTime>] [-ForceWildcardHandling] -SetConditionFolder [-StepName <String>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-DisableWildcardHandling] [-FolderDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FolderPath <String>] [-FolderTimestamp <DateTime>] [-ForceWildcardHandling] -InputObject <IResultObject> -SetConditionFolder [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Namespace <String[]>] [-Query <String>] -SetConditionQueryWmi [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> -SetConditionOperatingSystem [-StepName <String>] [-SupportedPlatform <IResultObject[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-RegistryKey <String>] [-RegistryOperator {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-RegistryValueData <String>] [-RegistryValueName <String>] [-RootKey {HKeyCurrentUser | HKeyLocalMachine | HKeyUsers | HKeyCurrentConfig}] -SetConditionRegistry [-StepName <String>] [-ValueType {RegistrySZ | RegistryExpandSZ | RegistryDWord}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-IsAnyVersion <Boolean>] [-MsiFilePath <String>] -SetConditionSoftware [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsAnyVersion <Boolean>] [-MsiFilePath <String>] -SetConditionSoftware [-StepName <String>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsAnyVersion <Boolean>] [-MsiFilePath <String>] -SetConditionSoftware [-StepName <String>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-DisableWildcardHandling] [-ForceWildcardHandling] [-Namespace <String[]>] [-Query <String>] -SetConditionQueryWmi [-StepName <String>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-DisableWildcardHandling] [-ForceWildcardHandling] [-Namespace <String[]>] [-Query <String>] -SetConditionQueryWmi [-StepName <String>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-DisableWildcardHandling] [-ForceWildcardHandling] [-RegistryKey <String>] [-RegistryOperator {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-RegistryValueData <String>] [-RegistryValueName <String>] [-RootKey {HKeyCurrentUser | HKeyLocalMachine | HKeyUsers | HKeyCurrentConfig}] -SetConditionRegistry [-StepName <String>] -TaskSequenceId <String> [-ValueType {RegistrySZ | RegistryExpandSZ | RegistryDWord}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-DisableWildcardHandling] [-ForceWildcardHandling] [-RegistryKey <String>] [-RegistryOperator {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-RegistryValueData <String>] [-RegistryValueName <String>] [-RootKey {HKeyCurrentUser | HKeyLocalMachine | HKeyUsers | HKeyCurrentConfig}] -SetConditionRegistry [-StepName <String>] -TaskSequenceName <String> [-ValueType {RegistrySZ | RegistryExpandSZ | RegistryDWord}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-DisableWildcardHandling] [-ForceWildcardHandling] -SetConditionOperatingSystem [-StepName <String>] [-SupportedPlatform <IResultObject[]>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepPrestartCheck [-DisableWildcardHandling] [-ForceWildcardHandling] -SetConditionOperatingSystem [-StepName <String>] [-SupportedPlatform <IResultObject[]>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```

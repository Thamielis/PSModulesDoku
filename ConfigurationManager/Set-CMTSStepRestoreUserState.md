Set-CMTSStepRestoreUserState
----------------------------




### Synopsis
Configure an instance of the Restore User State task sequence step.



---


### Description

Use this cmdlet to configure an instance of the Restore User State task sequence step.



For more information on this step, see About task sequence steps: Restore User State (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_RestoreUserState).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepRestoreUserState](Get-CMTSStepRestoreUserState)



* [New-CMTSStepRestoreUserState](New-CMTSStepRestoreUserState)



* [Remove-CMTSStepRestoreUserState](Remove-CMTSStepRestoreUserState)



* [About task sequence steps: Restore User State](About task sequence steps: Restore User State)





---


### Examples
#### Example 1
```PowerShell
$tsNameOsd = "Default OS deployment"
$tsStepNameRestoreState = "Restore User State"

Set-CMTSStepRestoreUserState -TaskSequenceName $tsNameOsd -StepName $tsStepNameRestoreState -ModeOption Customize -ConfigFiles "contoso.xml"
```



---


### Parameters
#### **AddCondition**

Specify a condition object to add to this step. To get this object, use one of the task sequence condition cmdlets. For example, Get-CMTSStepConditionVariable (Get-CMTSStepConditionVariable.md).






|Type               |Required|Position|PipelineInput|Aliases      |
|-------------------|--------|--------|-------------|-------------|
|`[IResultObject[]]`|false   |named   |False        |AddConditions|



#### **AddConfigFile**

When you specify `-ModeOption Customize` to customize how user profiles are restored, use this parameter to add file names of custom XML configuration files. These files need to be in the USMT package. Use this parameter to append to an existing list. To create a new list, use the ConfigFile parameter.






|Type        |Required|Position|PipelineInput|Aliases       |
|------------|--------|--------|-------------|--------------|
|`[String[]]`|false   |named   |False        |AddConfigFiles|



#### **CleanConfigFile**

Add this parameter to remove all of the file names for custom XML configuration files. To remove individual file names, use the RemoveConfigFile parameter.






|Type      |Required|Position|PipelineInput|Aliases         |
|----------|--------|--------|-------------|----------------|
|`[Switch]`|false   |named   |False        |CleanConfigFiles|



#### **ClearCondition**

Remove a condition from this step. Use the -Condition parameter to specify the condition to remove.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[Switch]`|false   |named   |False        |ClearConditions|



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



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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

Specify a task sequence object from which to get the Restore User State step. To get this object, use the Get-CMTaskSequence (Get-CMTaskSequence.md)cmdlet.






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



#### **Package**

Specify an object for the USMT package. To get this object, use the Get-CMPackage (Get-CMPackage.md)cmdlet.






|Type             |Required|Position|PipelineInput|Aliases                      |
|-----------------|--------|--------|-------------|-----------------------------|
|`[IResultObject]`|false   |named   |False        |UserStateMigrationToolPackage|



#### **Password**

If you enable the RestoreLocalAccount parameter, use this parameter to assign a new password to the restored local user accounts. USMT can't migrate the original passwords. Specify a secure string for the local account password.






|Type            |Required|Position|PipelineInput|Aliases                   |
|----------------|--------|--------|-------------|--------------------------|
|`[SecureString]`|false   |named   |False        |NewPasswordForLocalAccount|



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



#### **RemoveConfigFile**

Specify the file names of custom XML configuration files to remove from the list. To remove all configuration files, use the CleanConfigFile parameter.






|Type        |Required|Position|PipelineInput|Aliases          |
|------------|--------|--------|-------------|-----------------|
|`[String[]]`|false   |named   |False        |RemoveConfigFiles|



#### **RestoreLocalAccount**

Set this parameter to `$true` to restore local computer user profiles. These profiles aren't for domain users. USMT can't migrate the original passwords. To assign new passwords to the restored local user accounts, use the Password parameter.






|Type       |Required|Position|PipelineInput|Aliases                        |
|-----------|--------|--------|-------------|-------------------------------|
|`[Boolean]`|false   |named   |False        |RestoreLocalComputerUserProfile|



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

Specify the package ID of the task sequence from which to get the Restore User State step. This value is a standard package ID, for example `XYZ00858`.






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



#### **VerboseLogging**

Set this parameter to `$true` to enable USMT verbose logging.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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
Set-CMTSStepRestoreUserState [-AddCondition <IResultObject[]>] [-AddConfigFile <String[]>] [-CleanConfigFile] [-ClearCondition] [-ContinueOnRestore <Boolean>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-IsContinueOnError <Boolean>] [-IsEnabled <Boolean>] [-ModeOption {Standard | Customize}] [-MoveToIndex <Int32>] [-NewStepName <String>] [-Package <IResultObject>] [-Password <SecureString>] [-RemoveConditionFile] [-RemoveConditionFolder] [-RemoveConditionIfStatement] [-RemoveConditionOperatingSystem] [-RemoveConditionQueryWmi] [-RemoveConditionRegistry] [-RemoveConditionSoftware] [-RemoveConditionVariable] [-RemoveConfigFile <String[]>] [-RestoreLocalAccount <Boolean>] [-StepName <String>] [-StepOrder {MoveUp | MoveDown | MoveToIndex}] [-VerboseLogging <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-AddCondition <IResultObject[]>] [-AddConfigFile <String[]>] [-CleanConfigFile] [-ClearCondition] [-ContinueOnRestore <Boolean>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsContinueOnError <Boolean>] [-IsEnabled <Boolean>] [-ModeOption {Standard | Customize}] [-MoveToIndex <Int32>] [-NewStepName <String>] [-Package <IResultObject>] [-Password <SecureString>] [-RemoveConditionFile] [-RemoveConditionFolder] [-RemoveConditionIfStatement] [-RemoveConditionOperatingSystem] [-RemoveConditionQueryWmi] [-RemoveConditionRegistry] [-RemoveConditionSoftware] [-RemoveConditionVariable] [-RemoveConfigFile <String[]>] [-RestoreLocalAccount <Boolean>] [-StepName <String>] [-StepOrder {MoveUp | MoveDown | MoveToIndex}] -TaskSequenceId <String> [-VerboseLogging <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-AddCondition <IResultObject[]>] [-AddConfigFile <String[]>] [-CleanConfigFile] [-ClearCondition] [-ContinueOnRestore <Boolean>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsContinueOnError <Boolean>] [-IsEnabled <Boolean>] [-ModeOption {Standard | Customize}] [-MoveToIndex <Int32>] [-NewStepName <String>] [-Package <IResultObject>] [-Password <SecureString>] [-RemoveConditionFile] [-RemoveConditionFolder] [-RemoveConditionIfStatement] [-RemoveConditionOperatingSystem] [-RemoveConditionQueryWmi] [-RemoveConditionRegistry] [-RemoveConditionSoftware] [-RemoveConditionVariable] [-RemoveConfigFile <String[]>] [-RestoreLocalAccount <Boolean>] [-StepName <String>] [-StepOrder {MoveUp | MoveDown | MoveToIndex}] -TaskSequenceName <String> [-VerboseLogging <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-Condition <IResultObject[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] -SetConditionIfStatement [-StatementType {All | Any | None}] [-StepName <String>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-Condition <IResultObject[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] -SetConditionIfStatement [-StatementType {All | Any | None}] [-StepName <String>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-Condition <IResultObject[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> -SetConditionIfStatement [-StatementType {All | Any | None}] [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-ConditionVariableName <String>] [-ConditionVariableValue <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-OperatorType {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual | Like | NotLike}] -SetConditionVariable [-StepName <String>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-ConditionVariableName <String>] [-ConditionVariableValue <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-OperatorType {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual | Like | NotLike}] -SetConditionVariable [-StepName <String>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-ConditionVariableName <String>] [-ConditionVariableValue <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-OperatorType {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual | Like | NotLike}] -SetConditionVariable [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-DisableWildcardHandling] [-FileDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FilePath <String>] [-FileTimestamp <DateTime>] [-FileVersion <String>] [-ForceWildcardHandling] -SetConditionFile [-StepName <String>] -TaskSequenceId <String> [-VersionOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-DisableWildcardHandling] [-FileDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FilePath <String>] [-FileTimestamp <DateTime>] [-FileVersion <String>] [-ForceWildcardHandling] -SetConditionFile [-StepName <String>] -TaskSequenceName <String> [-VersionOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-DisableWildcardHandling] [-FileDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FilePath <String>] [-FileTimestamp <DateTime>] [-FileVersion <String>] [-ForceWildcardHandling] -InputObject <IResultObject> -SetConditionFile [-StepName <String>] [-VersionOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-DisableWildcardHandling] [-FolderDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FolderPath <String>] [-FolderTimestamp <DateTime>] [-ForceWildcardHandling] -SetConditionFolder [-StepName <String>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-DisableWildcardHandling] [-FolderDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FolderPath <String>] [-FolderTimestamp <DateTime>] [-ForceWildcardHandling] -SetConditionFolder [-StepName <String>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-DisableWildcardHandling] [-FolderDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FolderPath <String>] [-FolderTimestamp <DateTime>] [-ForceWildcardHandling] -InputObject <IResultObject> -SetConditionFolder [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Namespace <String[]>] [-Query <String>] -SetConditionQueryWmi [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> -SetConditionOperatingSystem [-StepName <String>] [-SupportedPlatform <IResultObject[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-RegistryKey <String>] [-RegistryOperator {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-RegistryValueData <String>] [-RegistryValueName <String>] [-RootKey {HKeyCurrentUser | HKeyLocalMachine | HKeyUsers | HKeyCurrentConfig}] -SetConditionRegistry [-StepName <String>] [-ValueType {RegistrySZ | RegistryExpandSZ | RegistryDWord}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-IsAnyVersion <Boolean>] [-MsiFilePath <String>] -SetConditionSoftware [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsAnyVersion <Boolean>] [-MsiFilePath <String>] -SetConditionSoftware [-StepName <String>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsAnyVersion <Boolean>] [-MsiFilePath <String>] -SetConditionSoftware [-StepName <String>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-DisableWildcardHandling] [-ForceWildcardHandling] [-Namespace <String[]>] [-Query <String>] -SetConditionQueryWmi [-StepName <String>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-DisableWildcardHandling] [-ForceWildcardHandling] [-Namespace <String[]>] [-Query <String>] -SetConditionQueryWmi [-StepName <String>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-DisableWildcardHandling] [-ForceWildcardHandling] [-RegistryKey <String>] [-RegistryOperator {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-RegistryValueData <String>] [-RegistryValueName <String>] [-RootKey {HKeyCurrentUser | HKeyLocalMachine | HKeyUsers | HKeyCurrentConfig}] -SetConditionRegistry [-StepName <String>] -TaskSequenceId <String> [-ValueType {RegistrySZ | RegistryExpandSZ | RegistryDWord}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-DisableWildcardHandling] [-ForceWildcardHandling] [-RegistryKey <String>] [-RegistryOperator {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-RegistryValueData <String>] [-RegistryValueName <String>] [-RootKey {HKeyCurrentUser | HKeyLocalMachine | HKeyUsers | HKeyCurrentConfig}] -SetConditionRegistry [-StepName <String>] -TaskSequenceName <String> [-ValueType {RegistrySZ | RegistryExpandSZ | RegistryDWord}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-DisableWildcardHandling] [-ForceWildcardHandling] -SetConditionOperatingSystem [-StepName <String>] [-SupportedPlatform <IResultObject[]>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRestoreUserState [-DisableWildcardHandling] [-ForceWildcardHandling] -SetConditionOperatingSystem [-StepName <String>] [-SupportedPlatform <IResultObject[]>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```

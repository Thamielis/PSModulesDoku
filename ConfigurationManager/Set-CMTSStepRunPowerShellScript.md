Set-CMTSStepRunPowerShellScript
-------------------------------




### Synopsis
Configure an instance of the Run PowerShell Script task sequence step.



---


### Description

Use this cmdlet to configure an instance of the Run PowerShell Script task sequence step.



For more information on this step, see About task sequence steps: Run PowerShell Script (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_RunPowerShellScript).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepRunPowerShellScript](Get-CMTSStepRunPowerShellScript)



* [New-CMTSStepRunPowerShellScript](New-CMTSStepRunPowerShellScript)



* [Remove-CMTSStepRunPowerShellScript](Remove-CMTSStepRunPowerShellScript)



* [About task sequence steps: Run PowerShell Script](About task sequence steps: Run PowerShell Script)





---


### Examples
#### Example 1
```PowerShell
$tsNameOsd = "Default OS deployment"
$tsStepNameRunPwsh = "Run PowerShell Script"

$scriptFile = "C:\Users\janed\scripts\Add-ContosoBrand.ps1"
$content = [IO.File]::ReadAllText( $scriptFile )

Set-CMTSStepRunPowerShellScript -TaskSequenceName $tsNameOsd -StepName $tsStepNameRunPwsh -SourceScript $content
```



---


### Parameters
#### **AddCondition**

Specify a condition object to add to this step. To get this object, use one of the task sequence condition cmdlets. For example, Get-CMTSStepConditionVariable (Get-CMTSStepConditionVariable.md).






|Type               |Required|Position|PipelineInput|Aliases      |
|-------------------|--------|--------|-------------|-------------|
|`[IResultObject[]]`|false   |named   |False        |AddConditions|



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



#### **ExecutionPolicy**

Specify the PowerShell execution policy for the scripts you allow to run on the computer. Choose one of the following policies:


* `AllSigned`: Only run scripts signed by a trusted publisher.


* `Undefined`: Don't define any execution policy.


* `Bypass`: Load all configuration files and run all scripts. If you download an unsigned script from the internet, PowerShell doesn't prompt for permission before running the script.



Valid Values:

* AllSigned
* Undefined
* Bypass






|Type                   |Required|Position|PipelineInput|Aliases                  |
|-----------------------|--------|--------|-------------|-------------------------|
|`[ExecutionPolicyType]`|false   |named   |False        |PowerShellExecutionPolicy|



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

Specify a task sequence object from which to get the Run PowerShell Script step. To get this object, use the Get-CMTaskSequence (Get-CMTaskSequence.md)cmdlet.






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



#### **OutputVariableName**

Specify the name of a custom task sequence variable. When you use this parameter, the step saves the last 1000 characters of the command output to the variable.






|Type      |Required|Position|PipelineInput|Aliases                  |
|----------|--------|--------|-------------|-------------------------|
|`[String]`|false   |named   |False        |Output<br/>OutputVariable|



#### **PackageId**

Specify the package ID for the package that has the PowerShell script. The package doesn't require a program. One package can contain multiple scripts.


This value is a standard package ID, for example `XYZ00821`.


Then use the ScriptName parameter to specify the name of the script.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Parameter**

Specify the parameters passed to the PowerShell script. These parameters are the same as the PowerShell script parameters on the command line. Provide parameters consumed by the script, not for the PowerShell command line.


The following example contains valid parameters:


`-MyParameter1 MyValue1 -MyParameter2 MyValue2`


The following example contains invalid parameters. The first two items are PowerShell command-line parameters ( NoLogo and ExecutionPolicy ). The script doesn't consume these parameters.


`-NoLogo -ExecutionPolicy Unrestricted -File MyScript.ps1 -MyParameter1 MyValue1 -MyParameter2 MyValue2`


If a parameter value includes a special character or a space, use single quotation marks (`'`) around the value. Using double quotation marks (`"`) may cause the task sequence step to incorrectly process the parameter.


For example: `-Arg1 '%TSVar1%' -Arg2 '%TSVar2%'`


You can also set this parameter to a task sequence variable. For example, if you specify `%MyScriptVariable%`, when the task sequence runs the script, it adds the value of this custom variable to the PowerShell command line.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|false   |named   |False        |Parameters|



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



#### **ScriptName**

Specify the name of the script to run. This script is in the package specified by the PackageId parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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



#### **SourceScript**

Instead of using the PackageId and ScriptName parameters, use this parameter to directly specify the script commands. This string value is the PowerShell commands that this step runs.


You can read the contents of an existing script file into a string variable, and then use that variable for this parameter. For example:


`$script = [IO.File]::ReadAllText( "C:\temp\script.ps1" )`






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|false   |named   |False        |SourceCode|



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



#### **SuccessCode**

Specify an array of integer values as exit codes from the script that the step should evaluate as success.






|Type       |Required|Position|PipelineInput|Aliases     |
|-----------|--------|--------|-------------|------------|
|`[Int32[]]`|false   |named   |False        |SuccessCodes|



#### **SupportedPlatform**

Use this parameter to specify the platforms for an OS condition.






|Type               |Required|Position|PipelineInput|Aliases           |
|-------------------|--------|--------|-------------|------------------|
|`[IResultObject[]]`|false   |named   |False        |SupportedPlatforms|



#### **TaskSequenceId**

Specify the package ID of the task sequence from which to get the Run PowerShell Script step. This value is a standard package ID, for example `XYZ00858`.






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[String]`|true    |named   |False        |Id<br/>TaskSequencePackageId|



#### **TaskSequenceName**

Specify the name of the task sequence to target for changes.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **TimeoutMins**

Specify an integer value that represents how long Configuration Manager allows the script to run. This value can be from `1` minute to `999` minutes. The default value is `15` minutes.


If you enter a value that doesn't allow enough time for the specified script to complete successfully, this step fails. The entire task sequence could fail depending on step or group conditions. If the timeout expires, Configuration Manager terminates the PowerShell process.






|Type     |Required|Position|PipelineInput|Aliases         |
|---------|--------|--------|-------------|----------------|
|`[Int32]`|false   |named   |False        |TimeoutInMinutes|



#### **UserName**

Use this parameter to run the script as a Windows user account and not the local system account. Specify the name of the Windows user account. To specify the account password, use the UserPassword parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **UserPassword**

Use this parameter to specify the password of the account that you specify with UserName .






|Type            |Required|Position|PipelineInput|Aliases |
|----------------|--------|--------|-------------|--------|
|`[SecureString]`|false   |named   |False        |Password|



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



#### **WorkingDirectory**

Specify the folder in which the command starts. This path can be up to 127 characters.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |StartIn|



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
Set-CMTSStepRunPowerShellScript [-AddCondition <IResultObject[]>] [-ClearCondition] [-Description <String>] [-DisableWildcardHandling] [-ExecutionPolicy {AllSigned | Undefined | Bypass}] [-ForceWildcardHandling] -InputObject <IResultObject> [-IsContinueOnError <Boolean>] [-IsEnabled <Boolean>] [-MoveToIndex <Int32>] [-NewStepName <String>] [-OutputVariableName <String>] [-PackageId <String>] [-Parameter <String>] [-RemoveConditionFile] [-RemoveConditionFolder] [-RemoveConditionIfStatement] [-RemoveConditionOperatingSystem] [-RemoveConditionQueryWmi] [-RemoveConditionRegistry] [-RemoveConditionSoftware] [-RemoveConditionVariable] [-ScriptName <String>] [-SourceScript <String>] [-StepName <String>] [-StepOrder {MoveUp | MoveDown | MoveToIndex}] [-SuccessCode <Int32[]>] [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-AddCondition <IResultObject[]>] [-ClearCondition] [-Description <String>] [-DisableWildcardHandling] [-ExecutionPolicy {AllSigned | Undefined | Bypass}] [-ForceWildcardHandling] [-IsContinueOnError <Boolean>] [-IsEnabled <Boolean>] [-MoveToIndex <Int32>] [-NewStepName <String>] [-OutputVariableName <String>] [-PackageId <String>] [-Parameter <String>] [-RemoveConditionFile] [-RemoveConditionFolder] [-RemoveConditionIfStatement] [-RemoveConditionOperatingSystem] [-RemoveConditionQueryWmi] [-RemoveConditionRegistry] [-RemoveConditionSoftware] [-RemoveConditionVariable] [-ScriptName <String>] [-SourceScript <String>] [-StepName <String>] [-StepOrder {MoveUp | MoveDown | MoveToIndex}] [-SuccessCode <Int32[]>] -TaskSequenceId <String> [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-AddCondition <IResultObject[]>] [-ClearCondition] [-Description <String>] [-DisableWildcardHandling] [-ExecutionPolicy {AllSigned | Undefined | Bypass}] [-ForceWildcardHandling] [-IsContinueOnError <Boolean>] [-IsEnabled <Boolean>] [-MoveToIndex <Int32>] [-NewStepName <String>] [-OutputVariableName <String>] [-PackageId <String>] [-Parameter <String>] [-RemoveConditionFile] [-RemoveConditionFolder] [-RemoveConditionIfStatement] [-RemoveConditionOperatingSystem] [-RemoveConditionQueryWmi] [-RemoveConditionRegistry] [-RemoveConditionSoftware] [-RemoveConditionVariable] [-ScriptName <String>] [-SourceScript <String>] [-StepName <String>] [-StepOrder {MoveUp | MoveDown | MoveToIndex}] [-SuccessCode <Int32[]>] -TaskSequenceName <String> [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-Condition <IResultObject[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] -SetConditionIfStatement [-StatementType {All | Any | None}] [-StepName <String>] -TaskSequenceId <String> [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-Condition <IResultObject[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] -SetConditionIfStatement [-StatementType {All | Any | None}] [-StepName <String>] -TaskSequenceName <String> [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-Condition <IResultObject[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> -SetConditionIfStatement [-StatementType {All | Any | None}] [-StepName <String>] [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-ConditionVariableName <String>] [-ConditionVariableValue <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-OperatorType {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual | Like | NotLike}] -SetConditionVariable [-StepName <String>] -TaskSequenceId <String> [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-ConditionVariableName <String>] [-ConditionVariableValue <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-OperatorType {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual | Like | NotLike}] -SetConditionVariable [-StepName <String>] -TaskSequenceName <String> [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-ConditionVariableName <String>] [-ConditionVariableValue <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-OperatorType {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual | Like | NotLike}] -SetConditionVariable [-StepName <String>] [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-DisableWildcardHandling] [-FileDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FilePath <String>] [-FileTimestamp <DateTime>] [-FileVersion <String>] [-ForceWildcardHandling] -SetConditionFile [-StepName <String>] -TaskSequenceId <String> [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-VersionOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-DisableWildcardHandling] [-FileDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FilePath <String>] [-FileTimestamp <DateTime>] [-FileVersion <String>] [-ForceWildcardHandling] -SetConditionFile [-StepName <String>] -TaskSequenceName <String> [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-VersionOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-DisableWildcardHandling] [-FileDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FilePath <String>] [-FileTimestamp <DateTime>] [-FileVersion <String>] [-ForceWildcardHandling] -InputObject <IResultObject> -SetConditionFile [-StepName <String>] [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-VersionOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-DisableWildcardHandling] [-FolderDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FolderPath <String>] [-FolderTimestamp <DateTime>] [-ForceWildcardHandling] -SetConditionFolder [-StepName <String>] -TaskSequenceId <String> [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-DisableWildcardHandling] [-FolderDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FolderPath <String>] [-FolderTimestamp <DateTime>] [-ForceWildcardHandling] -SetConditionFolder [-StepName <String>] -TaskSequenceName <String> [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-DisableWildcardHandling] [-FolderDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FolderPath <String>] [-FolderTimestamp <DateTime>] [-ForceWildcardHandling] -InputObject <IResultObject> -SetConditionFolder [-StepName <String>] [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Namespace <String[]>] [-Query <String>] -SetConditionQueryWmi [-StepName <String>] [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> -SetConditionOperatingSystem [-StepName <String>] [-SupportedPlatform <IResultObject[]>] [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-RegistryKey <String>] [-RegistryOperator {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-RegistryValueData <String>] [-RegistryValueName <String>] [-RootKey {HKeyCurrentUser | HKeyLocalMachine | HKeyUsers | HKeyCurrentConfig}] -SetConditionRegistry [-StepName <String>] [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-ValueType {RegistrySZ | RegistryExpandSZ | RegistryDWord}] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-IsAnyVersion <Boolean>] [-MsiFilePath <String>] -SetConditionSoftware [-StepName <String>] [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsAnyVersion <Boolean>] [-MsiFilePath <String>] -SetConditionSoftware [-StepName <String>] -TaskSequenceId <String> [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsAnyVersion <Boolean>] [-MsiFilePath <String>] -SetConditionSoftware [-StepName <String>] -TaskSequenceName <String> [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-DisableWildcardHandling] [-ForceWildcardHandling] [-Namespace <String[]>] [-Query <String>] -SetConditionQueryWmi [-StepName <String>] -TaskSequenceId <String> [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-DisableWildcardHandling] [-ForceWildcardHandling] [-Namespace <String[]>] [-Query <String>] -SetConditionQueryWmi [-StepName <String>] -TaskSequenceName <String> [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-DisableWildcardHandling] [-ForceWildcardHandling] [-RegistryKey <String>] [-RegistryOperator {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-RegistryValueData <String>] [-RegistryValueName <String>] [-RootKey {HKeyCurrentUser | HKeyLocalMachine | HKeyUsers | HKeyCurrentConfig}] -SetConditionRegistry [-StepName <String>] -TaskSequenceId <String> [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-ValueType {RegistrySZ | RegistryExpandSZ | RegistryDWord}] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-DisableWildcardHandling] [-ForceWildcardHandling] [-RegistryKey <String>] [-RegistryOperator {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-RegistryValueData <String>] [-RegistryValueName <String>] [-RootKey {HKeyCurrentUser | HKeyLocalMachine | HKeyUsers | HKeyCurrentConfig}] -SetConditionRegistry [-StepName <String>] -TaskSequenceName <String> [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-ValueType {RegistrySZ | RegistryExpandSZ | RegistryDWord}] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-DisableWildcardHandling] [-ForceWildcardHandling] -SetConditionOperatingSystem [-StepName <String>] [-SupportedPlatform <IResultObject[]>] -TaskSequenceId <String> [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepRunPowerShellScript [-DisableWildcardHandling] [-ForceWildcardHandling] -SetConditionOperatingSystem [-StepName <String>] [-SupportedPlatform <IResultObject[]>] -TaskSequenceName <String> [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

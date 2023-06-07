Set-CMTaskSequenceGroup
-----------------------




### Synopsis
Sets a Configuration Manager task sequence group.



---


### Description

The Set-CMTaskSequenceGroup cmdlet sets properties, options, specific conditions and steps of task sequence group(s) in a task sequence. The cmdlet supports pipeline from a task sequence object, and could be filtered by the name of the group.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMTaskSequenceGroup](New-CMTaskSequenceGroup)



* [Get-CMTaskSequenceGroup](Get-CMTaskSequenceGroup)



* [Remove-CMTaskSequenceGroup](Remove-CMTaskSequenceGroup)





---


### Examples
#### Example 1
```PowerShell
PS XYZ:\>$ReferencedTaskSequence | Set-CMTaskSequenceGroup -StepName $gpName -NewStepName $gpName2 -Description $gpNewDescription -IsContinueOnError $false -IsEnabled $false -ClearStep -AddStep $st1 -ClearCondition -AddCondition $cd1
```

#### Example 2
```PowerShell
$ReferencedTaskSequence | Set-CMTaskSequenceGroup -StepName $gpName2 -SetConditionIfStatement -StatementType None -Condition $cd1
```

#### Example 3
```PowerShell
$ReferencedTaskSequence | Set-CMTaskSequenceGroup -StepName $gpName2 -AddStep $st1 -InsertStepStartIndex $index
```

#### Example 4
```PowerShell
$ReferencedTaskSequence | Set-CMTaskSequenceGroup -StepName $gpName2 -StepOrder MoveToIndex -MoveToIndex $index
```



---


### Parameters
#### **AddCondition**

Specifies the condition objects to be added.






|Type               |Required|Position|PipelineInput|Aliases      |
|-------------------|--------|--------|-------------|-------------|
|`[IResultObject[]]`|false   |named   |False        |AddConditions|



#### **AddStep**

Specifies the steps to be added.






|Type               |Required|Position|PipelineInput|Aliases |
|-------------------|--------|--------|-------------|--------|
|`[IResultObject[]]`|false   |named   |False        |AddSteps|



#### **CleanStep**

Clean step by value/ID/name.






|Type      |Required|Position|PipelineInput|Aliases                                |
|----------|--------|--------|-------------|---------------------------------------|
|`[Switch]`|false   |named   |False        |ClearSteps<br/>ClearStep<br/>CleanSteps|



#### **ClearCondition**

Clear condition by value/ID/Name.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[Switch]`|false   |named   |False        |ClearConditions|



#### **Condition**

Specifies conditions.






|Type               |Required|Position|PipelineInput|Aliases                       |
|-------------------|--------|--------|-------------|------------------------------|
|`[IResultObject[]]`|false   |named   |False        |SubCondition<br/>SubConditions|



#### **ConditionVariableName**

Specifies a condition variable name.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|false   |named   |False        |Variable|



#### **ConditionVariableValue**

Specifies a condition variable value.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |Value  |



#### **Description**

Specifies a description.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FileDateTimeOperator**

Specifies a file date time operator.



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

Specifies a file path.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **FileTimestamp**

Specifies a file time stamp.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **FileVersion**

Specifies a file version.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **FolderDateTimeOperator**

Specifies a folder date time operator.



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

Specifies a folder path.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **FolderTimestamp**

Specifies a folder time stamp.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies a task sequence object.






|Type             |Required|Position|PipelineInput |Aliases     |
|-----------------|--------|--------|--------------|------------|
|`[IResultObject]`|true    |named   |True (ByValue)|TaskSequence|



#### **InsertStepStartIndex**

Specifies an insert step start index.






|Type     |Required|Position|PipelineInput|Aliases              |
|---------|--------|--------|-------------|---------------------|
|`[Int32]`|false   |named   |False        |InsertStepsStartIndex|



#### **IsAnyVersion**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **IsContinueOnError**

Indicates whether to continue when there is an error.






|Type       |Required|Position|PipelineInput|Aliases                  |
|-----------|--------|--------|-------------|-------------------------|
|`[Boolean]`|false   |named   |False        |IsThisStepContinueOnError|



#### **IsEnabled**

Indicates whether the step is enabled.






|Type       |Required|Position|PipelineInput|Aliases          |
|-----------|--------|--------|-------------|-----------------|
|`[Boolean]`|false   |named   |False        |IsThisStepEnabled|



#### **MoveToIndex**

Specifies an index to move to.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **MsiFilePath**

Specifies an MSI file path.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Namespace**

Specifies namespaces.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **NewStepName**

Specifies a new step name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **OperatorType**

Specifies an operation type.



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



#### **Query**

Specifies a query.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RegistryKey**

Specifies a registry key.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RegistryOperator**

Specifies a registry operator.



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

Specifies registry value data.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RegistryValueName**

Specifies a registry value name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RemoveConditionFile**

Remove condition file by value/ID/name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveConditionFolder**

Remove condition folder by value/ID/name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveConditionIfStatement**

Remove condition IF statement by value/ID/name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveConditionOperatingSystem**

Remove condition operating system by value/ID/name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveConditionQueryWmi**

Remove condition query WMI by value/ID/name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveConditionRegistry**

Remove condition registry by value/ID/name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveConditionSoftware**

Remove condition software by value/ID/name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveConditionVariable**

Remove condition variable by value/ID/name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RootKey**

Specify a root key.



Valid Values:

* HKeyCurrentUser
* HKeyLocalMachine
* HKeyUsers
* HKeyCurrentConfig






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[RegistryRootKeyType]`|false   |named   |False        |



#### **SetConditionFile**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **SetConditionFolder**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **SetConditionIfStatement**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **SetConditionOperatingSystem**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **SetConditionQueryWmi**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **SetConditionRegistry**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **SetConditionSoftware**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **SetConditionVariable**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **StatementType**





Valid Values:

* All
* Any
* None






|Type                      |Required|Position|PipelineInput|Aliases |
|--------------------------|--------|--------|-------------|--------|
|`[ConditionStatementType]`|false   |named   |False        |Operator|



#### **StepName**

Specifies a step name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **StepOrder**

Specifies a step order.



Valid Values:

* MoveUp
* MoveDown
* MoveToIndex






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[ReorderType]`|false   |named   |False        |



#### **SupportedPlatform**

Specifies supported platforms.






|Type               |Required|Position|PipelineInput|Aliases           |
|-------------------|--------|--------|-------------|------------------|
|`[IResultObject[]]`|false   |named   |False        |SupportedPlatforms|



#### **TaskSequenceId**

Specifies a task sequence ID.






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[String]`|true    |named   |False        |Id<br/>TaskSequencePackageId|



#### **TaskSequenceName**

Specifies a task sequence name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ValueType**

Specifies a value type.



Valid Values:

* RegistrySZ
* RegistryExpandSZ
* RegistryDWord






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[RegistryValueType]`|false   |named   |False        |



#### **VersionOperator**

Specifies a version operator.



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
Set-CMTaskSequenceGroup [-AddCondition <IResultObject[]>] [-AddStep <IResultObject[]>] [-CleanStep] [-ClearCondition] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-InsertStepStartIndex <Int32>] [-IsContinueOnError <Boolean>] [-IsEnabled <Boolean>] [-MoveToIndex <Int32>] [-NewStepName <String>] [-RemoveConditionFile] [-RemoveConditionFolder] [-RemoveConditionIfStatement] [-RemoveConditionOperatingSystem] [-RemoveConditionQueryWmi] [-RemoveConditionRegistry] [-RemoveConditionSoftware] [-RemoveConditionVariable] [-StepName <String>] [-StepOrder {MoveUp | MoveDown | MoveToIndex}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-AddCondition <IResultObject[]>] [-AddStep <IResultObject[]>] [-CleanStep] [-ClearCondition] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-InsertStepStartIndex <Int32>] [-IsContinueOnError <Boolean>] [-IsEnabled <Boolean>] [-MoveToIndex <Int32>] [-NewStepName <String>] [-RemoveConditionFile] [-RemoveConditionFolder] [-RemoveConditionIfStatement] [-RemoveConditionOperatingSystem] [-RemoveConditionQueryWmi] [-RemoveConditionRegistry] [-RemoveConditionSoftware] [-RemoveConditionVariable] [-StepName <String>] [-StepOrder {MoveUp | MoveDown | MoveToIndex}] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-AddCondition <IResultObject[]>] [-AddStep <IResultObject[]>] [-CleanStep] [-ClearCondition] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-InsertStepStartIndex <Int32>] [-IsContinueOnError <Boolean>] [-IsEnabled <Boolean>] [-MoveToIndex <Int32>] [-NewStepName <String>] [-RemoveConditionFile] [-RemoveConditionFolder] [-RemoveConditionIfStatement] [-RemoveConditionOperatingSystem] [-RemoveConditionQueryWmi] [-RemoveConditionRegistry] [-RemoveConditionSoftware] [-RemoveConditionVariable] [-StepName <String>] [-StepOrder {MoveUp | MoveDown | MoveToIndex}] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-Condition <IResultObject[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] -SetConditionIfStatement [-StatementType {All | Any | None}] [-StepName <String>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-Condition <IResultObject[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] -SetConditionIfStatement [-StatementType {All | Any | None}] [-StepName <String>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-Condition <IResultObject[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> -SetConditionIfStatement [-StatementType {All | Any | None}] [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-ConditionVariableName <String>] [-ConditionVariableValue <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-OperatorType {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual | Like | NotLike}] -SetConditionVariable [-StepName <String>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-ConditionVariableName <String>] [-ConditionVariableValue <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-OperatorType {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual | Like | NotLike}] -SetConditionVariable [-StepName <String>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-ConditionVariableName <String>] [-ConditionVariableValue <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-OperatorType {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual | Like | NotLike}] -SetConditionVariable [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-DisableWildcardHandling] [-FileDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FilePath <String>] [-FileTimestamp <DateTime>] [-FileVersion <String>] [-ForceWildcardHandling] -SetConditionFile [-StepName <String>] -TaskSequenceId <String> [-VersionOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-DisableWildcardHandling] [-FileDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FilePath <String>] [-FileTimestamp <DateTime>] [-FileVersion <String>] [-ForceWildcardHandling] -SetConditionFile [-StepName <String>] -TaskSequenceName <String> [-VersionOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-DisableWildcardHandling] [-FileDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FilePath <String>] [-FileTimestamp <DateTime>] [-FileVersion <String>] [-ForceWildcardHandling] -InputObject <IResultObject> -SetConditionFile [-StepName <String>] [-VersionOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-DisableWildcardHandling] [-FolderDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FolderPath <String>] [-FolderTimestamp <DateTime>] [-ForceWildcardHandling] -SetConditionFolder [-StepName <String>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-DisableWildcardHandling] [-FolderDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FolderPath <String>] [-FolderTimestamp <DateTime>] [-ForceWildcardHandling] -SetConditionFolder [-StepName <String>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-DisableWildcardHandling] [-FolderDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FolderPath <String>] [-FolderTimestamp <DateTime>] [-ForceWildcardHandling] -InputObject <IResultObject> -SetConditionFolder [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Namespace <String[]>] [-Query <String>] -SetConditionQueryWmi [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> -SetConditionOperatingSystem [-StepName <String>] [-SupportedPlatform <IResultObject[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-RegistryKey <String>] [-RegistryOperator {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-RegistryValueData <String>] [-RegistryValueName <String>] [-RootKey {HKeyCurrentUser | HKeyLocalMachine | HKeyUsers | HKeyCurrentConfig}] -SetConditionRegistry [-StepName <String>] [-ValueType {RegistrySZ | RegistryExpandSZ | RegistryDWord}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-IsAnyVersion <Boolean>] [-MsiFilePath <String>] -SetConditionSoftware [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsAnyVersion <Boolean>] [-MsiFilePath <String>] -SetConditionSoftware [-StepName <String>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsAnyVersion <Boolean>] [-MsiFilePath <String>] -SetConditionSoftware [-StepName <String>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-DisableWildcardHandling] [-ForceWildcardHandling] [-Namespace <String[]>] [-Query <String>] -SetConditionQueryWmi [-StepName <String>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-DisableWildcardHandling] [-ForceWildcardHandling] [-Namespace <String[]>] [-Query <String>] -SetConditionQueryWmi [-StepName <String>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-DisableWildcardHandling] [-ForceWildcardHandling] [-RegistryKey <String>] [-RegistryOperator {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-RegistryValueData <String>] [-RegistryValueName <String>] [-RootKey {HKeyCurrentUser | HKeyLocalMachine | HKeyUsers | HKeyCurrentConfig}] -SetConditionRegistry [-StepName <String>] -TaskSequenceId <String> [-ValueType {RegistrySZ | RegistryExpandSZ | RegistryDWord}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-DisableWildcardHandling] [-ForceWildcardHandling] [-RegistryKey <String>] [-RegistryOperator {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-RegistryValueData <String>] [-RegistryValueName <String>] [-RootKey {HKeyCurrentUser | HKeyLocalMachine | HKeyUsers | HKeyCurrentConfig}] -SetConditionRegistry [-StepName <String>] -TaskSequenceName <String> [-ValueType {RegistrySZ | RegistryExpandSZ | RegistryDWord}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -SetConditionOperatingSystem [-StepName <String>] [-SupportedPlatform <IResultObject[]>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -SetConditionOperatingSystem [-StepName <String>] [-SupportedPlatform <IResultObject[]>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```

Set-CMTSStepApplyOperatingSystem
--------------------------------




### Synopsis
Configure an instance of the Apply OS Image task sequence step.



---


### Description

Use this cmdlet to configure an instance of the Apply OS Image task sequence step.



For more information on this step, see About task sequence steps: Apply OS Image (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ApplyOperatingSystemImage).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepApplyOperatingSystem](Get-CMTSStepApplyOperatingSystem)



* [New-CMTSStepApplyOperatingSystem](New-CMTSStepApplyOperatingSystem)



* [Remove-CMTSStepApplyOperatingSystem](Remove-CMTSStepApplyOperatingSystem)



* [About task sequence steps: Apply OS Image](About task sequence steps: Apply OS Image)





---


### Examples
#### Example 1
```PowerShell
$tsNameOsd = "Default OS deployment"
$tsStepNameApplyOsImage = "Apply OS image"

Set-CMTSStepApplyOperatingSystem -TaskSequenceName $tsNameOsd -StepName $tsStepNameApplyOsImage -Destination SpecificDiskAndPartition -DestinationDisk 5 -DestinationPartition 50
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



#### **ConfigFileName**

Specify the file name of an unattended or Sysprep answer file to use for a custom installation. Use this parameter with the ConfigFilePackage parameter.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|false   |named   |False        |AnswerFileName|



#### **ConfigFilePackage**

Specify a package object that includes the unattended or Sysprep answer file to use for a custom installation. To get this object, use the Get-CMPackage (Get-CMPackage.md)cmdlet. Use this parameter with the ConfigFileName parameter.






|Type             |Required|Position|PipelineInput|Aliases          |
|-----------------|--------|--------|-------------|-----------------|
|`[IResultObject]`|false   |named   |False        |AnswerFilePackage|



#### **Description**

Specify an optional description for this task sequence step.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Destination**

Specify the location where you want to apply this OS. If you don't specify this parameter, the default is `NextAvailableFormattedPartition`.


* `NextAvailableFormattedPartition`: Use the next sequential partition not already targeted by an Apply Operating System or Apply Data Image step in this task sequence.


* `SpecificDiskAndPartition`: Specify the disk number with the DestinationDisk parameter and the partition number with the DestinationPartition parameter.


* `SpecificLogicalDriverLetter`: Use the DestinationDriveLetter parameter to specify the logical drive letter assigned to the partition by Windows PE. This drive letter can be different from the drive letter assigned by the newly deployed OS.


* `LogicalDriverLetterInVariable`: Use the DestinationVariable parameter to specify the task sequence variable containing the drive letter assigned to the partition by Windows PE. This variable is typically set with the DiskNumberVariable parameter of the Set-CMTSStepPartitionDisk (Set-CMTSStepPartitionDisk.md) or [New-CMTSStepPartitionDisk](New-CMTSStepPartitionDisk.md)cmdlets for the Format and Partition Disk task sequence step.



Valid Values:

* NextAvailableFormattedPartition
* SpecificDiskAndPartition
* SpecificLogicalDriverLetter
* LogicalDriverLetterInVariable






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[DestinationType]`|false   |named   |False        |



#### **DestinationDisk**

When you use `-Destination SpecificDiskAndPartition`, use this parameter to specify the disk number. Specify an integer from `0` to `99`. Also use the DestinationPartition parameter.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **DestinationDriveLetter**

When you use `-Destination SpecificLogicalDriverLetter`, use this parameter to specify the logical drive letter. Specify a drive letter from `C` to `Z`.






|Type      |Required|Position|PipelineInput|Aliases                |
|----------|--------|--------|-------------|-----------------------|
|`[String]`|false   |named   |False        |DestinationLogicalDrive|



#### **DestinationPartition**

When you use `-Destination SpecificDiskAndPartition`, use this parameter to specify the partition number. Specify an integer from `1` to `99`. Also use the DestinationDisk parameter.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **DestinationVariable**

When you use `-Destination LogicalDriverLetterInVariable`, use this parameter to specify the task sequence variable with the logical drive letter. The variable name needs to alphanumeric without spaces and fewer than 256 characters.






|Type      |Required|Position|PipelineInput|Aliases                |
|----------|--------|--------|-------------|-----------------------|
|`[String]`|false   |named   |False        |DestinationVariableName|



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



#### **ImagePackage**

Specify an OS image package object. The step applies the OS from this image. Use the ImagePackageIndex parameter to set the image index.


To get this object, use the Get-CMOperatingSystemImage (Get-CMOperatingSystemImage.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **ImagePackageIndex**

Specify an integer value of the image index. Use this parameter with the ImagePackage parameter.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **InputObject**

Specify a task sequence object that has the Apply OS Image step to configure. To get this object, use the Get-CMTaskSequence (Get-CMTaskSequence.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases     |
|-----------------|--------|--------|--------------|------------|
|`[IResultObject]`|true    |named   |True (ByValue)|TaskSequence|



#### **InstallPackage**

Specify an OS upgrade package object. The step applies the OS from this original installation source. Use the InstallPackageIndex parameter to set the edition.


To get this object, use the Get-CMOperatingSystemInstaller (Get-CMOperatingSystemInstaller.md)cmdlet.






|Type             |Required|Position|PipelineInput|Aliases       |
|-----------------|--------|--------|-------------|--------------|
|`[IResultObject]`|false   |named   |False        |UpgradePackage|



#### **InstallPackageIndex**

Specify an integer value of the OS upgrade package edition. Use this parameter with the InstallPackage parameter.






|Type     |Required|Position|PipelineInput|Aliases            |
|---------|--------|--------|-------------|-------------------|
|`[Int32]`|false   |named   |False        |UpgradePackageIndex|



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



#### **LayeredDriver**

Starting in version 2107, use this parameter to select other types of keyboards that are common with Japanese and Korean languages. Specify an integer value for the layered driver to install with Windows. Use the same values as the OsdLayeredDriver (/mem/configmgr/osd/understand/task-sequence-variables#OsdLayeredDriver)task sequence variable.



Valid Values:

* DoNotSpecify
* Driver1
* Driver2
* Driver3
* Driver4
* Driver5
* Driver6






|Type                |Required|Position|PipelineInput|Aliases       |
|--------------------|--------|--------|-------------|--------------|
|`[OsdLayeredDriver]`|false   |named   |False        |KeyboardDriver|



#### **MoveToIndex**

Move this step to the specified index position in the task sequence.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **MsiFilePath**

Use this parameter with the SetConditionSoftware parameter to specify the path to a Windows Installer file.






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



#### **RunFromNet**

Set this parameter to `$true` to allow the task sequence to apply the OS image directly from the distribution point.


For greatest security, it's recommended to not enable this setting. This option is designed for use on devices with limited storage capacity. For more information, see Access content directly from the distribution point (/mem/configmgr/osd/understand/task-sequence-steps#access-content-directly-from-the-distribution-point).






|Type       |Required|Position|PipelineInput|Aliases                         |
|-----------|--------|--------|-------------|--------------------------------|
|`[Boolean]`|false   |named   |False        |AllowAccessFromDistributionPoint|



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

Specify the package ID of the task sequence with the Apply OS Image step to configure. This value is a standard package ID, for example `XYZ00858`.






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[String]`|true    |named   |False        |Id<br/>TaskSequencePackageId|



#### **TaskSequenceName**

Specify the name of the task sequence with the Apply OS Image step to configure.






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
Set-CMTSStepApplyOperatingSystem [-AddCondition <IResultObject[]>] [-ClearCondition] [-ConfigFileName <String>] [-ConfigFilePackage <IResultObject>] [-Description <String>] [-Destination {NextAvailableFormattedPartition | SpecificDiskAndPartition | SpecificLogicalDriverLetter | LogicalDriverLetterInVariable}] [-DestinationDisk <Int32>] [-DestinationDriveLetter <String>] [-DestinationPartition <Int32>] [-DestinationVariable <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-ImagePackage <IResultObject>] [-ImagePackageIndex <Int32>] -InputObject <IResultObject> [-InstallPackage <IResultObject>] [-InstallPackageIndex <Int32>] [-IsContinueOnError <Boolean>] [-IsEnabled <Boolean>] [-LayeredDriver {DoNotSpecify | Driver1 | Driver2 | Driver3 | Driver4 | Driver5 | Driver6}] [-MoveToIndex <Int32>] [-NewStepName <String>] [-RemoveConditionFile] [-RemoveConditionFolder] [-RemoveConditionIfStatement] [-RemoveConditionOperatingSystem] [-RemoveConditionQueryWmi] [-RemoveConditionRegistry] [-RemoveConditionSoftware] [-RemoveConditionVariable] [-RunFromNet <Boolean>] [-StepName <String>] [-StepOrder {MoveUp | MoveDown | MoveToIndex}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-AddCondition <IResultObject[]>] [-ClearCondition] [-ConfigFileName <String>] [-ConfigFilePackage <IResultObject>] [-Description <String>] [-Destination {NextAvailableFormattedPartition | SpecificDiskAndPartition | SpecificLogicalDriverLetter | LogicalDriverLetterInVariable}] [-DestinationDisk <Int32>] [-DestinationDriveLetter <String>] [-DestinationPartition <Int32>] [-DestinationVariable <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-ImagePackage <IResultObject>] [-ImagePackageIndex <Int32>] [-InstallPackage <IResultObject>] [-InstallPackageIndex <Int32>] [-IsContinueOnError <Boolean>] [-IsEnabled <Boolean>] [-LayeredDriver {DoNotSpecify | Driver1 | Driver2 | Driver3 | Driver4 | Driver5 | Driver6}] [-MoveToIndex <Int32>] [-NewStepName <String>] [-RemoveConditionFile] [-RemoveConditionFolder] [-RemoveConditionIfStatement] [-RemoveConditionOperatingSystem] [-RemoveConditionQueryWmi] [-RemoveConditionRegistry] [-RemoveConditionSoftware] [-RemoveConditionVariable] [-RunFromNet <Boolean>] [-StepName <String>] [-StepOrder {MoveUp | MoveDown | MoveToIndex}] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-AddCondition <IResultObject[]>] [-ClearCondition] [-ConfigFileName <String>] [-ConfigFilePackage <IResultObject>] [-Description <String>] [-Destination {NextAvailableFormattedPartition | SpecificDiskAndPartition | SpecificLogicalDriverLetter | LogicalDriverLetterInVariable}] [-DestinationDisk <Int32>] [-DestinationDriveLetter <String>] [-DestinationPartition <Int32>] [-DestinationVariable <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-ImagePackage <IResultObject>] [-ImagePackageIndex <Int32>] [-InstallPackage <IResultObject>] [-InstallPackageIndex <Int32>] [-IsContinueOnError <Boolean>] [-IsEnabled <Boolean>] [-LayeredDriver {DoNotSpecify | Driver1 | Driver2 | Driver3 | Driver4 | Driver5 | Driver6}] [-MoveToIndex <Int32>] [-NewStepName <String>] [-RemoveConditionFile] [-RemoveConditionFolder] [-RemoveConditionIfStatement] [-RemoveConditionOperatingSystem] [-RemoveConditionQueryWmi] [-RemoveConditionRegistry] [-RemoveConditionSoftware] [-RemoveConditionVariable] [-RunFromNet <Boolean>] [-StepName <String>] [-StepOrder {MoveUp | MoveDown | MoveToIndex}] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-Condition <IResultObject[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] -SetConditionIfStatement [-StatementType {All | Any | None}] [-StepName <String>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-Condition <IResultObject[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] -SetConditionIfStatement [-StatementType {All | Any | None}] [-StepName <String>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-Condition <IResultObject[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> -SetConditionIfStatement [-StatementType {All | Any | None}] [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-ConditionVariableName <String>] [-ConditionVariableValue <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-OperatorType {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual | Like | NotLike}] -SetConditionVariable [-StepName <String>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-ConditionVariableName <String>] [-ConditionVariableValue <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-OperatorType {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual | Like | NotLike}] -SetConditionVariable [-StepName <String>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-ConditionVariableName <String>] [-ConditionVariableValue <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-OperatorType {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual | Like | NotLike}] -SetConditionVariable [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-DisableWildcardHandling] [-FileDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FilePath <String>] [-FileTimestamp <DateTime>] [-FileVersion <String>] [-ForceWildcardHandling] -SetConditionFile [-StepName <String>] -TaskSequenceId <String> [-VersionOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-DisableWildcardHandling] [-FileDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FilePath <String>] [-FileTimestamp <DateTime>] [-FileVersion <String>] [-ForceWildcardHandling] -SetConditionFile [-StepName <String>] -TaskSequenceName <String> [-VersionOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-DisableWildcardHandling] [-FileDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FilePath <String>] [-FileTimestamp <DateTime>] [-FileVersion <String>] [-ForceWildcardHandling] -InputObject <IResultObject> -SetConditionFile [-StepName <String>] [-VersionOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-DisableWildcardHandling] [-FolderDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FolderPath <String>] [-FolderTimestamp <DateTime>] [-ForceWildcardHandling] -SetConditionFolder [-StepName <String>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-DisableWildcardHandling] [-FolderDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FolderPath <String>] [-FolderTimestamp <DateTime>] [-ForceWildcardHandling] -SetConditionFolder [-StepName <String>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-DisableWildcardHandling] [-FolderDateTimeOperator {Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-FolderPath <String>] [-FolderTimestamp <DateTime>] [-ForceWildcardHandling] -InputObject <IResultObject> -SetConditionFolder [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Namespace <String[]>] [-Query <String>] -SetConditionQueryWmi [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> -SetConditionOperatingSystem [-StepName <String>] [-SupportedPlatform <IResultObject[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-RegistryKey <String>] [-RegistryOperator {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-RegistryValueData <String>] [-RegistryValueName <String>] [-RootKey {HKeyCurrentUser | HKeyLocalMachine | HKeyUsers | HKeyCurrentConfig}] -SetConditionRegistry [-StepName <String>] [-ValueType {RegistrySZ | RegistryExpandSZ | RegistryDWord}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-IsAnyVersion <Boolean>] [-MsiFilePath <String>] -SetConditionSoftware [-StepName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsAnyVersion <Boolean>] [-MsiFilePath <String>] -SetConditionSoftware [-StepName <String>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsAnyVersion <Boolean>] [-MsiFilePath <String>] -SetConditionSoftware [-StepName <String>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-DisableWildcardHandling] [-ForceWildcardHandling] [-Namespace <String[]>] [-Query <String>] -SetConditionQueryWmi [-StepName <String>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-DisableWildcardHandling] [-ForceWildcardHandling] [-Namespace <String[]>] [-Query <String>] -SetConditionQueryWmi [-StepName <String>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-DisableWildcardHandling] [-ForceWildcardHandling] [-RegistryKey <String>] [-RegistryOperator {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-RegistryValueData <String>] [-RegistryValueName <String>] [-RootKey {HKeyCurrentUser | HKeyLocalMachine | HKeyUsers | HKeyCurrentConfig}] -SetConditionRegistry [-StepName <String>] -TaskSequenceId <String> [-ValueType {RegistrySZ | RegistryExpandSZ | RegistryDWord}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-DisableWildcardHandling] [-ForceWildcardHandling] [-RegistryKey <String>] [-RegistryOperator {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual}] [-RegistryValueData <String>] [-RegistryValueName <String>] [-RootKey {HKeyCurrentUser | HKeyLocalMachine | HKeyUsers | HKeyCurrentConfig}] -SetConditionRegistry [-StepName <String>] -TaskSequenceName <String> [-ValueType {RegistrySZ | RegistryExpandSZ | RegistryDWord}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-DisableWildcardHandling] [-ForceWildcardHandling] -SetConditionOperatingSystem [-StepName <String>] [-SupportedPlatform <IResultObject[]>] -TaskSequenceId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTSStepApplyOperatingSystem [-DisableWildcardHandling] [-ForceWildcardHandling] -SetConditionOperatingSystem [-StepName <String>] [-SupportedPlatform <IResultObject[]>] -TaskSequenceName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```

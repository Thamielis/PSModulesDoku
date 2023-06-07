Set-CMTaskSequence
------------------




### Synopsis
Sets a Configuration Manager task sequence.



---


### Description

The Set-CMTaskSequence cmdlet modifies a Configuration Manager task sequence.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMTaskSequence](New-CMTaskSequence)



* [Get-CMTaskSequence](Get-CMTaskSequence)



* [Copy-CMTaskSequence](Copy-CMTaskSequence)



* [Import-CMTaskSequence](Import-CMTaskSequence)



* [Export-CMTaskSequence](Export-CMTaskSequence)



* [Remove-CMTaskSequence](Remove-CMTaskSequence)



* [Get-CMSupportedPlatform](Get-CMSupportedPlatform)





---


### Examples
#### Example 1: Get a task sequence and change its name
```PowerShell
PS XYZ:\> $TaskSequence = Get-CMTaskSequence -Name "TaskSequence01"
PS XYZ:\> Set-CMTaskSequence -InputObject $TaskSequence -NewName "NewTS01"
```
The first command gets the task sequence object named TaskSequence01 and stores the object in the $TaskSequence variable.


The second command changes the name of the task sequence stored in $TaskSequence to NewTS01.
#### Example 2: Pass a task sequence and change its name
```PowerShell
PS XYZ:\> Get-CMTaskSequence -Name "TaskSequence02" | Set-CMTaskSequence -NewName "NewTS02"
```
This command gets the task sequence object named TaskSequence02 and uses the pipeline operator to pass the object to Set-CMTaskSequence , which changes the name of the task sequence object to NewTS02.


---


### Parameters
#### **AddSupportedOperatingSystemPlatform**

Adds a supported operating system platform object to the task sequence. To obtain a supported operating system platform object, use the Get-CMSupportedPlatform (Get-CMSupportedPlatform.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases                             |
|-------------------|--------|--------|-------------|------------------------------------|
|`[IResultObject[]]`|false   |named   |False        |AddSupportedOperatingSystemPlatforms|



#### **BootImageId**

Specifies the ID of a boot image.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Category**

Specifies a category for the task sequence. You can use categories to group task sequences.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CustomText**

Specifies custom text for the task sequence. Custom text appears in the progress notification dialog box while the task sequence runs.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeploymentPackageId**

Specifies the ID of a package. If you specify a value of $True for the RunAnotherProgram parameter, the specified package runs before the task sequence runs.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Description**

Specifies a description for the task sequence.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableTaskSequence**

Indicates whether to disable this task sequence.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableNotification**

Indicates whether to enable notifications for this task sequence.






|Type       |Required|Position|PipelineInput|Aliases            |
|-----------|--------|--------|-------------|-------------------|
|`[Boolean]`|false   |named   |False        |EnableNotifications|



#### **EnableTaskSequence**

Indicates whether to enable this task sequence.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **HighPerformance**

Use this parameter to set the following option on the Performance page of the task sequence properties: Run as high performance power plan .






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **InputObject**

Specifies a task sequence object. To obtain a task sequence object, use the Get-CMTaskSequence (Get-CMTaskSequence.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases     |
|-----------------|--------|--------|--------------|------------|
|`[IResultObject]`|true    |named   |True (ByValue)|TaskSequence|



#### **MaxRunTimeMins**

Specifies, in minutes, the maximum running time for the task sequence.






|Type     |Required|Position|PipelineInput|Aliases |
|---------|--------|--------|-------------|--------|
|`[Int64]`|false   |named   |False        |Duration|



#### **NewName**

Specifies a new name for the task sequence.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Returns the current working object. By default, this cmdlet does not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ProgramName**

Specifies the name of a program to run from a Configuration Manager software package specified by the DeploymentPackageId parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RemoveSupportedOperatingSystemPlatform**

Removes a supported operating system platform object from the task sequence. To obtain a supported operating system platform object, use the Get-CMSupportedPlatform (Get-CMSupportedPlatform.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases                                |
|-------------------|--------|--------|-------------|---------------------------------------|
|`[IResultObject[]]`|false   |named   |False        |RemoveSupportedOperatingSystemPlatforms|



#### **RunAnotherProgram**

Indicates whether to run another program before running the task sequence. Specify the program by using the DeploymentPackageId parameter and the ProgramName parameter.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RunEveryTime**

Indicates whether the program specified in the ProgramName parameter runs every time that the task sequence runs. If you specify a value of $False, the program does not run if it has run successfully in the past.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RunOnAnyPlatform**

Indicates that the task sequence runs on any operating system platform.






|Type      |Required|Position|PipelineInput|Aliases                               |
|----------|--------|--------|-------------|--------------------------------------|
|`[Switch]`|false   |named   |False        |ClearSupportedOperatingSystemPlatforms|



#### **SuppressNotification**

Indicates whether to suppress notifications for this task sequence.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **TaskSequenceId**

Specifies the ID of a task sequence.






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[String]`|true    |named   |False        |Id<br/>TaskSequencePackageId|



#### **TaskSequenceName**

Specifies the name of a task sequence.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



#### **UseBootImage**

Indicates whether the task sequence uses the boot image specified by using the BootImageID parameter.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UseDefaultText**

Indicates whether to use default text in the progress notification dialog box while the task sequence runs. If you select a value of $False for this parameter, be sure to specify custom text by using the CustomText parameter.






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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMTaskSequence [-AddSupportedOperatingSystemPlatform <IResultObject[]>] [-BootImageId <String>] [-Category <String>] [-CustomText <String>] [-DeploymentPackageId <String>] [-Description <String>] [-DisableTaskSequence <Boolean>] [-DisableWildcardHandling] [-EnableNotification <Boolean>] [-EnableTaskSequence <Boolean>] [-ForceWildcardHandling] [-HighPerformance <Boolean>] -InputObject <IResultObject> [-MaxRunTimeMins <Int64>] [-NewName <String>] [-PassThru] [-ProgramName <String>] [-RemoveSupportedOperatingSystemPlatform <IResultObject[]>] [-RunAnotherProgram <Boolean>] [-RunEveryTime <Boolean>] [-RunOnAnyPlatform] [-SuppressNotification <Boolean>] [-UseBootImage <Boolean>] [-UseDefaultText <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequence [-AddSupportedOperatingSystemPlatform <IResultObject[]>] [-BootImageId <String>] [-Category <String>] [-CustomText <String>] [-DeploymentPackageId <String>] [-Description <String>] [-DisableTaskSequence <Boolean>] [-DisableWildcardHandling] [-EnableNotification <Boolean>] [-EnableTaskSequence <Boolean>] [-ForceWildcardHandling] [-HighPerformance <Boolean>] [-MaxRunTimeMins <Int64>] [-NewName <String>] [-PassThru] [-ProgramName <String>] [-RemoveSupportedOperatingSystemPlatform <IResultObject[]>] [-RunAnotherProgram <Boolean>] [-RunEveryTime <Boolean>] [-RunOnAnyPlatform] [-SuppressNotification <Boolean>] -TaskSequenceId <String> [-UseBootImage <Boolean>] [-UseDefaultText <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequence [-AddSupportedOperatingSystemPlatform <IResultObject[]>] [-BootImageId <String>] [-Category <String>] [-CustomText <String>] [-DeploymentPackageId <String>] [-Description <String>] [-DisableTaskSequence <Boolean>] [-DisableWildcardHandling] [-EnableNotification <Boolean>] [-EnableTaskSequence <Boolean>] [-ForceWildcardHandling] [-HighPerformance <Boolean>] [-MaxRunTimeMins <Int64>] [-NewName <String>] [-PassThru] [-ProgramName <String>] [-RemoveSupportedOperatingSystemPlatform <IResultObject[]>] [-RunAnotherProgram <Boolean>] [-RunEveryTime <Boolean>] [-RunOnAnyPlatform] [-SuppressNotification <Boolean>] -TaskSequenceName <String> [-UseBootImage <Boolean>] [-UseDefaultText <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

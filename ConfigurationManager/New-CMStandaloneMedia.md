New-CMStandaloneMedia
---------------------




### Synopsis
Creates stand-alone media.



---


### Description

The New-CMStandaloneMedia cmdlet creates media used to deploy operating systems without network access.



NOTE: This cmdlet requires elevated permissions to run.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDistributionPoint](Get-CMDistributionPoint)



* [Get-CMPackage](Get-CMPackage)



* [Get-CMTaskSequence](Get-CMTaskSequence)





---


### Examples
#### Example 1: Create stand-alone media using variables
```PowerShell
PS XYZ:\> $TaskSequence = Get-CMTaskSequence -Name "TaskSequence01"
PS XYZ:\> $DistributionPoint = Get-CMDistributionpoint -SiteCode CM1
PS XYZ:\> New-CMStandaloneMedia -MediaType CdDvd -Path \\server\share\standaloneMedia.iso -TaskSequence $TaskSequence -DistributionPoint $DistributionPoint
```
The first command gets the task sequence object named TaskSequence01 and stores the object in the $TaskSequence variable.


The second command gets the distribution point object for the site code named CM1 and stores the object in the $DistributionPoint variable.


The last command creates stand-alone media using the task sequence stored in $TaskSequence and the distribution point stored in $DistributionPoint.


---


### Parameters
#### **AllowUacPrompt**

Indicates that User Account Control (UAC) prompts are allowed.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **AllowUnattended**

Indicates that unattended operating system deployments are allowed. An unattended operating system deployment does not prompt for network configuration or optional task sequences.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Application**








|Type               |Required|Position|PipelineInput|Aliases     |
|-------------------|--------|--------|-------------|------------|
|`[IResultObject[]]`|false   |named   |False        |Applications|



#### **CertificatePath**

Specifies a path from which to import a PKI certificate.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DistributionPoint**

Specifies an array of distribution point objects. To obtain a distribution point object, use the Get-CMDistributionPoint (Get-CMDistributionPoint.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases           |
|-------------------|--------|--------|-------------|------------------|
|`[IResultObject[]]`|true    |named   |False        |DistributionPoints|



#### **DriverPackage**








|Type               |Required|Position|PipelineInput|Aliases                                            |
|-------------------|--------|--------|-------------|---------------------------------------------------|
|`[IResultObject[]]`|false   |named   |False        |DriverPackages<br/>PackageDriver<br/>PackageDrivers|



#### **Force**

Forces the command to run without asking for user confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FormatMedia**

Indicates that the cmdlet formats the removable USB drive (FAT32), and makes it bootable.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **IncludeApplicationDependency**

Indicates that the cmdlet detects associated application dependencies and adds them to this media.






|Type      |Required|Position|PipelineInput|Aliases                       |
|----------|--------|--------|-------------|------------------------------|
|`[Switch]`|false   |named   |False        |IncludeApplicationDependencies|



#### **MediaExpirationDate**








|Type        |Required|Position|PipelineInput|Aliases   |
|------------|--------|--------|-------------|----------|
|`[DateTime]`|false   |named   |False        |Expiration|



#### **MediaPassword**

Specifies, as a secure string, a password to protect task sequence media.






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|false   |named   |False        |



#### **MediaSize**

Specifies the size of the media. Valid values are:


* None


* Size4GB


* Size8GB


* Size650MB


* SizeUnlimited



Valid Values:

* None
* Size650MB
* Size4GB
* Size8GB
* SizeUnlimited






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[MediaSize]`|false   |named   |False        |



#### **MediaStartDate**








|Type        |Required|Position|PipelineInput|Aliases|
|------------|--------|--------|-------------|-------|
|`[DateTime]`|false   |named   |False        |Start  |



#### **MediaType**

Specifies the media type. Valid values are:


* CdDvd


* Usb


* Hd



Valid Values:

* Usb
* CdDvd
* Hd






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[MediaInputType]`|true    |named   |False        |



#### **NoAutoRun**

Use this parameter to configure the following option from the create task sequence media wizard: Include autorun.inf file on media






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Package**








|Type               |Required|Position|PipelineInput|Aliases |
|-------------------|--------|--------|-------------|--------|
|`[IResultObject[]]`|false   |named   |False        |Packages|



#### **Path**

Specifies the name and path where the output files are written.






|Type      |Required|Position|PipelineInput|Aliases                               |
|----------|--------|--------|-------------|--------------------------------------|
|`[String]`|true    |named   |False        |MediaPath<br/>OutputPath<br/>DriveName|



#### **PrestartCommand**

Specifies a prestart command that will run before the task sequence runs. A prestart command is a script or an executable that can interact with the user in Windows PE before the task sequence runs to install the operating system.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[String]`|false   |named   |False        |PreExecCommandLine|



#### **PrestartPackage**

Specifies a package object that contains files for the prestart command. To obtain a package object, use the Get-CMPackage (Get-CMPackage.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **SiteCode**

{{ Fill SiteCode Description }}






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **TaskSequence**

Specifies a task sequence object. To obtain a task sequence object, use the Get-CMTaskSequence (Get-CMTaskSequence.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **TemporaryFolder**

{{ Fill TemporaryFolder Description }}






|Type      |Required|Position|PipelineInput|Aliases                           |
|----------|--------|--------|-------------|----------------------------------|
|`[String]`|false   |named   |False        |TemporaryDirectory<br/>StagingArea|



#### **Variable**

Specifies a task sequence variable. A task sequence variable is a name/value pair that is used during the task sequence deployment.






|Type         |Required|Position|PipelineInput|Aliases                            |
|-------------|--------|--------|-------------|-----------------------------------|
|`[Hashtable]`|false   |named   |False        |TaskSequenceVariables<br/>Variables|



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
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
New-CMStandaloneMedia [-AllowUacPrompt] [-AllowUnattended] [-Application <IResultObject[]>] [-CertificatePath <String>] [-DisableWildcardHandling] -DistributionPoint <IResultObject[]> [-DriverPackage <IResultObject[]>] [-Force] [-ForceWildcardHandling] [-FormatMedia] [-IncludeApplicationDependency] [-MediaExpirationDate <DateTime>] [-MediaPassword <SecureString>] [-MediaSize {None | Size650MB | Size4GB | Size8GB | SizeUnlimited}] [-MediaStartDate <DateTime>] -MediaType {Usb | CdDvd} [-NoAutoRun] [-Package <IResultObject[]>] -Path <String> [-PrestartCommand <String>] [-PrestartPackage <IResultObject>] [-SiteCode <String>] -TaskSequence <IResultObject> [-TemporaryFolder <String>] [-Variable <Hashtable>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

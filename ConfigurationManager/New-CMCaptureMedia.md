New-CMCaptureMedia
------------------




### Synopsis
Creates capture media.



---


### Description

The New-CMCaptureMedia cmdlets creates media used to capture an operating system deployment image from a reference computer.



NOTE: This cmdlet requires elevated permissions to run.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMBootImage](Get-CMBootImage)



* [Get-CMDistributionPoint](Get-CMDistributionPoint)





---


### Examples
#### Example 1: Create capture media
```PowerShell
PS XYZ:\> $BootImage = Get-CMBootImage -Name "Boot image (x64)"
PS XYZ:\> $DistributionPoint = Get-CMDistributionpoint -SiteCode CM1
PS XYZ:\> New-CMCaptureMedia -MediaType CdDvd -Path "\\server\share\CaptureMedia.iso" -BootImage $BootImage -DistributionPoint $DistributionPoint
```
The first command gets the boot image object named Boot image (x64) and stores the object in the $BootImage variable.


The second command gets the distribution point object for the site code named CM1 and stores the object in the $DistributionPoint variable.


The last command creates capture media using the BootImage stored in $BootImage, and the distribution point stored in $DistributionPoint.


---


### Parameters
#### **AllowUacPrompt**

Indicates that User Account Control (UAC) prompts are allowed.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **BootImage**

Specifies a boot image object. To obtain a boot image object, use the Get-CMBootImage (Get-CMBootImage.md)cmdlet.






|Type             |Required|Position|PipelineInput|Aliases         |
|-----------------|--------|--------|-------------|----------------|
|`[IResultObject]`|true    |named   |False        |BootImagePackage|



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



#### **MediaType**

Specifies the media mode. Valid values are:


* Usb


* CdDvd


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



#### **Path**

Specifies the name and path where the output files are written.






|Type      |Required|Position|PipelineInput|Aliases                               |
|----------|--------|--------|-------------|--------------------------------------|
|`[String]`|true    |named   |False        |MediaPath<br/>OutputPath<br/>DriveName|



#### **SiteCode**

{{ Fill SiteCode Description }}






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **TemporaryFolder**

{{ Fill TemporaryFolder Description }}






|Type      |Required|Position|PipelineInput|Aliases                           |
|----------|--------|--------|-------------|----------------------------------|
|`[String]`|false   |named   |False        |TemporaryDirectory<br/>StagingArea|



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
New-CMCaptureMedia [-AllowUacPrompt] -BootImage <IResultObject> [-DisableWildcardHandling] -DistributionPoint <IResultObject[]> [-Force] [-ForceWildcardHandling] [-FormatMedia] -MediaType {Usb | CdDvd} [-NoAutoRun] -Path <String> [-SiteCode <String>] [-TemporaryFolder <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
